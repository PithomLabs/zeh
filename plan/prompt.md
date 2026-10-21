# ZEH paper — scope proposal and next research task

My recommendation is to scope the paper before authorizing ZEH-6. We have enough information to define a bounded scientific question, but we should not yet pretend that we know which publishable result the mathematics will deliver.

The paper should investigate one central problem: the relationship between spatially averaged kinematical backreaction and past-light-cone observables in Lemaître–Tolman–Bondi (LTB) cosmology.

The goal is not to prove that backreaction explains cosmic acceleration, construct a Theory of Everything, or build a complete physics-research platform. The goal is to establish one defensible result that improves our understanding of what light-cone observations can tell us about spatially averaged inhomogeneous cosmology.

## 1. Proposed paper scope

WORKING TITLE

# Spatial Backreaction and Light-Cone Observables in LTB Cosmology: An Identifiability Analysis

Provisional title; revise after the literature and novelty audit.

Central research question

Under clearly specified LTB assumptions, what can past-light-cone observations establish about the present-day Buchert kinematical backreaction \\(Q\_{\mathcal D}(t_0)\\) on a specified spatial domain? Under what additional restrictions, if any, can that quantity be reconstructed or independently constrained?

Minimum intended contribution

A mathematically rigorous result about identifiability, reconstruction, or the limits of reconstruction, supported by a coherent derivation and a careful comparison with existing literature.

The paper must remain open to three possible outcomes. We should not choose a preferred answer before doing the research.

Outcome A — An identifiability result

Establish whether the same specified distance–redshift relation can correspond to admissible LTB models with different present-day \\(Q\_{\mathcal D}\\), or establish a theorem describing the conditions under which that ambiguity exists.

Outcome B — A conditional reconstruction result

Establish what additional assumptions or independent observables permit reconstruction of \\(Q\_{\mathcal D}\\), and exactly which conclusions depend on those restrictions.

Outcome C — A stronger relation or meaningful no-go result

Derive a new relation with demonstrable predictive content beyond standard metric reconstruction, or prove a precise limitation on such a relation within the stated model class. This outcome is optional, not a requirement to force.

A rigorous negative result can be the paper's contribution. We must not manufacture a stronger result merely to make the paper seem more novel.

## 2. The novelty risk we must resolve first

An initial literature check reveals an important reason not to launch directly into new derivations.

