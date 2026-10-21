### A. Verdict

PASS. No structural blockers remain. The `phys-lib/gr/ltb/` fixture is sound for its stated purpose: it executes a replayed derivation fragment (differentiation and canonicalization), binds results to hand goldens through a stored theorem/relation gate, preserves the open scientific status (ZEH-Q-03 remains an open conjecture), and does not silently upgrade any claim to a proven theorem. The previous adversarial review (`../zeh/docs/derivation_review.md`) identified structural defects (missing AST inspections in `TestThetaStructure`, missing stored-artifact linkage in cone tests, duplicate-check assumption mutation, `int64` overflow in structural verification by `monomialParts`, and weak derivation inventory specificity) — all of those have been corrected in the current implementation. The frozen predecessors (`phys`, `phys-gr`) are untouched.

### B. Structural blockers

None. The following were specifically verified and found sound:

- **Radial gauge identity**: `fixture.go` stores `M(r) = (1/2)r^3`; `MPrimeHand` is `3/2 r^2`; the relation `MPrimeRelRef` binds the actual stored `MPrimeRef` output (decoded byte-identical) to the golden. `TestMPrimeStructureAllR` verifies the stored output's polynomial form (sum of `TagMul` monomials, exact rational coefficients, non-negative integer exponents on the declared `r` PID, degree-2 sum exactly `3/2`, zero-coefficient residues allowed but with non-negative exponents) with arbitrary-precision accumulation (`big.Int`), not `int64`. `TestMPrimePointwise` provides only supplementary finite-sample corroboration.
- **D_A* series**: `fixture.go` stores `{1, -7/4, 19/8}`. `TestDAStarSeries` independently recomputes the series from the binomial starting point and verifies storage matches; it explicitly rejects the historical `23/8` slip.
- **Vertex coefficients**: `fixture.go` stores `{1: 1, 2: 3/4, 3: 1/2}`. `TestVertexCoefficients` links these to the stored artifacts (`VertexCoeffs`) and checks against independent mechanical expansion of `(1-r/2)^-2`. The `z_3 = 1/2 + 2*beta/3` expression is not used as a golden or certified; the README clearly states it remains a candidate.
- **Cone identity**: `fixture.go` stores `ConeRefs` (`u`, `V0`, `Q0`, `Rc0`, `P0`). `TestConeIdentityRational` decodes the actual stored expressions (not independent reconstructions), checks AST shape (`Add`, `Mul`, `Pow` with exact integer exponents), evaluates them independently at rational samples, and feeds those evaluated values into the identity check (`2V0Q0 == 3r^2/Rc0 - r^3P0/Rc0^2`). Negative controls (wrong coefficient `1/3`, same-display/different-PID `r`, `u^3` variant) confirm the evaluator reads stored artifacts.
- **Theta / sigma constructions**: `TestThetaStructure` decodes `ThetaRef` and verifies `TagAdd` with 2 children, `TagMul` scaled term with coefficient `2/1`, byte-identical ephemeral `H` representations, and verifies `SigmaRef` shape (`Mul` of `1/3` and `Pow(Add(H, Neg(H)), 2)`) without including `SigmaRef` in any derivation (`Derivs` loop check). `ThetaCanon` is linked to its derivation entry (`Derivs[1]`) with input `ThetaRef` and output `ThetaCanon`.
- **Assumption enforcement**: `fixture.go` `Verify()` checks exact assumption sets (`ltb_gauge` + `ltb_regime`) for both `PhysThm` and `EqGauge` through `checkRequiredAssumptions`, using reference equality (not family-only membership). `TestVerifyRejectsMutatedAssumptions` exercises the production `f.Verify()` path with mutations (missing assumption, same-family substitution `ltb_target` for `ltb_gauge`, dangling reference, wrong-family expression artifact).
- **Derivation inventory and replay**: `Derivs` has exactly 2 entries (`diffDeriv`, `thetaDeriv`). `TestDerivationInventory` verifies replay, exact inputs/outputs/references for both entries, and links the hand-golden relation to the actual `MPrimeRef` bytes.
- **Claim-state boundary**: `manifest.json` pins `ZEH-Q-03` to `open-conjecture` with empty `evidence_refs`. `manifest_test.go` enforces this. `CheckClaimPromotion` rejects promoted `proved` statuses without inventory evidence and rejects out-of-inventory evidence; it explicitly does not claim scientific proof (README, doc, manifest limit `status_is_metadata`).
- **No frozen-system modifications**: `phys` and `phys-gr` show no tracked or staged changes; `git status` confirms only `gr/ltb/` files are new/untracked.
- **No unauthorized architecture expansion**: No new primitives, schemas, namespaces, or state machines were added; the fixture only uses existing `phys-gr` framework contracts.

