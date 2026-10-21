# Scoped Adversarial Review: `evalRat` Exponent Safety

## Mission

Independently review the latest change to:

`phys-lib/gr/ltb/protocol/derivation_test.go`

The change adds fail-closed exponent bounds to the test-side `evalRat` evaluator and the test `TestEvaluatorExponentBounds`.

The implementation report states that:
- The `TagPow` branch checks exponent integer-ness, then uses safe `big.Int` comparisons before conversion or negation.
- Exponents outside the documented oracle bound \(|n|\leq1024\) are rejected.
- The change prevents undefined narrowing behavior, `math.MinInt64` negation problems, and impractically long exponentiation loops.
- Zero-to-negative-power rejection and supported nonzero-base negative powers remain intact.
- The all-\(r\) proof check (`TestMPrimeStructureAllR`) and `monomialParts` remain unchanged.
- Formatting, vet, targeted tests, and the full `phys-lib` suite passed.

Verify these claims against the actual source. Do not accept the completion report or comments as proof.

## Review standard

Apply the agreed minimum passing standard:

**PASS** if there are no structural blockers in the guard or its tests.

**REVISE** only if a material defect permits silent mis-evaluation, integer overflow or narrowing, a hang from excessive iteration, incorrect handling of negative powers, or a test that fails to exercise the claimed protection.

Minor style preferences, redundant checks, or optional improvements must not block acceptance.

This is a review-only task. Do not modify files, commit, push, tag, publish, add dependencies, or propose an architecture redesign.

## 1. Inspect the actual change

Inspect the live working tree and the diff for `phys-lib/gr/ltb/protocol/derivation_test.go`.

Confirm the change is limited to the intended evaluator guard and targeted tests. Inspect the surrounding `evalRat` implementation and its use by `monomialParts` so that the guard is reviewed in context.

Do not redo the entire ZEH/LTB review. Reopen an earlier concern only if this change materially affects it.

## 2. Attack the `TagPow` guard

Verify the actual order of operations.

The exponent must be evaluated and confirmed to be an integer before being accepted. Its size must be checked using safe arbitrary-precision comparisons **before any narrowing conversion, negation, or exponentiation loop**.

Specifically check:

1. A nested exponent such as \(10^{30}\) cannot overflow or silently narrow into a small exponent.
2. `math.MinInt64` cannot trigger an overflow during absolute-value or negation handling.
3. A large but representable exponent, such as \(10^9\), is rejected before a loop begins.
4. No code path reaches `Int64()` or negation before the relevant safety checks.
5. The bound is implemented without an overflow-prone magnitude calculation.
6. The documented \(|n|\leq1024\) limit applies to the evaluator's accepted exponent, not to the general mathematical semantics of PhysMath.
7. The small accepted exponent range does not introduce unreasonable work or recursion through nested exponent expressions. Report this only if a concrete material failure path exists.

Do not demand support for arbitrarily large powers. The intended behavior is to reject unsupported inputs, not to implement unlimited exact-rational exponentiation.

## 3. Verify negative-power semantics

Check the actual base handling:

- \(r^0\) and supported small positive powers continue to evaluate correctly.
- A supported negative integer exponent evaluates correctly when the base is nonzero.
- Zero raised to a negative power is rejected.
- Non-integer exponents are rejected.
- Negative exponents outside the supported bound are rejected before inversion or iteration.
- Errors propagate to the test caller rather than being converted into plausible numerical values.

Use the existing evaluator contract. Do not expand its accepted AST language.

## 4. Adversarially inspect the tests

Inspect `TestEvaluatorExponentBounds` and its existing supporting tests.

Verify that each negative test genuinely reaches the relevant `TagPow` guard and asserts an error:

- Nested/oversized exponent, such as `Pow(r, Pow(10, 30))`.
- `math.MinInt64` exponent.
- Large exponent such as \(10^9\) that would otherwise cause excessive iteration.

Verify positive controls:
- Existing supported small exponents still work.
- Exponent \(-2\) works for a nonzero base.
- Zero raised to a negative exponent remains rejected.

Check that test setup does not itself overflow, that nested-exponent evaluation actually traverses the intended path, and that the positive controls validate results rather than only checking for the absence of errors.

Do not request elaborate fuzzing or property-based infrastructure unless you identify a concrete defect that cannot be covered by a minimal targeted test.

## 5. Protect the all-\(r\) argument

Confirm that `monomialParts` and `TestMPrimeStructureAllR` remain unchanged and that the new bound does not weaken their existing guarantees.

The intended all-\(r\) argument still rests on checking the actual stored derivative expression's permitted structure, non-negative integer powers of the declared radial variable, exact rational coefficients, and degree-two coefficients summing to \(3/2\).

The finite-sample pointwise check remains supplementary corroboration. Do not conflate the evaluator's exponent bound with the scope of the mathematical derivative identity.

## 6. Run verification

If the live workspace is available, execute:

- `gofmt -l gr/ltb/protocol/derivation_test.go`
- `go vet ./gr/ltb/...`
- The targeted test `go test ./gr/ltb/protocol/... -run 'TestEvaluatorExponentBounds|TestEvaluatorSanity|TestMPrimeStructureAllR|TestMonomialPartsAdversarial'`
- `go test ./gr/ltb/...`
- `go test ./...` from the `phys-lib` module root.

Record actual commands and results. Do not claim a test passed if you only inspected its source or relied on cached report text. If a command is unavailable or fails for an environmental reason, distinguish that from a code defect.

Confirm that frozen `phys` and `phys-gr` remain untouched and that no changes outside the intended scope were introduced.

## 7. Report

Use this concise format:

### A. Verdict
`PASS` or `REVISE`, with a one-paragraph rationale.

### B. Structural blockers
List only material defects. For each, identify the file and function, the failure path, why it matters, and the smallest fix.

If none remain, state: **No structural blockers found in the scoped exponent-safety change.**

### C. Optional observations
Include only useful non-blocking notes. Do not disguise minor preferences as blockers.

### D. Verification
List commands actually executed and their results.

### E. Scope and scientific status
Confirm whether the change is confined to the intended file and whether frozen repositories remain untouched. State that ZEH-Q-03 remains an open conjecture; this change establishes no new physics result.

## Final instruction

Review this change independently and proportionately. Attack the integer boundaries and error paths, but do not restart the architecture review or expand the task beyond the exponent evaluator.

The goal is a reliable pre-commit decision, not another general hardening campaign.