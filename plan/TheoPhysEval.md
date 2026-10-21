## prompt

how does attached 2610.16733v1.pdf relate to our Phys infra?

## chatgpt

The attached paper, TheoPhysEval: Assessing AI agents at autonomous theoretical physics problem solving, is highly relevant to our Phys infrastructure. I see it as a potential evaluation layer built on top of Phys, not a replacement for Phys and not a reason to change the current ZEH/LTB implementation plan.

Its most important lesson for us is that solving a physics calculation, verifying a derivation, and conducting original physics research are different capabilities.

## 1. What TheoPhysEval contributes

The paper evaluates AI agents on 50 unpublished, research-level theoretical physics problems with verifiable answers. The problems require concrete calculations and adapting known techniques, but deliberately exclude major open research problems. The authors describe them as “turn-the-crank” research tasks.&#x20;

2610.16733v1.pdf



The benchmark's workflow often involves locating a paper, adapting its equations, performing symbolic or numerical calculations, and obtaining a checkable answer. Its grading primarily evaluates final answers rather than independently validating the full derivation chain.&#x20;

2610.16733v1.pdf

2610.16733v1.pdf



The authors explicitly distinguish this kind of problem-solving from choosing good research questions and constructing new physical theories. They argue that excellent calculation ability does not, by itself, establish autonomous research ability.&#x20;

2610.16733v1.pdf



That distinction closely matches the problem we are trying to solve with Phys.

## 2. How it maps to our Phys architecture

## Layer 1 — Phys formalizes the scientific work

PhysArtifact · PhysMath · PhysLib · PhysTrace

Represents source claims, assumptions, quantities, equations, derivations, dependencies, conditions, provenance, evidence, limitations, and unresolved conjectures.

Provides structured, auditable scientific artifacts

## Layer 2 — Verification checks the artifacts

Structural and semantic checks · independent goldens · replay · negative tests

Checks the mathematical operations and the relationships between premises, inputs, intermediate results, conclusions, and evidence, to the extent supported by the implementation.

Can support reproducible evaluation

## Layer 3 — Phys AI Evals evaluates agents and research workflows

Potential future capability, not part of the current required build

Evaluates whether an agent produces correct results, preserves assumptions, follows the derivation, rejects invalid alternatives, and accurately reports what has and has not been established.

The distinction between the layers matters. A benchmark can report that an agent gave the correct answer. Phys should help us inspect what that answer means, how it was obtained, which assumptions it depends on, and what the available evidence actually establishes.

Even a complete derivation replay would not automatically prove that the physical model is appropriate or that its conclusions agree with Nature.

## 3. What we should take from the paper

A. Make correctness independently checkable

Use well-defined problems with checkable results as positive fixtures. The existing `phys-lib/bohm/minisuperspace` work is a better precedent for our derivation layer than final-answer grading alone, because it checks intermediate expressions, derivation replay, incorrect paths, and limitations.

B. Treat the reference answer as something that must itself be audited

TheoPhysEval reports cases where expert review revealed errors in reference solutions that initially led to correct agent answers being marked wrong. It also discusses ambiguous conventions in some prompts.&#x20;

2610.16733v1.pdf

2610.16733v1.pdf



That directly supports our insistence on independently re-deriving the `plan2_z.md` coefficients and identities before turning them into goldens. Neither an agent's output nor a published reference is automatically authoritative.

C. Evaluate the research process, not just the final answer

A future Phys evaluation suite could check whether an agent preserved the problem's assumptions, used valid mathematical operations, maintained the provenance chain, detected incorrect derivations, and accurately described missing evidence.

These criteria extend beyond the final-answer evaluation described in TheoPhysEval. They are a proposed direction for us, not capabilities the paper demonstrates.

D. Keep problem selection separate from calculation

The authors emphasize that choosing the right question and adapting when a problem proves unsuitable remain important research skills.&#x20;

2610.16733v1.pdf



This reinforces our division of responsibility: research direction and mathematical judgment remain separate from the coding agent's job of translating approved work into structured artifacts and executable checks.

## 4. How this relates to our current ZEH/LTB work

Our current reference case deliberately spans two kinds of scientific work:

| Research artifact                        | What Phys should demonstrate                                                                                                                                               |
| ---------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Established EdS baseline                 | Record assumptions and represent the homogeneous result \\(Q\_{\mathcal D}=0\\), executing only the supported mathematics and documenting any missing averaging semantics. |
| Known derivation from minisuperspace     | Preserve structured inputs, ordered operations, intermediate results, independent checks, replay, and explicit limitations.                                                |
| ZEH-Q-01, literature claim               | Record the source and make verification of its scope and applicability explicit.                                                                                           |
| ZEH-Q-02, candidate construction         | Preserve its incomplete status and unresolved mathematical obligations.                                                                                                    |
| ZEH-Q-03, non-identifiability conjecture | Keep the theorem open until an admissible construction or equivalent proof genuinely discharges the obligations.                                                           |
| Future agent benchmark task              | Evaluate an agent against independently verified requirements and evidence appropriate to that task's scientific status.                                                   |

This is where Phys can go beyond a conventional question-and-answer benchmark. The system should not require every research artifact to have a known final answer before it can represent that artifact faithfully.

For an established calculation, an expected result may be available. For an open conjecture, the evaluation must focus on what can legitimately be checked—such as assumption consistency, valid derivation steps, counterexample handling, and honest reporting of unresolved obligations—without pretending there is a known correct final theorem.

Our current Phys AI Evals framework also keeps theoretical evaluation distinct from empirical truth: a theoretical result and its null-model comparison can be evaluated from formal assumptions and equations, while the Nature/Reality result remains unavailable until empirical evidence exists.

## 5. What I recommend we do now

Do not expand Plan3 to implement a TheoPhysEval-style benchmark yet. Keep the current implementation bounded.

The immediate objective remains a faithful ZEH/LTB research-workflow reference case in the new Phys architecture, respecting the frozen `phys` and `phys-gr` systems and the existing growth gate.

After that vertical slice works, TheoPhysEval can inform a separate evaluation roadmap with two complementary tracks:

- Known-answer evaluations: established derivations and concrete theoretical-physics calculations with independently verified expected results.
- Research-workflow evaluations: open problems where the agent is assessed on mathematical validity, evidence handling, adversarial robustness, and epistemic honesty—not on matching a nonexistent known answer.

The same infrastructure could support both, but their success criteria must remain distinct.

My conclusion: TheoPhysEval shows why we need strong AI physics evaluations. Phys is intended to provide the auditable scientific representation and verification foundation on which a more rigorous, derivation-aware evaluation system could be built. The paper complements our direction; it does not replace our research workflow or change the immediate build priorities.


## Z

# THEOPHYSEVAL AND THE PHYS INFRASTRUCTURE

The attached paper — *TheoPhysEval: Assessing AI agents at autonomous theoretical physics problem solving* (arXiv:2610.16733v1) — is not directly about your Phys infrastructure, but it is the closest published work to it, and its findings bear on every design decision you've been making. The relationship is best understood as: **the paper evaluates the engine your Phys infrastructure runs on.** Here is how the connections stack up.

## 1. The shared premise: verifiable answers

TheoPhysEval's core methodological move is the same one your ZEH-5 and ZEH-6A tasks made: convert research-level physics problems into forms with **numerical or symbolic answers that cannot be guessed**, so that grading is objective and automatable. The paper's Box 2 shows the canonical example — take a symbolic rate calculation, insert numerical values for all relevant and irrelevant physical quantities, and require a floating-point answer in a specific format. Your ZEH-6A does the same with its `AGENTS.md`/`manifest.json`/`protocol/derivation_test.go` structure and its "answer sheet" format.

**What the paper adds.** It demonstrates at scale (50 problems, 5 agents, two tracks) that this conversion works, and it documents the failure modes when it doesn't. The inverse problem (§1b) is the one problem no agent solved, and the paper's Appendix B explains why: the answer is a fractional delay differential equation that cannot be converted to a numerical answer without playing on the terms of the prompt. Your ZEH-6A ran into the same class of problem — the conjecture is not a number, it is a structural statement about a functional equation, and you correctly labeled it UNRESOLVED rather than forcing a numerical proxy.

