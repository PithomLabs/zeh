# Targeted Hardening: ZEH/LTB Derivation Tests

## Mission

Address the findings from the adversarial review of `phys-lib/gr/ltb/protocol/derivation_test.go` and its supporting fixture.

This is a targeted test-hardening task, not an architecture redesign. Inspect the live workspace and package-local instructions, make the smallest changes necessary, run the relevant tests, then run the full `phys-lib` test suite.

The objective is to ensure that each test verifies the actual artifact and behavior it claims to verify, independently of the implementation where required.

### Mandatory boundaries

- Modify only `phys-lib/gr/ltb/` unless a genuine dependency or contract issue makes that impossible. If a change outside this directory appears necessary, stop and report why before making it.
- Do not modify frozen `phys` or `phys-gr`.
- Do not add a new PhysMath primitive, rule, artifact family, schema, or epistemic state machine.
- Do not claim that `Fixture.Verify()` proves scientific truth.
- Keep Q-01 as a literature claim requiring verification, Q-02 as an incomplete candidate construction, Q-03 as an open conjecture, and Q-04 as deferred.
- Do not change the scientific scope of the ZEH/LTB investigation.
- Read actual APIs and package contracts before implementing; do not invent methods or assumptions.

## Finding 1 — Repair `TestThetaStructure`

**Problem:** The current test decodes `ThetaRef`, calls `Canonicalize`, discards the result, and checks an encoding round-trip. This does not establish the promised expression structure. The sigma test checks only that an expression artifact exists.

### Required changes

For `ThetaRef`, inspect the decoded AST and explicitly verify the expected structure:

\[
\theta=H+2H.
\]

Assert that the outer node is the expected `Add`; inspect its children and confirm the coefficient is exactly two and both occurrences of \(H\) have the same encoded symbol identity. Do not compare display names alone.

For `SigmaRef`, inspect the decoded AST and verify that it structurally represents

\[
\sigma^2=\frac13(H-H)^2
\]

using the same \(H\) identity in both terms. Confirm that the represented expression is not accidentally different because of a wrong coefficient, operator, or variable identity.

Verify that `ThetaCanon` is the output of the recorded canonicalization derivation: check the actual derivation rule, its input, output, result references, and correspondence to the fixture's recorded refs. Check canonicalization against its documented contract without pretending canonicalization proves a physical result.

Retain the assertion that the sigma construction is represented-only and does not enter the executed derivation inventory.

Add negative controls for at least:
- Distinct symbol identities with the same display name.
- An incorrect theta coefficient.
- An incorrect sigma factor or mismatched \(H\) identity.
- A derivation whose recorded output does not match the expected `ThetaCanon` reference.

## Finding 2 — Connect the cone identity test to stored artifacts

**Problem:** `TestConeIdentityRational` currently reconstructs \(u,V_0,Q_0,R_{c0},P_0\) directly with Go rational arithmetic. It therefore does not catch incorrect expressions stored in `Fixture.ConeRefs`. `TestVertexCoefficients` similarly verifies a standalone series calculation rather than a stored vertex artifact.

### Required changes

For the cone identity test, resolve and decode the actual stored expressions referenced by:

- `ConeRefs["u"]`
- `ConeRefs["V0"]`
- `ConeRefs["Q0"]`
- `ConeRefs["Rc0"]`
- `ConeRefs["P0"]`

Validate the stored expression structures against independently constructed expectations. Then evaluate the decoded stored expressions with the test-side exact-rational evaluator and use those values in the cone-identity check.

The evaluator must not resolve variables by display name alone. Validate bound parameter identity against the declared radial function and its `ParameterID` before evaluation. A same-labeled symbol with a different identity must be rejected.

Preserve exact-rational arithmetic, the current finite-sample corroboration label, and anti-goldens for wrong expressions. Do not describe finitely many evaluations as a symbolic proof of the cone identity.

For `TestVertexCoefficients`, choose the smallest honest treatment:
- Either connect the series calculation to an actual stored vertex-series artifact, if one already exists and the representation supports it faithfully; or
- Explicitly document and name it as a standalone analytical cross-check, not executed evidence for a stored artifact.

Do not create a new artifact type simply to make this test appear more complete.

Add negative tests demonstrating that a corrupted stored cone expression is detected, including a wrong radial power, an incorrect coefficient, and a same-display-name/different-identity radial symbol.

## Finding 3 — Exercise the real assumption-verification path

**Problem:** `TestAssumptionLinkage` creates a separate `PhysicalTheorem` and duplicates family-check logic inside the test. It does not demonstrate that the actual `Fixture.Verify()` path rejects mutations to the fixture's required assumptions. The existing mutation tests only establish family-level rejection.

### Required changes

Refactor the tests to mutate a freshly built fixture's actual `PhysThm` and `EqGauge` values and invoke `Fixture.Verify()`.

Test at least:
- Missing required assumptions.
- Dangling assumption references.
- Wrong-family references.
- Substitution of one valid `PhysicalAssumption` for a different required assumption of the same family.

The fixture's contract explicitly identifies the gauge and regime assumptions for the executed fragment. Verify their required identities, not just the broad family `assumption/1`, where the existing model supports that check.