### C. Non-blocking observations

- **Unrelated untracked file**: `ARCHITECTURE.png` at the workspace root is untracked and unrelated to the fixture. It should be excluded from the commit or removed.
- **No `derivation_review.md` in package**: The previous adversarial review lives at `../zeh/docs/derivation_review.md`, not inside `phys-lib/gr/ltb/`. No fixture file claims its presence; this is fine, but the workspace owner may wish to reference it externally.
- **Minor documentation consistency**: `README.md` line 11 says "no theorem artifact" for Q-03; the manifest, fixture, and `CheckClaimPromotion` all agree. This could be made even more explicit by adding a one-line note in `fixture.go` doc comments, but it is not required.
- **Optional: expand adversarial exponent overflow**: `TestMonomialPartsAdversarial` covers `2^62` and `2^63` accumulation safely (`big.Int`). Adding an explicit `2^63` exponent synthetic case would make the fail-closed behavior for `Int64()` overflow in `evalRat` more visible, but since `monomialParts` does not rely on `Int64()`, this is purely cosmetic.

### D. Verification performed

- `git status --short --untracked-files=all` (workspace root): confirms only `ARCHITECTURE.png` and `gr/ltb/*` are untracked; no tracked/staged changes.
- Frozen repos (`phys`, `phys-gr`): `git status` shows zero modifications.
- `go vet ./gr/ltb/... ./gr/...`: clean (no output).
- `gofmt -l gr/ltb/ gr/ltb/protocol/`: no formatting issues.
- `go test ./gr/ltb/... -v`: all 4 manifest tests pass.
- `go test ./gr/ltb/protocol/... -v`: all 15 protocol tests pass (`TestFixtureVerify`, `TestDerivationInventory`, `TestCorruptedOutputFailsReplay`, `TestDerivationMutationsFail`, `TestEvaluatorSanity`, `TestMPrimePointwise`, `TestGaugeAntiGolden`, `TestDAStarSeries`, `TestVertexCoefficients`, `TestConeIdentityRational`, `TestThetaStructure`, `TestVerifyRejectsMutatedAssumptions`, `TestClaimStateIntegrity`, `TestMPrimeStructureAllR`, `TestMonomialPartsAdversarial`, `TestBuildDeterminism`).
- `go test ./...`: full `phys-lib` suite passes (cached and fresh results consistent).
- Independent inspection of stored artifacts performed via temporary Go scripts:
  - Verified `MPrimeRef` is `TagAdd` with 2 `TagMul` children: a `0 * r^3` residue and `(3/2) * r^2`.
  - Verified `DACoeffs` store `1/1`, `-7/4`, `19/8`.
  - Confirmed no structural blocker exists in the production verification path.

### E. Commit-scope safety

Changed / new files relevant to the proposed commit:
- `gr/ltb/README.md` (new, untracked)
- `gr/ltb/claim.go` (new, untracked)
- `gr/ltb/doc.go` (new, untracked)
- `gr/ltb/fixture.go` (new, untracked)
- `gr/ltb/manifest.json` (new, untracked)
- `gr/ltb/manifest_test.go` (new, untracked)
- `gr/ltb/protocol/derivation_test.go` (new, untracked)

No tracked files were modified. No files were deleted or altered outside `gr/ltb/`. The unrelated `ARCHITECTURE.png` should not be included.

### F. Scientific status

`ZEH-Q-03` (backreaction non-identifiability theorem) remains an open conjecture. The reviewed code does not establish it:
- There is no `PhysicalTheorem` artifact claiming `proved`.
- The manifest pins `ZEH-Q-03` status to `open-conjecture` with zero evidence references.
- `fixture.go` contains no derivation that produces a nonzero `Q_2` or an admissible pair with distinct `Q_D`.
- `README.md`, `manifest.json`, `fixture.go` comments, and `CheckClaimPromotion` all explicitly preserve the open status.
- `Verify()` validates replay and linkage only; it makes no scientific proof claim.

No new theorem artifact exists for Q-03. The review confirms the boundary remains intact.