**What your infrastructure adds.** Your `protocol/derivation_test.go` is a structural check on the derivation itself, not just the final answer. The paper's evaluation is answer-only ("automated and only based on the final answers," p. 2). Your Phys artifact specification requires the derivation to be traced, the status of each proposition to be labeled (established, derived, conditional, conjectural, unsupported, falsified), and the proof obligations to be listed. This is a strictly stronger standard than TheoPhysEval's, and the paper's discussion section implicitly concedes the gap: "the excellence of AI agents at problem solving does not immediately imply their all-round excellence at autonomous physics research."

## 2. The shared concern: category errors

TheoPhysEval's qualitative analysis observes that agents fail in characteristic ways:
- **Gemini and GLM used 5D formulas for a 4D problem** (§10d Page time) because they did not adapt the equation to the correct dimension.
- **Gemini, GLM, and DeepSeek evaluated geodesic lengths rather than minimal areas** on the isolated track — a category error about what the problem was asking for.
- **GLM asserted a problem was equivalent to another one** (§11f) without checking.
- **Opus used initial data from a reference paper that differed from the prompt's specified initial data** (§1c).

These are precisely the failures the Math Reality Check is designed to catch. The MRC's rule — "do not use constraints to claim that you have generated a physical mechanism, selected initial conditions, or predicted a fundamental constant unless an explicit derivation establishes that claim" — is a formalization of what Gemini, GLM, and DeepSeek did wrong. They imported formulas and assumptions from adjacent problems without verifying that the category of the problem was preserved.

**What the paper adds.** It quantifies the failure rate. Even the best agent (Astra) fails on the inverse problem and on three additional problems in the isolated track. The paper's finding that Astra initially appeared to fail on several problems, but that the *expert solutions* were later found to contain errors (p. 6), is a direct vindication of the MRC's discipline: the agent was right and the humans were wrong, because the agent followed the derivation and the humans did not.

**What your infrastructure adds.** Your ZEH-6A specifies the exact status classification (established, derived, conditional, conjectural, unsupported, falsified) and requires the artifact to record what remains unresolved. The paper's evaluation does not require this; it only checks the final answer. Your infrastructure would have caught the category errors earlier, because the status label would have forced the agent to say "I am treating this 5D formula as if it were 4D" before proceeding.

## 3. The shared problem: memorization vs. derivation

The paper's most striking quantitative finding is that agents show **only small accuracy changes when denied web search** (Astra: 98% realistic, 92% isolated; Opus: 92% both tracks). The paper concludes: "leading LLMs have effectively memorized large parts of the theoretical physics literature" (p. 1). The paper's Figure 4 shows that even without web access, Astra and Opus solve 46/50 problems each.

This is the same problem your ZEH-6A faced. You specified that the task is to "derive or falsify" a specific conjecture, not to look up a known answer. But the paper shows that a sufficiently capable agent may already have the relevant formulas memorized, which means the derivation may be reconstructed from memory rather than derived from the specified assumptions.

**What the paper adds.** It quantifies the memorization. The paper's Appendix C per-problem grades show which problems were solved on both tracks versus only one — the difference is small, confirming the memorization hypothesis. The paper also notes that "it would be impossible for a human to attempt §11f without looking up the text of the background paper mentioned there" (p. 7) — yet agents solve it on the isolated track. This is direct evidence that the agent is not reasoning from first principles.

**What your infrastructure adds.** Your ZEH-6A's specification of the fixed physical framework, gauge, domain, foliation, and regularity conditions is designed to make the problem *derivation-dependent*, not lookup-dependent. If the derivation is forced through specific assumptions, the agent cannot substitute a memorized formula from a different context. Your `protocol/derivation_test.go` structural checks — EdS limit, dimensional consistency, regularity, redshift formula — are specifically designed to catch substitutions that violate the stated assumptions. This is a stronger defense against memorization than TheoPhysEval's isolated track, because it tests the derivation path, not just the endpoint.

## 4. The shared limitation: taste and problem selection

The paper's discussion (Section V) makes an observation that is directly relevant to your Phys infrastructure:

> "At the moment, agents do not appear to have the same 'taste' in problems. We have observed that, when asked to come up with new problems, agents focus excessively on details that a human might find uninteresting."

And:

> "A good researcher can then find a related but simpler and equally interesting problem to solve. In our experience, current agents are not adept at dynamically switching direction in this manner."