If this requires a narrowly scoped check in `Fixture.Verify()`, implement it there using existing APIs. Do not generalize it into a new schema or state machine.

Inspect the relationship between the in-memory `PhysThm` / `EqGauge` values and their stored artifact references. Where existing APIs support validating that relationship, ensure the verification path does not silently validate the in-memory object while ignoring a mismatched stored artifact. If the current contract cannot enforce a required relationship, document the exact limitation instead of claiming it is enforced.

Each adversarial test must fail because the production verification path rejects the malformed fixture—not because a duplicate checker in the test happens to reject it.

## Finding 4 — Make the all-\(r\) degree check overflow-safe

**Problem:** `monomialParts` accumulates degree in an `int64`, and `Int64()` is used for an exponent without first establishing representability. A sufficiently large exponent or sum could overflow and undermine the purported all-\(r\) argument.

### Required changes

Make `TestMPrimeStructureAllR` safe against exponent and degree overflow.

Prefer accumulating total polynomial degree with `math/big.Int`, or use checked arithmetic that rejects overflow before it can influence classification. Never silently narrow an arbitrary-precision exponent to `int64`.

Keep the structural argument explicit:

1. Decode the actual stored derivative output.
2. Resolve the radial parameter identity through its declaring function.
3. Require the expected sum-of-monomials structure.
4. Require all factors to be rational coefficients or non-negative integer powers of the correctly declared \(r\).
5. Verify that every nonzero term has total degree two.
6. Independently sum the exact rational coefficients of those degree-two terms and verify the result is \(3/2\).
7. Permit zero-coefficient residues only when their non-negative exponents preserve well-defined behavior at \(r=0\).

Add adversarial unit cases for:
- Oversized integer exponents.
- Degree-sum overflow or the corresponding arbitrary-precision case.
- Fractional and negative exponents.
- Wrong parameter identity despite the same display name.
- Non-monomial factors.
- Nonzero terms of degrees other than two.

For every rejection, assert that the verifier fails closed. Do not rely on the current differentiation engine only generating small exponents.

Keep `TestMPrimePointwise` as explicitly labeled finite-sample corroboration. The independently justified structural argument is the all-\(r\) result.

## Finding 5 — Verify the derivation inventory and output linkage

**Problem:** The current inventory test checks count, uniqueness, artifact family, decoding, replay, and `Fixture.Verify()`. It does not fully verify that each inventory entry corresponds to the operation and result the fixture claims to have executed.

### Required changes

Strengthen `TestDerivationInventory` to inspect the actual decoded derivations, not merely count and replay them.

For each inventory entry, validate as appropriate:
- Expected producer namespace and rule ID.
- Exact ordered input references.
- Required conditions and differentiation parameters.
- Output and result references.
- Correspondence to the fixture's expected operation and stored result.

In particular, explicitly establish:
- The differentiation derivation consumes `MRef` and the declared radial function, differentiates with respect to the correct bound parameter, and produces `MPrimeRef`.
- The canonicalization derivation consumes `ThetaRef` and produces `ThetaCanon`.
- The fixture's hand-golden and theorem-conclusion checks refer to the intended stored derivative result.
- Every derivation claimed as executed is included in the inventory, and no represented-only expression is inadvertently counted as executed evidence.

Preserve the corrupted-replay negative test. Where possible, add mutations to the derivation rule, input refs, and output/result refs, and confirm they cannot pass verification.

Do not treat replay success alone as proof that the derivation is relevant to a scientific claim or that its physical interpretation is correct.

## Claim-state limitation — preserve, do not overengineer

`CheckClaimPromotion` is a limited metadata/evidence-consistency check. It rejects an unsupported `proved` status when no evidence is cited or the cited evidence is outside the fixture inventory. It does not prove that an in-inventory derivation establishes the claim being promoted.

Keep this boundary explicit in comments, tests, README, and manifest. Do not add a state machine, artifact-schema status field, or claim-specific proof framework during this task.

A green `Verify()` result establishes the checks it actually performs. It does not establish the ZEH-Q-03 non-identifiability theorem, validate all scientific statuses, or prove empirical truth.

## Verification and completion report

Run the appropriate formatter and tests, then run the full `phys-lib` test suite. Report the actual commands and results; do not infer successful execution from code inspection.

The completion report must state:

1. Exact files changed and why.
2. How each of the five findings was addressed.
3. New negative tests and which defects they demonstrate.
4. Whether stored-artifact verification and assumption linkage are complete, or which gaps remain.
5. The precise scope of the all-\(r\) derivative argument.
6. Actual package and full-suite test results.
7. Confirmation that no frozen repository, shared schema, or architecture was changed.
8. Confirmation that Q-03 remains open and that no spatial-integration capability was introduced.

### Acceptance criterion

The implementation is ready when the tests genuinely inspect stored artifacts, test the production verification path, reject meaningful malformed inputs, and distinguish all-\(r\) algebraic arguments from finite-sample corroboration.

Do not enlarge the task beyond these findings. Preserve the existing architecture, report remaining limitations honestly, and finish with a reproducible verification report.