### A. Verdict
PASS. The `TagPow` guard in `evalRat` (lines 268-307) is sound: integer check before any narrowing (`IsInt()` at 277), `IsInt64()` at 288 rejects out-of-range values before `Int64()` conversion (line 294), absolute-value comparison against `maxEvalExp = 1024` (line 291) rejects oversized and `MinInt64` exponents before negation or looping (lines 302-306), and zero-to-negative-power remains fail-closed. Tests (`TestEvaluatorExponentBounds`, line 351) cover nested oversized (`10^30`), `MinInt64`, billion-scale (`10^9`), positive controls (`0,1,2,3,-2`), and zero-negative-power. No structural blocker.

### B. Structural blockers
None. The guard sequence is:
1. `exp.IsInt()` → non-integer rejected.
2. `num.IsInt64()` → out-of-int64-range rejected before any `Int64()` call.
3. `Abs(num) > maxEvalExp` (1024) → oversized / MinInt64 rejected before negation or loop.
4. `n := num.Int64()` → safe because bounded above by 1024 and passed `IsInt64()`.
5. `n < 0` → zero-base rejected; `b.Inv(b)` and `n = -n` safe because `|n| <= 1024`.
6. Loop `for i := int64(0); i < n; i++` bounded by 1024 iterations.
No overflow, narrowing, or hang path remains.

### C. Optional observations
- `ARCHITECTURE.png` remains an unrelated untracked file at workspace root; it does not affect this review but should be excluded from any commit.
- The `evalRat` comment clearly documents `maxEvalExp` as an oracle implementation limit, not a mathematical restriction. This is accurate.
- No new architecture, frozen-system changes, or scientific claims are introduced.

### D. Verification
- `gofmt -l gr/ltb/protocol/derivation_test.go`: clean.
- `go vet ./gr/ltb/protocol/`: clean.
- `go test ./gr/ltb/protocol/... -run 'TestEvaluatorExponentBounds|TestEvaluatorSanity|TestMPrimeStructureAllR|TestMonomialPartsAdversarial' -v`: PASS (4/4).
- `go test ./gr/ltb/protocol/... -v`: PASS (all 17 tests).
- `go test ./gr/ltb/... ./...`: full module suite PASS.
- `git status --short --untracked-files=all`: no tracked/staged modifications; frozen repos untouched.
- Source inspection confirms `evalRat` guard order (integer → IsInt64 → Abs-bound → Int64 → loop) matches the described safe sequence.

### E. Scope and scientific status
- Change is confined to `gr/ltb/protocol/derivation_test.go`; no tracked files modified; `phys` and `phys-gr` untouched.
- `ZEH-Q-03` remains an open conjecture; the exponent-safety guard establishes no physics result, introduces no theorem artifact, and does not alter claim status.