This is the gap your Phys infrastructure is designed to fill. The MRC's central distinction — between what math can *derive* and what it can only *constrain* — is a formalization of "taste." It tells the agent when to stop: when the question has crossed from derivation into genesis, selection, or probability, and the honest answer is "no mechanism found." Your ZEH-6A's specification of the stopping condition and the explicit non-claims list is a direct implementation of this.

**What the paper adds.** It confirms that agents do not have this discipline natively. Astra, Opus, and Gemini all solved problems they were given, but none of them, when facing a problem they could not solve, found a related but simpler problem — they simply failed or produced no valid output. Your ZEH-6A would have required the agent to state the obstruction and identify the missing proof obligation, which is exactly the "switching direction" behavior the paper says is missing.

## 5. The direct overlap: Phys-compatible artifact

Your ZEH-6A specified a Phys-compatible artifact with:
- `AGENTS.md`
- `manifest.json`
- `protocol/derivation_test.go`

The TheoPhysEval paper used the Harbor framework, which is the same class of infrastructure: a containerized environment with fine-grained tool controls (web search on/off, local tools, time limits). The paper's Appendix A gives the full problem list, and the Hugging Face repository (RameshChandra1/TheoPhysEval) provides the task bundles.

The structural correspondence is direct:
- **Your `manifest.json`** ↔ **Harbor task configuration**
- **Your `protocol/derivation_test.go`** ↔ **Harbor's automated grader**
- **Your `AGENTS.md`** ↔ **The problem prompt**

**What the paper adds.** It provides a working implementation of the harness. If you want to run your ZEH-6A conjecture through an agent, the Harbor framework is the natural tool. The paper also provides evidence for which models and harnesses work best: Astra+Codex (98%), Opus+Claude Code (92%), Gemini+Antigravity (68%). Your choice of agent matters, and the paper's Table II–III gives token and cost data that would inform your resource planning.

## 6. The key divergence: what counts as a contribution

The paper is explicit that its problems are "turn-the-crank" research problems, not breakthroughs:

> "None of the problems in our dataset constitute breakthrough open problems. Solving them does not require great originality or the ability to construct new physical theories." (p. 3)

Your ZEH-6A is aimed at a different target: a **new theorem or a rigorously established negative result**. The paper's benchmark measures calculation ability; your infrastructure measures contribution ability. The paper itself acknowledges this gap: "the main aim of the field is to construct theories of the physical world. Second, it is necessary to ask the 'right' high-level questions of the theory. Third, it is necessary to convert these questions into concrete calculations." TheoPhysEval measures the third; your ZEH-6A measures the first two.

**What this means for your infrastructure.** TheoPhysEval is a benchmark for the calculation stage. Your Phys infrastructure is a framework for the full pipeline. The paper's findings are encouraging for the calculation stage — if Astra can solve 98% of research-level calculations autonomously, then the calculation bottleneck is largely solved. The bottleneck is now at the stage of problem selection, derivation strategy, and status classification — which is exactly where your MRC framework operates.

## 7. The implications for your current work

TheoPhysEval has four direct implications for your ZEH-6A execution:

**First, the calculation is not the hard part.** Astra can do the linearized LTB calculation, the functional equation, and the \(\delta Q_{\mathcal D}\) computation if the problem is stated as a verifiable calculation. The hard part is knowing *which* calculation to do and *when to stop*. Your ZEH-6A correctly identified the stopping point — the functional equation is the obstruction — and did not force a numerical answer.

**Second, the isolated track is the relevant one.** If you want to test whether the agent is deriving from your stated assumptions or recalling a formula from the literature, run the task in an isolated environment (no web search). The paper's finding that accuracy barely drops suggests the agent may be recalling, which would undermine the claim that the derivation is from your specified assumptions.

**Third, the structural checks matter.** Your `protocol/derivation_test.go` is a stronger check than the paper's final-answer grading. It catches category errors, dimensional errors, and assumption violations before they propagate to the final answer. The paper's qualitative analysis found exactly these errors in the weaker models; your infrastructure would catch them earlier.

**Fourth, the human is still in the loop.** The paper concludes: "human experts are necessary to guide current agents and to set directions" (p. 8). Your role in the ZEH-6A task is exactly this: you set the direction (the conjecture), specified the assumptions, and will adjudicate the verdict. The agent's role is to perform the calculation and report the status. The paper confirms this division of labor is currently necessary, and its quantitative findings suggest it may remain necessary for problem selection even as calculation becomes fully autonomous.

