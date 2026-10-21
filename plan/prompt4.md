# Independent Adversarial Code Review — Phys ZEH/LTB Reference Implementation

## Mission

Conduct an independent, adversarial review of all changes made so far for the ZEH/LTB research-workflow reference implementation in `phys-lib/gr/ltb/`, before the user commits the work to GitHub.

The implementation is intended to demonstrate how Phys can faithfully formalize a real scientific investigation: problem definition, assumptions, mathematical representations, partial derivations, claims, evidence, proof obligations, and limitations.

Your job is to determine whether the implementation meets that purpose without structural defects in its logic, mathematical meaning, verification path, or scientific claims.

**Do not implement fixes, commit, push, tag, publish, or modify any files.** This is a review-only task. Report findings and recommendations so the owner can decide what to change.

## 1. Review standard

Use a blocker-focused standard.

A **structural blocker** is a defect that materially undermines correctness, logical soundness, derivation provenance, assumption enforcement, the meaning of a represented quantity, or the reliability of a verification claim.

Examples include:

- A mathematically incorrect derivative or series coefficient.
- A test that claims to check an invariant but never inspects the relevant expression or artifact.
- A verifier that accepts corrupted or semantically substituted evidence.
- A stored artifact that is disconnected from the derivation claimed to produce it.
- Incorrect variable identity, operator order, premise, or model convention.
- An all-\(r\) argument whose structure permits an incorrect polynomial to pass.
- A status or documentation claim that materially overstates what the code establishes.
- An accidental modification of a frozen repository or an unrelated package.

Minor style issues, redundant assertions, naming preferences, and nonessential improvements are **not blockers** if the derivation's core logic and intended semantics remain sound.

Do not invent work to make the review appear comprehensive. Do not demand perfect formalization of mathematical capabilities that this slice explicitly documents as unsupported. Do not reopen architecture merely because another design is imaginable.

Use these outcomes:

- **PASS:** No structural blockers remain for the stated purpose.
- **REVISE:** At least one material structural blocker remains.
- **OPTIONAL IMPROVEMENTS:** Useful but non-blocking suggestions, listed separately.

## 2. Reconnaissance: inspect the actual repository

Read applicable workspace and package instructions, including the current `AGENTS.md`, normative `DERIVATION_SPEC_GUIDELINES.md`, additive `GUIDELINES.md`, and relevant package contracts.

Inspect the real working tree, not only the prior completion report or previously supplied file copies.

At minimum:

1. Run `git status --short --untracked-files=all`.
2. Inspect `git diff` and `git diff --cached`.
3. Inspect every new or modified file under `phys-lib/gr/ltb/`, including untracked files.
4. Inspect the live implementations and contracts used by the fixture in `phys-artifact`, `phys-math`, and `phys-lib/gr`.
5. Review `README.md`, `manifest.json`, `manifest_test.go`, `claim.go`, `fixture.go`, `doc.go`, and `protocol/derivation_test.go`.
6. Inspect `derivation_review.md` and other implementation notes if present. Confirm that claimed review artifacts actually exist.
7. Trace critical behavior through the real production verification functions. Do not infer behavior from test comments.

The implementation report states that the new fixture is confined to `phys-lib/gr/ltb/`. Verify that boundary from the actual workspace.

Do not treat an untracked directory as equivalent to a tracked diff. Enumerate what would actually be included in the proposed commit and identify unrelated, unexpected, missing, or generated files.

## 3. Frozen-system and architecture boundaries

The repositories `phys` and `phys-gr` are frozen predecessor/reference systems.

Verify that:

- No files in frozen repositories have been modified.
- The new fixture lives under the active `phys-lib/gr/ltb/` package.
- Reuse of the durable `phys-gr` namespace follows an existing live contract and has no unintended collision or dependency on frozen code.
- No new shared schema, primitive, mathematical operation, artifact family, namespace, or state machine has been introduced without authorization.
- The fixture does not import or shim around the frozen predecessor.
- No unauthorized Git history changes, publication, push, merge, or tag operation occurred.

The intended scope is deliberately small. Do not recommend moving packages or redesigning the architecture unless you find a concrete blocking violation.

## 4. Scientific contract: verify against the stated problem

The research question is:

> Under a specified class of admissible Lemaître–Tolman–Bondi cosmologies, what can a past-light-cone distance observation \(D_A(z)\) determine about present-day Buchert backreaction \(Q_{\mathcal D}(t_0)\) on a specified physical comoving domain?

The main non-identifiability claim remains open.

Required status conventions:

- `ZEH-Q-01`: literature claim requiring verification.
- `ZEH-Q-02`: candidate construction — incomplete.
- `ZEH-Q-03`: open conjecture.
- `ZEH-Q-04`: deferred.

Verify that no executable artifact, comment, README, manifest, or test silently upgrades Q-03 to an established theorem.

Check these mathematical conventions directly against the code:

**Radial gauge**

\[
M(r)=\frac{r^3}{2},
\qquad
\frac{dM}{dr}=\frac{3r^2}{2}.
\]

