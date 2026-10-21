# Plan3 Implementation Report — ZEH/LTB Research-Workflow Reference in Phys

## 1. Changed files (all new, under `phys-lib/gr/ltb/`)

- `doc.go` — package status discipline (executed vs represented vs open).
- `fixture.go` — `Build()` + `Verify()`: 7 LTB assumptions, bound-`r` identity with declaring function, executed `dM/dr` fragment with stored EQ relation + math/phys-gr theorem wrappers, EdS theta/sigma constructions, hand-recorded `D_A*` coefficients, EdS cone structured expressions, 2-entry derivation evidence inventory with replay, assumption target-check resolution.
- `claim.go` — `CheckClaimPromotion` metadata/evidence consistency check + status constants. No artifact schema change, no state machine.
- `manifest.json` — strict metadata: regime, conventions (`M(r)=r^3/2`, `R=D_A`, central norm), claims Q-01…Q-04 with final statuses, obligations O1–O7 with blocks + discharge evidence, assumptions, verification split, 5 limitations, 2 background literature entries (no pages/volumes invented).
- `README.md` — question, executed-vs-represented split, all four hand derivations written out, claim register, layout.
- `manifest_test.go` — strict-parse (unknown fields rejected), header/entry-point/provenance pins, exact status pins, O1–O7 completeness, limitation pins.
- `protocol/derivation_test.go` — 13 tests (see §7).

## 2. Research workflow demonstrated

Problem → 7 typed assumptions → 4 claims with statuses → math constructions → 2 replayed derivations → O1–O7 obligations → evidence by class (replayed rules / rational corroboration / metadata) → limitations. Q-03 has **no theorem artifact**; its openness is structural, not just a label.

## 3. Reference derivation

Executed: `dM/dr = 3r²/2` via DIFFERENTIATE-001 (replayed) + CANON on EdS theta (replayed) + theorem conclusion gate binding output to hand golden. Checking the engine's uncollected output form against `3r²/2` canonically **failed honestly** — resolved per Lesson 3 via an independent test-side exact-rational evaluator over the stored artifact at 5 sample points. `D_A*` coefficients (1, −7/4, 19/8) and cone identity corroborated by independent mechanical recomputation; `z_3` slope kept candidate-only.

## 4. Scientific status

Q-01 literature-claim-requiring-verification; Q-02 candidate-construction-incomplete; **Q-03 open conjecture**; Q-04 deferred. The LTB theorem is not proved.

## 5. Growth-gate decisions

No new primitives, families, rules, or namespaces. Averaging/integration stays represented-only (documented gap). Durable `phys-gr` namespace reused for the subpackage; frozen `phys-gr` untouched. `plan2_z.md` treated as lead: every reused coefficient re-derived by hand.

## 6. Verification evidence (all ran)

- `go build ./...` — clean; `go vet ./gr/ltb/...` — clean; `gofmt -l` — clean.
- `go test ./gr/ltb/...` — 4/4 manifest tests + 13/13 protocol tests pass:
  TestManifestContract, TestManifestClaimStatuses, TestManifestObligations, TestManifestLimitationsHonest,
  TestFixtureVerify, TestDerivationInventory, TestCorruptedOutputFailsReplay, TestEvaluatorSanity,
  TestMPrimePointwise, TestGaugeAntiGolden, TestDAStarSeries, TestVertexCoefficients,
  TestConeIdentityRational, TestThetaStructure, TestAssumptionLinkage, TestClaimStateIntegrity,
  TestBuildDeterminism.
- `go test ./...` (phys-lib) — all packages pass, including `gr`, `gr/equivariance`, `gr/maxwellbox`, `bohm/minisuperspace`, conformance fixture2.

## 7. Independent and adversarial tests (all reject as required)

Corrupted replay output; `r^(3/2)` gauge confusion; 23/8 historical slip; `r³`-vs-`r²` golden confusion; substituted/dangling assumption refs; Q-03→proved without evidence; out-of-inventory evidence; unknown status; sigma-in-derivation (represented-only enforcement).

## 8. Limitations

Averaging unexecuted; status is metadata (`Verify` enforces linkage, not epistemics); series goldens are candidate-grade; no model pair; no empirical claims. All recorded in manifest + README.

## 9. Repository safety

`git status` clean in `phys`, `phys-gr`, `phys-math`, `phys-artifact`, `phys-trace`, `phys-system` (one pre-existing untracked `system.md` in phys-trace, not from this work). Only addition: `phys-lib/gr/ltb/`. No push/merge/tag/publication.

## 10. Assessment

A working, auditable reference implementation showing how Phys records real scientific research faithfully — from precise problem definition and explicit assumptions to conjectures, partial derivations, executable evidence, and unresolved proof obligations — without confusing formalization with discovery. ZEH-Q-03 remains open.