## 8. What a TheoPhysEval-style benchmark for your Phys infrastructure would look like

If you wanted to benchmark your Phys infrastructure the way TheoPhysEval benchmarks raw calculation, you would design problems that test:

1. **Status classification**: given a derivation with a hidden category error (e.g., a constraint treated as a generator), can the agent correctly label the claim as "unsupported" or "conjectural"?
2. **Obstruction identification**: given an unsolved problem, can the agent state the exact missing proof obligation rather than producing an unsupported claim?
3. **Assumption tracking**: given a derivation that silently imports an assumption from a different context, can the agent detect the import?
4. **Stopping condition**: given a problem that has crossed from derivation into genesis, can the agent recognize the crossing and stop?

These are the skills your MRC framework formalizes, and TheoPhysEval provides the benchmark infrastructure to test them. The paper's problems are the calculation layer; your problems would be the meta-cognitive layer. Both are necessary, and the paper's finding that calculation is largely solved makes the meta-cognitive layer the frontier.

## 9. The bottom line

TheoPhysEval is the infrastructure layer your Phys infrastructure runs on. It provides the harness (Harbor), the benchmark format (verifiable answers), the model evaluations (Astra > Opus > Gemini > DeepSeek > GLM), and the confirmation that calculation-level problems are largely solved. Your Phys infrastructure adds the layer above: the MRC discipline, the status classification, the stopping conditions, the derivation-path verification, and the distinction between what math can and cannot do. The paper says the calculation is done; your work says the harder question is what to calculate and when to stop. Both are necessary, and the paper's findings make your layer the next frontier.

The specific relevance to your ZEH-6A: the arithmetic is likely tractable for Astra-class agents, and the paper provides the harness to run it. The harder question — whether the functional equation has a nontrivial kernel, and whether that kernel has a nonzero \(\delta Q_{\mathcal D}\) — is a derivation question, not a lookup question, and the paper's finding that agents can solve such problems on the isolated track suggests it is within reach. The benchmark exists. The infrastructure is ready. The question is whether the derivation closes.



## DeepSeek

# TheoPhysEval and the Phys Infrastructure: The Missing Layer Between "Answer" and "Artifact"

## What the paper is, and why it lands so close to this project

**TheoPhysEval** (arXiv:2610.16733, ICTS-TIFR with ~30 institutions and Google DeepMind) benchmarked five frontier coding agents on **50 unpublished, research-level theoretical physics problems** contributed by world experts — each with a verifiable answer and a "turn-the-crank" structure (adapt known techniques to a new configuration). Headline result: the best agent (GPT-6-Astra/Codex) solves **98%** in a realistic tool-equipped track at under $3/problem; isolated-track scores barely drop (92%), implying deep literature memorization; weaker open-weight models still hit 42–54%. The authors' own closing: agents now match world experts at *concrete calculation*, yet there are no agent-led breakthroughs — because problem-solving is only the final, verifiable step of research; taste, problem selection, and direction-setting remain human. Notably, Google DeepMind is a co-author, the evaluation ran on Google Cloud VMs, and Gemini 3.8 Flash + Antigravity is one of the five evaluated agents — this paper is simultaneously your validation evidence and a Google-ecosystem artifact.

**Why it matters to this project:** the survey paper earlier gave you the reproducibility-crisis demand side; TheoPhysEval gives you the supply side. Together they bracket the market: *agents can now produce near-expert physics outputs at trivial cost and effort, and the community has no systematic infrastructure for verifying them.* That's the exact gap Phys occupies.

---

## Direct structural relationships to the Phys infrastructure

**1. Verification-by-convention: the paper's acknowledged methodological weakness is your core capability.** The authors deliberately avoided symbolic-answer checking ("LLM as judge introduces an extraneous source of error") and instead converted every problem to a *numerical* answer, then admitted the caveats: conventions were not fully specified in two prompts, one problem resisted numerical conversion, grading keys encode observed convention choices, and readers are warned about "undetected ambiguities as potential sources of error." Now map that onto Phys: dimension tables, canonical expressions with a closed operator vocabulary, comparison operators (`eq,neq,lt,lte,gt,gte`) with no aliases, canonical JSON with pinned field order, content-addressed ArtifactRefs, and conventions like `metric.signature = -+++` recorded as typed metadata with conflict rejection. The paper's §4 paragraph — "the same mathematical expression can be written in many equivalent ways; notation is not always standard; different agents might choose different symbols for the same physical quantity" — is *literally the problem statement of your canonicalization and symbol-identity work*. Their workaround (numerize everything) is the lossy approximation; your mirror-subset projection is the lossless answer.