The gauge is \(M(r)=r^3/2\), not \(r^{3/2}\). Check that the stored input expression, differentiation target, independent expectation, parameter identity, relation, theorem conclusion, and tests agree.

**Angular-diameter distance**

\[
D_A^*(z)=
\frac{2[1-(1+z)^{-1/2}]}{1+z}.
\]

The first three nonzero coefficients around \(z=0\) are

\[
1,\qquad -\frac74,\qquad \frac{19}{8}.
\]

Independently verify the series calculation and confirm the stored rational artifacts are connected to the correct series orders.

**EdS vertex profile**

\[
Z_0(r)=(1-r/2)^{-2},
\qquad z(r)=Z_0(r)-1.
\]

The first three coefficients of \(z(r)\) are \(1,\frac34,\frac12\). Verify the stored coefficient-to-order mapping and the test's independent expansion. The \(z_3=1/2+2\beta/3\) expression is only a candidate recursion; this fixture must not certify it as a general result.

**EdS cone identity**

The stored reference expressions are constructed from

\[
u=1-\frac r2,\quad V_0=\frac r u,\quad
Q_0=\frac1u,\quad R_{c0}=ru^2,\quad P_0=u^2.
\]

The checked identity is

\[
2V_0Q_0=
\frac{3r^2}{R_{c0}}-
\frac{r^3P_0}{R_{c0}^{\,2}}.
\]

Verify that the test decodes the actual stored expressions and uses those decoded expressions in the rational evaluator. A test that rebuilds the equations independently but never reads the stored artifacts does not establish their correctness.

For every mathematics check, identify its actual evidential scope: exact algebraic argument, structural proof for a restricted expression form, finite-sample corroboration, or unresolved candidate.

## 5. Adversarial review of `TestMPrimeStructureAllR`

This is a particularly important check because the implementation report presents it as the all-\(r\) derivative argument.

Read the complete implementation of the expression decoder, the declared-radial-parameter resolver, the monomial parser, exponent handling, coefficient accumulation, and the associated adversarial tests.

Determine whether the test really establishes

\[
M'(r)=\frac{3r^2}{2}
\quad\text{for every }r
\]

for all expression trees that it accepts.

Check that:

1. The test inspects the actual stored derivative output.
2. It requires the intended sum-of-monomials structure rather than a sampled approximation.
3. The radial variable is linked to the correct declaration and parameter identity, not merely a display name.
4. Every accepted nonzero term has the required total degree.
5. Exact rational coefficients are accumulated correctly and the degree-two coefficient total equals \(3/2\).
6. Zero-coefficient residues are handled safely, including at \(r=0\).
7. Exponents are exact non-negative integers and there is no lossy conversion or overflow in parsing exponents or accumulating total degree.
8. Unsupported AST nodes, non-monomial factors, mismatched PIDs, fractional exponents, and negative exponents fail closed.
9. The adversarial test cases actually invoke the production structural-checking function and verify the expected rejection behavior.

Do not require a general polynomial algebra system. Evaluate whether this restricted structural argument is sound for the exact expression class it accepts.

`TestMPrimePointwise` is supplementary finite-sample corroboration, not the all-\(r\) proof. Confirm that documentation preserves that distinction.

## 6. Review the theta and sigma constructions

The intended EdS fragment is

\[
\theta=H+2H,\qquad
\sigma^2=\frac13(H-H)^2.
\]

Check the decoded AST structures directly.

For theta, verify the correct root and child structures, exact coefficient, and sameness of the two stored `H` operands according to the live PhysMath identity semantics.

For sigma, verify the coefficient, power, subtraction, and matching symbol operands.

The fixture's `H` is an ephemeral symbol. Do not claim that byte-identical ephemeral symbols establish the stronger identity semantics of declaration-bound mathematical variables. The documentation should say what is actually established.

Check that:

- `ThetaCanon` is linked to the correct canonicalization derivation, input, output, rule, and result.
- The represented sigma expression is not falsely included in the executed derivation inventory.
- No test claims that syntactic cancellation alone executes spatial averaging or proves the full Buchert baseline.

Determine whether any defect is material to the intended conditional EdS reference fragment or is only a documentation/strength-of-claim issue.

## 7. Review cone and vertex checks

Inspect whether the cone tests decode the actual stored `ConeRefs` and validate them rather than checking only independently reconstructed Go arithmetic.

Review:

- AST shape and allowed factors.
- Exact rational coefficients and powers.
- Bound parameter identity for the radial variable.
- The independent evaluator's accepted language and failure behavior.
- Same-display-name/different-identity cases.
- Negative controls for the wrong radial power and wrong coefficient.
- The vertex series coefficient artifacts and explicit order mapping.
- Whether every finite-sample check is described as corroboration rather than universal proof.

The independent evaluator is allowed to be small. It must simply be honest and adequate for the expression subset it supports. Do not demand general symbolic equivalence or a new Math primitive.

## 8. Review assumptions and `Fixture.Verify()`

