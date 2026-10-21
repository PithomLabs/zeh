## prompt

just to clarify, so in our case there is no derivation yet that is worthy of publishing as physics paper? if none, that is fine, this can serve as our reference implementation of formalizing whatever needs to be formalized in Phys (artifacts, derivations, conjectures, etc)

## answer

Yes—that is the correct assessment, with one important qualification.

As of our current ZEH/LTB research, we have not established a novel, independently verified result that I would responsibly call ready for submission as a physics paper. That is not a failure. It is an honest assessment of where the research stands.

## 1. Where the physics stands

For our proposed paper, “Spatial Backreaction and Light-Cone Observables in LTB Cosmology: An Identifiability Analysis,” we have a research question and a plausible route toward a result.

The central claim we want to investigate is whether two admissible LTB cosmologies can reproduce the same angular-diameter distance observations \\(D_A(z)\\) yet have different present-day Buchert backreaction \\(Q\_{\mathcal D}(t_0)\\) on the same specified physical domain.

But we have not yet established the decisive mathematical result: an admissible pair of models with identical target observations and provably different backreaction, or an equivalent rigorous identifiability theorem. Metric non-uniqueness alone does not establish backreaction non-identifiability.

So the current status is:

- Research question: defined.
- Candidate mathematical construction: proposed, but not fully verified.
- Main theorem: conjectural.
- Outstanding obligations: regularity at the observer, admissibility and off-cone extension, a nonzero backreaction variation, and control of the perturbative remainder.
- Novelty: still requires a serious prior-art audit.

These are meaningful research foundations, but we should not represent them as a completed physics result.

## 2. Why this is still an excellent reference case for Phys

I agree with your proposed direction. We should use this case to formalize scientific work at whatever stage it actually occupies, rather than waiting until we have a publishable theorem.

The reference implementation should demonstrate that Phys can represent the complete lifecycle of a scientific claim:

Source and scientific question

Paper, cited result, conjecture, or research question

Assumptions and formal representation

Quantities, domains, equations, conditions, and dependencies

Derivation path

Intermediate results, mathematical steps, proofs, and verification obligations

Conjecture path

Proposed claims, supporting arguments, counterarguments, and missing lemmas

Evidence and scientific status

Structural validation, executable checks, mathematical proof, physical interpretation, empirical evidence, and limitations—kept distinct

The crucial requirement is that a conjecture must remain a conjecture even when its representation validates and its tests pass. Likewise, a valid derivation must not silently become a claim of empirical confirmation.

Our ZEH/LTB case is particularly useful because it forces Phys to represent an unfinished theorem honestly: we have a precise target, a candidate construction, partial reasoning, and identifiable proof obligations, but not yet the final result.

## 3. What success looks like

We should maintain two distinct evaluation criteria.

Scientific success: Establish a novel, defensible result—or discover that the proposed result is false, already known, or requires narrower assumptions. Any of those outcomes can be scientifically valuable if handled rigorously.

Formalization success: Show that Phys can preserve the scientific meaning of the work, its assumptions, derivation dependencies, evidence, provenance, uncertainty, and unresolved obligations in a language-agnostic, auditable form.

The second does not depend on achieving the first. We can build a high-quality reference case without claiming to have solved the underlying physics.

That also gives us a way to test the infrastructure against more mature material: established derivations can serve as positive reference fixtures, while conjectures, incorrect derivations, missing assumptions, and incomplete proofs test whether the system catches unsupported claims.

One boundary remains important: we should not expand into a generic framework for every possible scientific artifact before we have a working end-to-end example. Start with the real ZEH/LTB claim and the artifacts it actually requires, formalize them faithfully, and let concrete gaps drive any necessary additions to PhysMath, PhysArtifact, or PhysLib. The separate coding agent handles that translation and implementation; the research work stays focused on the mathematics.

Bottom line: We do not yet have a completed novel physics result from this line of research. We do have a worthwhile reference case for demonstrating how Phys should formalize scientific knowledge—including unfinished and potentially false claims—without confusing formal validity with scientific truth. That is a legitimate milestone in its own right.