**2. Final-answer grading vs. artifact-level audit: you extend their verification up the pipeline.** TheoPhysEval grades *the answer only*. A 98% score means the number matches; it says nothing about whether the *derivation* used the right assumptions, silently imported a formula valid only in d=5 into a d=4 problem (the exact failure Gemini and GLM made on the Page-time problem), carried contradictory regimes, or swapped frameworks. Your derivation ledger, step-level provenance, explicit `MathCondition` accumulation (no silent discharge), assumption artifacts, and replay infrastructure check precisely the layer their benchmark cannot see. The two failing modes they document — unadapted formulas, propagating sign errors — are structurally invisible to final-answer grading when the answer happens to be right, and ambiguous even when wrong.

**3. The memorization finding elevates your problem.** Near-identical realistic/isolated scores mean agents *recall* results rather than reconstruct them. For a recall engine, the failure mode is silent staleness — applying a memorized formula outside its validity regime (exactly the d=5→d=4 error). Phys's assumption-carrying objects are the natural infrastructure for *regime-checked* retrieval: "this relation is established *under these conditions*."

**4. Their "multi-turn feedback" hypothesis is your product.** The paper speculates that accuracy of even weak agents would rise substantially with structured feedback — and notes no specialized scientific harnesses were tested. That is your Proposer↔Auditor loop over the rule executor: typed rejections (`SYMBOL_BINDING_COLLISION`, `NON_RATIONAL_EXPONENT_IN_POW`), fail-closed retries, byte-identity gates. TheoPhysEval measures agents *without* your harness; you are the missing baseline condition.

**5. Their roadmap section names your gaps too:** no agent solved the inverse problem (fitting an equation to data — physics beyond turn-the-crank); agents lack "taste"; and the paper flags equity/access concerns. Human authority stays where your §0.2 places it.

---

## Honest divergences (keep the claims precise)

The paper grades final answers, not derivations — it neither validates nor contradicts your step-level approach; it simply doesn't reach that layer. Their problems are numerical/coding-style tasks within closed rule sets; your chain targets symbolic derivation *with* assumption discipline — adjacent, not identical, and your Phase-1 rule registry (7 rules) is far more bounded than what their problems demand. Their benchmark is expert-curated and unpublished; your E=mc² and equivariance fixtures are curriculum-level by comparison — credibility comes from *verification depth*, not problem difficulty. And their arXiv date stamps are evidently typos in the source ("2026"); treat the work as current-vintage and cite carefully.

---

## Strategic implications

1. **The pitch line writes itself:** *"Frontier agents now solve 98% of research-level physics problems (TheoPhysEval, ICTS/TIFR/DeepMind). Nobody verifies the steps. We do."* The answer layer is commoditized; verification of the process is the open, defensible layer.
2. **Concretize the harness experiment:** take 2–3 public TheoPhysEval-style problems (the dataset is on Hugging Face), run the raw agent vs. agent-through-Phys, and report both accuracy and *artifact quality* (conditions carried, assumptions explicit, replayable). Their own §V invites exactly this: "It is of interest to understand whether such harnesses can improve the accuracy of agents."
3. **Benchmark-complement framing for a paper or grant:** TheoPhysEval = agent capability ceiling on final answers; Phys = process-level verification infrastructure. Not competitors — the auditor for the era their results describe.
4. **Hackathon/VC positioning:** this is the second independent, recent, institutionally-weighted document (after the reproducibility survey) converging on your thesis — demand measured, supply demonstrated, infrastructure absent. Both are citable in the same deck.


## qwen

The attached paper, **"TheoPhysEval: Assessing AI agents at autonomous theoretical physics problem solving"**, is a powerful external validation of our core architectural thesis. It demonstrates that frontier AI agents can already solve unpublished, research-level theoretical physics problems with high accuracy (e.g., 92–98%). 