The intended production verification path checks the actual fixture, including `PhysThm`, `EqGauge`, and their stored representations.

Verify that the tests mutate the live fixture and call `Fixture.Verify()`, instead of relying on a test-local duplicate checker.

Inspect whether the checks reject:

- Missing required assumptions.
- Dangling references.
- Wrong-family references.
- Same-family substitutions, particularly replacing `ltb_gauge` with `ltb_target`.
- Incorrect required-assumption sets or duplicate/missing identities.
- A mismatch between an in-memory `PhysicalTheorem`/`PhysicalEquation` and the corresponding stored artifact bytes.
- Changes to required identities that leave all references resolvable.

The intended exact required assumption set for the executed gauge fragment is `ltb_gauge` plus `ltb_regime`, with order-independent comparison and identity-based membership.

Determine whether the implementation enforces the stated requirement through the actual production path and existing APIs.

If some aspect cannot be enforced with available APIs, check that the limitation is documented precisely. Do not treat a broad artifact-family check as proof of exact semantic identity.

## 9. Review the derivation inventory and replay

Inspect each derivation in the fixture's declared evidence inventory.

Verify, entry by entry, the expected:

- Producer namespace and rule ID.
- Ordered input references.
- Conditions.
- Parameter bytes and derivative order where applicable.
- Output reference and result references.
- Correspondence to the intended fixture artifact.

In particular, verify the relationships:

- Differentiation input → `MRef`, declared radial function, and `MPrimeRef`.
- Canonicalization input → `ThetaRef` and output → `ThetaCanon`.
- Stored hand golden → equality relation → theorem conclusion gate.
- Every executed derivation claimed by the fixture → inventory entry → replay.
- Represented-only expressions → excluded from the executed evidence inventory.

Check negative mutations of derivation rules, inputs, and outputs through the actual replay or verification path.

Replay success alone does not establish that the derivation proves Q-03. The review must preserve that distinction.

## 10. Review the manifest, README, and claim-state boundary

Confirm that manifest tests pin the intended claims and the seven unresolved proof obligations, O1–O7, and that the written documentation agrees with the live behavior.

Verify that the current evidence and limitations are stated accurately:

- Spatial averaging and its volume measure are represented-only, not executed.
- The perturbative \(Q_2\) functional and off-cone extension remain unresolved or unsupported.
- There is no admissible pair of distance-matching models with distinct \(Q_{\mathcal D}\) established in this slice.
- No empirical result is claimed.
- The status lives in manifest/README metadata; `PhysicalTheorem` has no status field.
- `CheckClaimPromotion` only checks metadata/evidence-inventory consistency to its documented extent.
- Evidence being in the inventory is not proof that it is relevant to the claim being promoted.
- `Verify()` validates its implemented checks; it does not prove scientific truth.

Do not require a new status state machine or artifact schema.

## 11. Run the tests and check repository safety

Run the applicable formatting, build, vet, package tests, and full `phys-lib` suite if the workspace is available.

At minimum, verify the reported results for:

- `go vet` and formatting.
- `go test ./gr/ltb/...`.
- `go test ./...` from the `phys-lib` module root.
- Any additional checks directly needed to reproduce an alleged defect.

Record the exact commands, exit statuses, and material failures. Distinguish executed tests from tests merely inspected.

If execution is impossible, state precisely why. Do not claim the suite passed based only on the supplied report.

Recheck `git status --short --untracked-files=all`, tracked and staged diffs, and the contents of all untracked package files. Confirm frozen repositories are untouched.

Do not alter the tree during this review.

## 12. Required report

Use this format:

### A. Verdict

`PASS` or `REVISE`, with a concise explanation of whether any structural blocker remains.

### B. Structural blockers

For each blocker, provide:

- Severity.
- Exact file and function/test.
- The material defect.
- A reproducible counterexample or explanation of the invalid pass path.
- Why it affects logical correctness, intended semantics, or claimed evidence.
- The smallest recommended fix.

If there are no structural blockers, state that explicitly.

### C. Non-blocking observations

List only meaningful optional improvements. Do not disguise nitpicks as blockers.

### D. Verification performed

List actual commands and results, and separate independent execution from claims in the existing completion report.

### E. Commit-scope safety

Identify all changed, staged, and untracked files relevant to the proposed commit. Confirm whether any unauthorized or out-of-scope changes were found.

### F. Scientific status

Explicitly confirm that Q-03 remains an open conjecture and that the reviewed code does not establish the LTB non-identifiability theorem.

## Final instruction

Prioritize soundness over volume. Attack the implementation with malformed artifacts, changed references, incorrect expressions, wrong parameter identities, and misleading evidence claims. Do not accept comments as proof that the code does what they say.

At the same time, apply the agreed minimum passing standard: minor issues that do not undermine the derivation's core logic, assumptions, evidence, or scientific meaning must not block acceptance.

The desired outcome is an independent, decision-useful review before commit—not a new planning phase, not a redesign, and not an open-ended list of speculative improvements.