- LTB inverse problems are established research. Yoo's 2010 paper discusses the two physical functional degrees of freedom, conditions for regular inverse solutions, and how to solve the simultaneous-big-bang inverse problem for a given \\(D_A(z)\\). Therefore, neither the general function-count argument nor the mere existence of a restricted inversion should be presented as novel.&#x20;

  [image](https://www.google.com/s2/favicons?domain=https://academic.oup.com\&sz=32)

  OUP Academic

- The relationship between LTB spatial backreaction and geometry has substantial prior art. Sussman's analytical work studies Buchert backreaction, spatial curvature, and conditions under which the backreaction is positive. We must not mistake a known sign condition or identity for a new result.&#x20;

  [image](https://www.google.com/s2/favicons?domain=https://arxiv.org\&sz=32)

  arXiv

- The wider spatial-average/light-cone problem is also established. Buchert, van Elst, and Heinesen developed a formalism for averaging inhomogeneous dust cosmologies on past null cones.&#x20;

  [image](https://www.google.com/s2/favicons?domain=https://arxiv.org\&sz=32)

  arXiv

- There is especially relevant recent work. Heinesen and Clifton's 2026 paper develops observational tests for distinguishing cosmological model classes; Koksbang's 2026 paper applies a combination of redshift, distance, and expansion-rate observables to constrain cosmic backreaction. The precise overlap with our LTB-specific target must be established rather than assumed.&#x20;

  [image](https://www.google.com/s2/favicons?domain=https://inspirehep.net\&sz=32)

  INSPIRE

  +1



Consequently, the potentially meaningful contribution is narrower than “connect backreaction with light-cone observables.” It may be a rigorous \\(Q\_{\mathcal D}\\)-specific identifiability result, a mathematically nontrivial conditional reconstruction result, or a demonstrable limitation of an existing method.

We should abandon that particular contribution if the literature shows it is already established and we cannot identify a meaningful extension. Our objective is a credible paper, not protecting our initial hypothesis.

## 3. Scope boundaries to lock

## In scope

- A central observer in exact LTB dust cosmology under classical GR, with \\(\Lambda=0\\) and the radial gauge \\(M(r)=r^3/2\\).
- The Buchert kinematical backreaction \\(Q\_{\mathcal D}\\), evaluated on a specified comoving dust slice and a clearly defined physical domain.
- The information content of a specified light-cone observable set, beginning with \\(D_A(z)\\) and adding independent observables only if required by the research question.
- The distinction between general LTB and explicitly restricted subclasses, including the simultaneous-bang case.
- Analytical derivations as the default, with targeted numerical work only if an essential existence, uniqueness, or counterexample question cannot be settled adequately on paper.

## Out of scope for this paper

- Quantum gravity, the Planck regime, the Theory of Everything, and explanations of the origin of \\(\Lambda\\).
- Multi-center LTB ensembles, off-center observers, non-dust matter, or nonzero \\(\Lambda\\).
- Real-survey data analysis, observational-error propagation, and large simulation campaigns unless a specific necessity is demonstrated later.
- Building PhysTrace features, implementing every equation in Go, or turning the article into a software-methodology paper.
- Claims about the cause of cosmic acceleration that are not established by the derivation.

Regime and scale: late-time classical GR, irrotational pressureless dust. The existing synthetic EdS benchmark over \\(0\leq z\leq1\\), with a present-day \\(100\\)-Mpc domain, remains a useful controlled example. It should be retained only to the extent that it helps establish the paper's principal result; those specific numerical choices are not automatically fundamental to a general theorem.

## 4. The next task for the four research agents

I recommend a new gate, ZEH-PAPER-SCOPE-1: Literature, Novelty, and Contribution Lock.

This comes before ZEH-6. Its deliverable is a completed paper scope and a precise research question—not a numerical reconstruction. Each worker gets one bounded assignment so they contribute complementary evidence instead of producing four overlapping essays.

### Common instructions for all four agents

Use these instructions for every assignment below.

# ZEH-PAPER-SCOPE-1: Literature, Novelty, and Contribution Lock

## Mission

Help scope a credible physics paper on the identifiability or reconstruction of Buchert kinematical backreaction from past-light-cone observations in LTB cosmology.

The ultimate goal is a meaningful scientific contribution about Nature, potentially a new derivation, equation, theorem, mathematical map, constraint, or rigorously established negative result. The minimum deliverable is a coherent paper-level contribution, not merely a benchmark, literature summary, or software artifact.

## Research philosophy

1. Allow intuition, hunches, conjectures, and unconventional mathematical avenues to be explored freely.
2. Prefer pen-and-paper mathematics and logical derivation when establishing claims.
3. Treat numerical computation and simulation as last resorts, reserved for questions that analytical reasoning cannot adequately settle or for a specifically justified check.
4. Do not mistake formal elegance, function counting, a plausible narrative, or a known identity for a new scientific result.
5. Distinguish exploratory conjectures, derived claims, established results, and unresolved questions. Never promote a result beyond its evidence.

## Candidate research question

Within central-observer LTB dust cosmology, after explicitly fixing the radial gauge, model assumptions, foliation, domain, and observable set, does the available past-light-cone information determine the present-day Buchert kinematical backreaction Q_D(t0)? What can be established analytically in general LTB and under an explicitly restricted subclass such as simultaneous bang?

This is a candidate question, not an assumed novel contribution. Refine or reject it if the literature or mathematical analysis warrants doing so.

## Fixed starting assumptions

Use classical GR with irrotational pressureless dust, Lambda = 0, c = G = 1, and the gauge M(r) = r^3/2 as the initial research fixture.

Define Q_D on a stated comoving dust slice and a clearly specified physical spatial domain. Distinguish the physical domain from its coordinate boundary.

The existing EdS distance-redshift target over 0 <= z <= 1 and the 100-Mpc illustrative averaging domain may serve as a controlled example. They are not mandatory ingredients of a general theorem.

Begin with D_A(z) as the sole observational input. Introduce additional observables only when justified by the mathematical question and distinguish inputs used for reconstruction from genuinely independent predictions.

## Literature and novelty obligations

Inspect the primary literature, including relevant LTB inverse-problem work, Buchert averaging, LTB backreaction, past-null-cone averaging, observational consistency tests, and recent work on observable constraints on cosmic backreaction.

Check relevant publications and preprints available as of 16 October 2026.

For every proposed contribution, identify:

- Closest prior result and precise source.
- What the prior work actually proves.
- What it leaves unresolved, if anything.
- The exact proposed extension or difference.
- Why that difference matters scientifically.

Cite sources accurately. Do not infer novelty from not finding a paper with identical wording. Do not call a result new until the closest prior work has been compared directly.

## Scope-control rules

Choose one primary scientific question and one principal contribution. State explicit exclusions and a stopping condition.

Do not expand into a Theory of Everything, a survey-analysis project, a software-engineering paper, a multi-center cosmological model, or a broad review of every backreaction approach.

Do not begin the ZEH-6 numerical reconstruction during this task. Analytical reasoning and targeted literature review are permitted.

## Required deliverable

Produce a paper-scope recommendation containing:

1. Recommended provisional title.
2. One-sentence primary research question.
3. The research gap, supported by comparison with primary literature.
4. One principal candidate contribution, clearly labeled conjectural until established.
5. The minimum mathematical obligations needed to establish it.
6. Relevant assumptions, physical regime, scale, domain, foliation, and observable set.
7. Explicit claims the paper will not make.
8. Out-of-scope topics and a stopping condition.
9. A proposed paper outline.
10. A go / revise / stop recommendation for proceeding to ZEH-6.

If no defensible novelty remains, say so and recommend the smallest scientifically meaningful alternative. Do not manufacture a novel result to satisfy the assignment.

Do not provide invented derivations, numerical results, execution claims, or bibliography entries. Preserve unresolved questions explicitly.

### Agent-specific assignments

Send the common instructions above together with the corresponding assignment.

## DeepSeek — literature and novelty audit

Primary responsibility: establish what is already known.

Identify the closest primary papers on LTB inverse problems, simultaneous-bang reconstruction, Buchert \\(Q\_{\mathcal D}\\), and observable backreaction constraints. Build a claim-by-claim prior-art table, especially for the exact proposition that \\(D_A(z)\\) may or may not determine \\(Q\_{\mathcal D}(t_0)\\). Identify the smallest defensible literature gap, if one exists. Give full citations and links, and distinguish direct evidence from inference.

Success criterion: a defensible novelty boundary, not a large bibliography.

## Gemini — pen-and-paper contribution analysis

Primary responsibility: find the smallest meaningful mathematical result.

Without implementing a numerical solver, formulate the sharpest candidate proposition about the identifiability of \\(Q\_{\mathcal D}\\). List the assumptions and proof obligations. Determine whether the general-LTB ambiguity, a restricted uniqueness result, or a conditional reconstruction statement could be established analytically. Separate what follows from equations already known from what would require a new proof. Do not assume that function counting proves nonuniqueness of \\(Q\_{\mathcal D}\\).

Success criterion: a precisely stated result that is plausibly provable, or a clear explanation of the mathematical obstacle.

## Google — adversarial scope and novelty review

Primary responsibility: try to invalidate the proposed paper before we invest further.

Attack the candidate contribution as a skeptical referee. Search for prior work that already proves the same result, expose hidden assumptions, identify when the physical domain or foliation makes a comparison ambiguous, and test whether proposed conclusions really follow from the observable set. Reject any attempt to equate common-metric consistency with a new predictive law. Recommend the narrowest viable scope and specify what would cause the paper idea to be abandoned.

Success criterion: identify the strongest objections and a defensible response—or recommend stopping.

## Qwen — paper architecture and scope lock

Primary responsibility: translate the scientific conclusion into a bounded manuscript plan.

Propose an arXiv-style paper structure centered on one principal contribution. For every planned section, specify the scientific question it serves, the result it must establish, and the evidence needed. Separate indispensable material from optional extensions. Define the paper's claim register, explicit exclusions, minimum deliverable, and stopping condition. Do not add a new research direction unless it is necessary to establish the central result.

Success criterion: a manuscript plan that cannot quietly expand into multiple papers or a software project.

## 5. How I will adjudicate the four outputs

As Research Director, I will consolidate the reports claim by claim—not by majority vote—and make one decision:

- GO: The literature gap is defensible, the primary question is precise, and there is a plausible route to one meaningful mathematical result. Proceed to the corresponding analytical research task.
- REVISE: The general question remains worthwhile, but the scope or candidate contribution needs sharpening before derivation begins.
- STOP / REFRAME: The proposed result is already known, or the remaining work would not provide sufficient scientific value. Select the smallest worthwhile alternative rather than forcing novelty.

The acceptance criterion is that we finish this gate with one paper question, one principal contribution target, explicit boundaries, and clear mathematical proof obligations.

That prevents scope creep at its source: we decide what scientific knowledge the paper is meant to establish before spending effort on the derivation, computation, or infrastructure.
