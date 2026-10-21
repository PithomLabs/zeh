Refer to github.com/PithomLabs/phys-lib/gr/ltb


# Adversarial review: ZEH/LTB derivation tests

Verdict: REVISE — the new all-\\(r\\) derivative check is a meaningful improvement, but the overall test suite still overstates what some tests verify. I would keep the architecture and research scope unchanged. The remaining work is targeted test hardening and more precise evidence claims.

I reviewed the uploaded Go source, fixture, manifest, and README. I have not independently rerun the Go suite because the full workspace and its dependencies were not supplied; the green results remain reported rather than independently reproduced here.

## What improved and should be retained

`TestMPrimeStructureAllR` is the strongest addition. Instead of treating agreement at five sample points as a proof, it decodes the stored derivative output and checks its polynomial structure: only powers of the declared radial variable, rational coefficients, no nonzero terms of degree other than two, and a total degree-two coefficient of \\(3/2\\).&#x20;

derivation_test.go



That is a valid all-\\(r\\) argument for an expression satisfying those checked structural conditions, provided the degree arithmetic itself cannot overflow. It is materially stronger than the earlier finite-sample check.

The explicit `M(r)=r^3/2` convention, the independent \\(D_A^\*(z)\\) coefficient calculation, and the distinction between executed and represented-only mathematics are also worth preserving.&#x20;

README.md



## Findings that need attention

High

### 1. `TestThetaStructure` does not test the structure it claims to test

The comment promises to verify that \\(\theta=H+2H\\) uses one shared variable identity. But the test only decodes the expression, calls `Canonicalize`, discards the result, and checks that encoding and decoding preserve the expression. It never inspects the actual `Add`, `Mul`, coefficient, or symbol identities.&#x20;

derivation_test.go



The sigma check has the same problem: it confirms that the stored artifact is an expression, but not that it actually represents \\(\frac13(H-H)^2\\) using the same \\(H\\).&#x20;

derivation_test.go



Required fix: inspect the decoded AST and assert the expected structure and shared identity explicitly. Also connect the stored `ThetaCanon` result to its derivation output and verify the result against an independent expectation appropriate to the actual canonicalization contract.

Until then, this test does not substantiate its advertised structural claim.

High

### 2. The cone identity tests do not check the stored cone expressions

`TestConeIdentityRational` reconstructs \\(u,V_0,Q_0,R\_{c0},P_0\\) directly as Go rational calculations. It never reads `f.ConeRefs`. Therefore, the test can continue passing if the structured cone artifacts are wrong. `TestVertexCoefficients` likewise checks a standalone series calculation rather than linking it to a stored vertex-series artifact.&#x20;

derivation_test.go



This is a provenance and coverage gap, not a reason to add a new mathematics primitive.

Required fix: load the actual stored cone expressions, independently evaluate those expressions at the rational sample points, and use those results in the identity check. Add structural checks against independently constructed expectations. Keep the finite-sample result explicitly labeled as corroboration, not a symbolic proof. For the vertex calculation, either link it to a stored artifact or clearly label it as a standalone analytical cross-check.

High

### 3. `TestAssumptionLinkage` tests its own duplicate checks, not the production verification path

The test creates a new `PhysicalTheorem` from hard-coded fixture references, implements the family-check loop locally, and repeats that loop for mutated references. It does not mutate the actual fixture and assert the behavior of `f.Verify()`.&#x20;

derivation_test.go



Furthermore, the mutation replaces an assumption with an expression artifact. That checks rejection by family, not correctness of the specific assumptions. Replacing `ltb_gauge` with another `PhysicalAssumption` such as `ltb_target` would pass a family-only check even though it may violate the fixture's intended contract.

`Fixture.Verify()` currently checks `TargetChecks()` on the in-memory `PhysThm` and `EqGauge` objects. The test should exercise that actual path.&#x20;

fixture.go



Required fix: mutate the actual fixture's assumption references and assert that `f.Verify()` rejects missing, dangling, wrong-family, and—where the fixture contract specifies exact required references—same-family substituted assumptions. If the existing API cannot express a particular semantic requirement, document that limitation instead of pretending a family check proves it.

Medium

### 4. The all-\\(r\\) checker can overflow its degree counter

`monomialParts` accumulates the total degree in an `int64` and converts each integer exponent using `Int64()` without checking whether the value or sum is representable.&#x20;

derivation_test.go



A crafted expression containing several enormous, non-negative integer powers of \\(r\\) can overflow the counter. In principle, a polynomial of a degree other than two could then be misclassified as degree two. That is precisely the kind of edge case a structural verifier should reject.

Required fix: accumulate degree with arbitrary-precision integers or use checked arithmetic that rejects overflow before it can affect the result. Add negative tests for oversized exponents and degree-sum overflow. Do not rely on the current differentiation rule happening to emit small exponents.

Medium

### 5. Derivation inventory coverage is not sufficiently specific

`TestDerivationInventory` checks the expected count, uniqueness, artifact family, decoding, and replay. Those are useful checks, but they do not by themselves establish that each inventory entry represents the exact operation and output the fixture claims to have executed.&#x20;

derivation_test.go



This matters especially for the theta-canonicalization derivation: the suite does not explicitly bind the corresponding inventory entry to `ThetaRef`, the canonicalization rule, and `ThetaCanon`.

Required fix: inspect every derivation step and assert the expected rule, inputs, conditions, and output references. Ensure the theta entry specifically produces the recorded `ThetaCanon` result, and that every executed derivation claimed by the fixture is covered by the verification inventory.

## One important limitation that must remain explicit

`CheckClaimPromotion` currently rejects a `proved` status with no evidence and rejects references outside the fixture inventory. But it does not establish that an in-inventory derivation is relevant to the claim being promoted.&#x20;

claim.go



For example, an unrelated mass-derivative artifact could satisfy the current membership test for Q-03. That would not prove the backreaction non-identifiability theorem.

This is acceptable as a deliberately limited metadata/evidence-consistency check, provided the documentation continues to say so. Do not introduce a new state machine or modify the artifact schema to solve it in this slice. Clarify that inventory membership is not claim-specific scientific proof.

## Recommended disposition

Keep the new all-\\(r\\) approach. Address findings 1–4, tighten derivation-to-output linkage in finding 5, and preserve the documented claim-evidence limitation.

The most important lesson from this review is that a test must inspect the actual artifact and exercise the production verification path—not independently recreate the expected calculation and then pass itself.

No new architecture, no changes to frozen `phys` or `phys-gr`, and no expansion into a spatial-integration engine are needed. After those targeted corrections, rerun the package tests and full `phys-lib` suite, then reassess the reference implementation. Q-03 remains an open conjecture throughout.