# Minimal Fix: Fail-Closed Exponent Evaluation in the LTB Test Oracle

## Objective

Fix the identified integer-overflow and excessive-loop failure path in `phys-lib/gr/ltb/protocol/derivation_test.go`.

This is a targeted test-hardening change. Do not redesign `evalRat`, change PhysMath, add new primitives, or reopen the architecture.

## 1. Guard the `evalRat` power branch

In `evalRat`, inspect the `TagPow` branch. After recursively evaluating the exponent and confirming it is an integer, but **before converting it with `Int64()` or entering the exponentiation loop**:

1. Require the exponent numerator to fit in `int64`, using the appropriate `math/big.Int` range check.
2. Reject exponents outside the documented test-oracle bound \(|n|\leq1024\).
3. Only then convert to `int64` and perform exponentiation.
4. Ensure the check cannot itself overflow when handling `math.MinInt64`.
5. Preserve existing behavior for supported expressions, including negative powers where the base is nonzero. Continue rejecting zero raised to a negative power.

Treat the bound as a limitation of this test-side exact-rational evaluator, not as a restriction on the mathematical domain of PhysMath.

## 2. Add minimal adversarial tests

Extend the existing evaluator tests with:

- **Oversized nested exponent:** evaluate an expression such as `Pow(r, Pow(10, 30))`; it must return an error rather than silently narrowing the exponent or returning an incorrect value.
- **Minimum `int64` exponent:** an exponent of `math.MinInt64` must fail safely before negation or looping.
- **Large but representable exponent:** an exponent such as \(10^9\) must be rejected by the documented bound without attempting a billion iterations.
- **Positive control:** existing small integer exponents, including the current cases from zero through three, must continue to work.
- Preserve the existing non-integer, negative-exponent and zero-base protections.

Ensure each negative test actually exercises the `evalRat` power branch and checks that an error is returned.

## 3. Preserve the all-\(r\) argument

Do not weaken or replace `TestMPrimeStructureAllR`. Its degree accumulation must remain arbitrary-precision, and `monomialParts` must continue rejecting negative or non-integer exponents and mismatched radial parameter identities.

Keep the distinction explicit:

- `TestMPrimeStructureAllR` establishes the derivative identity for the restricted expression structure it checks.
- `TestMPrimePointwise` is supplementary finite-sample corroboration.
- The test oracle's exponent bound is a fail-closed implementation limit, not a theorem about arbitrary expressions.

## 4. Scope and verification

Keep changes within `phys-lib/gr/ltb/`. Do not modify frozen `phys` or `phys-gr`, shared schemas, artifact families, namespaces, or production mathematical rules.

Run formatting, the LTB protocol tests, the complete LTB package tests, and the full `phys-lib` test suite. Report the exact commands and results, including the new adversarial test cases.

Do not commit, push, tag, or publish.

**Acceptance criterion:** no accepted exponent can trigger silent integer narrowing, overflow-induced incorrect evaluation, or an impractically long loop. Supported existing calculations remain unchanged, and the scientific status of ZEH-Q-03 remains open.