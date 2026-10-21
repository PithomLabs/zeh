# Plan3 — ZEH/LTB Research Workflow Reference Implementation in Phys

## 1. Mission

Implement a small, complete, auditable reference case demonstrating how the Phys infrastructure can formalize a real physics research workflow, from problem definition and assumptions through hypotheses, mathematical representations, derivations, proof obligations, evidence, limitations, and scientific status.

Working title: *Spatial Backreaction and Light-Cone Observables in LTB Cosmology: An Identifiability Analysis.*

This is not a request to solve the entire research problem, build a generic research-management platform, or claim a publishable discovery.

As of the latest scientific review, we have a defined research question, a candidate mathematical construction, partial reasoning, and unresolved proof obligations. We do **not** yet have a novel central theorem that has been independently verified and is ready for a physics-paper submission. The implementation must faithfully encode this reality.

## 2. Reconnaissance (done)

- Read `zeh/docs/plan2_*.md`, `prompt2.md`, `plan2_review.md`, `plan2_status.md`.
- Read `phys-system/AGENTS.md`, `DERIVATION_SPEC_GUIDELINES.md` (normative), `GUIDELINES.md` (additive).
- Inspected live `phys-lib/gr`, `phys-lib/bohm/minisuperspace`, `phys-math`, `phys-artifact`, `phys-trace`.
- Converged verdict: framework + Buchert `Q_D` + EdS control usable; cone system + vertex series partially derived; Lemma A, Lemma B, exact family, remainder control, prior-art audit open. Strongest source: `plan2_z.md`.

## 3. Frozen-system boundary

`phys` and `phys-gr` frozen — no modifications, no imports, no shims. New work in `phys-artifact` / `phys-math` / `phys-lib/gr` / `PhysTrace` / `phys-system` per live architecture.

## 4. Growth gate

No new primitive/operation/family/abstraction without: real need, inexpressibility, correct layer, precise semantics/validation/failure/tests, reusability or justified GR scope, no frozen violation. Default: narrow slice on existing APIs; document gaps.

## 5. Build slice

Coherent artifact in correct active package: problem, assumptions, claims (Q-01 premise, Q-02 conditional, Q-03 open, Q-04 deferred), obligations O1–O7 unresolved with stable IDs, derivations with premises/steps/provenance/limits, evidence by class, evaluation of what checks do and do not prove. Positive reference derivation only: homogeneous EdS `Q_D=0`, iff faithfully supported.

## 6. Verification

Malformed metadata rejected; premise linkage; Q-03 stays unresolved; decode/validate/replay; independent goldens + anti-goldens; stale-evidence detection; `Verify()` coverage; executed-vs-unproved boundary; determinism; no legacy regression.

## 7. Scope

Do not claim theorem proved; invent outputs/citations; claim novelty pre-audit; build generic ontology; add unsupported rules; conflate math with truth; modify frozen systems; publish without authorization.

## 8. Open decisions

Package path (`gr/ltb/` vs `gr/zeh/`), Q-04 exclusion, Lemma B scope, new Math primitives vs document-only gaps.

Success = auditable reference without confusing formalization with discovery.