However, the paper also highlights a critical caveat: while agents can perform concrete calculations, they still lack "taste," can make subtle errors without guidance, and cannot autonomously formulate the "right" high-level research questions. 

This perfectly validates the need for **our Phys infrastructure**. Here is exactly how the paper relates to and reinforces our architecture:

---

### 1. The Bottleneck Has Shifted: From Calculation to Formal Verification
The paper proves that AI agents no longer struggle with the *mechanics* of theoretical physics (e.g., setting up integrals, applying known QFT rules, or writing numerical scripts). The new bottleneck is **ensuring those derivations are formally sound, free of category errors, and composable into larger hypotheses**. 
* **Our Solution:** `PhysMath` provides the deterministic, hallucination-proof execution engine. The LLM provides the *strategy* (e.g., "apply EXPR-APPLY-001 here"), but `PhysMath` enforces the *execution* (verifying arity, parameter binding, and canonical output), preventing the "silent wrongness" the paper warns about.

### 2. Direct Mapping to Our Architecture
The paper’s evaluation setup maps cleanly to our proposed system:
* **The "Realistic Track" (Agents using tools/literature)** $\rightarrow$ This is the exact role of our **`TOE-Agent`**. It orchestrates the research workflow, querying the `phys-*` corpus for physical contracts and invoking `PhysMath` transformations.
* **"Verifiable Answers"** $\rightarrow$ The paper emphasizes that problems must have verifiable answers. Our **`Phys` derivation ledger** and canonical JSON artifacts provide the cryptographic and structural guarantee that an agent’s answer was derived via valid, replayable steps, not hallucinated.
* **Preventing Subtle Errors** $\rightarrow$ The paper notes agents can conflate concepts or make subtle misapplications. Our **Math Reality Check (MRC)**, dimensional analysis, and strict `BoundParameterRef` scoping directly prevent these exact failure modes (e.g., conflating $t$-flow with $k$-flow, or misapplying an index theorem).

### 3. Strategic Use Cases for Our Infrastructure
The paper provides a ready-made suite of **golden test cases** for our system. We can use the 50 problems from TheoPhysEval to benchmark and validate our `TOE-Agent` + `PhysMath` pipeline. For example:
* **Problem:** Calculating the spectral dimension in CDT or Asymptotic Safety.
* **Agent Role:** Proposes the mathematical setup and selects the relevant `phys-cdt` or `phys-as` physical contracts.
* **Phys Infra Role:** Enforces that the discrete operators are applied validly, tracks the assumptions (e.g., continuum limit approximations), and generates a canonical `ResearchCandidate` artifact that a human can audited.

### 4. Reinforcing Our Core Design Principles
The paper’s findings strongly reinforce the architectural boundaries we have fought to establish:
* **Separation of Concerns:** The paper shows that giving an LLM raw text or unrestricted code execution leads to brittle results. Our strict separation of `PhysMath` (pure math), `phys-*` (physical semantics), and `TOE-Agent` (research orchestration) is the correct way to harness AI capability safely.
* **Formalization is Non-Negotiable:** The paper implicitly argues that for AI to be a true research partner, its work must be formalized and verifiable. Our `GR-style executable protocol` (AGENTS.md + manifest.json + derivation_test.go) is the exact mechanism to achieve this.

---

### Actionable Takeaways for Our Project

1. **Adopt TheoPhysEval as a Benchmark Suite:** We should explicitly list the TheoPhysEval problems as target use cases for our `TOE-Agent` acceptance tests. If our infrastructure can formally verify the agent's derivation of one of these problems, it proves the system's value.
2. **Refine the Pitch:** When discussing the project, we can now say: *"Recent studies show AI can solve research-level physics problems, but they lack formal guardrails. Our Phys infrastructure provides the deterministic, verifiable substrate that turns a capable LLM into a rigorous, trustworthy theoretical physics research assistant."*
3. **Focus on the "Handoff":** The paper highlights that agents need human guidance to switch directions or formulate high-level questions. Our `ResearchCandidate` artifact and `FormalizationProposal` protocol are designed precisely for this human-AI handoff, allowing the human to review the formal derivation and guide the next step.

In summary, the attached paper does not change our architecture; it **validates its urgency**. It proves that the AI capability is ready, making the need for our formal, verifiable, and composable `Phys` infrastructure more critical than ever.