# Task: Stress-test Phys Pseudo on the ZEH/LTB identifiability problem

You are an independent physics research agent. Your task is to use the existing **Phys Pseudo language** to reason about the supplied ZEH/LTB research workflow.

**The goal is to stress-test whether Phys Pseudo can faithfully express and expose the important reasoning in this case. This is not an implementation handoff. Produce pseudocode only—no Go implementation, no new tests, no schema changes, and no modifications to the Phys libraries.**

Do not attempt to settle the ZEH conjecture merely to make the document look complete.

## 1. Read the authoritative instructions first

Read the following files in the `phys-pseudo` repository:

- `AGENTS.md`, together with the applicable parent `../AGENTS.md`.
- `PSEUDO.md`, the sole authoritative specification of language syntax and meaning.
- `MRC_REVIEW_PROTOCOL.md`, the operational procedure for reviewing reasoning.
- `CONVENTIONS.md`, only as a historical pointer, not as an alternate specification.
- `README.md`, for scope and intended use.

Consult `plan/reality_check.md` only as advisory physics-domain knowledge. It is not an authority that automatically rejects, scores, or gates the reasoning.

Inspect the relevant existing files under `phys-lib/gr/ltb`, especially its local instructions, `fixture.go`, `claim.go`, `manifest.json`, and any relevant source or test documentation. The purpose is to reconstruct what the existing fixture actually says and distinguishes—not to change or rerun its implementation.

Read source material before making claims about what is implemented, represented, derived, or left open. If a relevant file or source is unavailable, state that limitation instead of guessing.

Do not consult implementation-handoff requirements as though this task were an implementation candidate. This is exploratory mathematical reasoning and adversarial review only.

## 2. Objective

Produce one standalone document named `ZEH_LTB.phys-pseudo.md` in the task's output or scratch location.

Use it to express the mathematical reasoning behind the ZEH/LTB identifiability investigation with Phys Pseudo, then apply the Math Reality Check (MRC) review protocol to the resulting document.

The document should make it possible for another researcher to understand:

1. What is the mathematical question?
2. What are the definitions, conventions, assumptions, and supplied results?
3. Which equations can be independently derived from the stated premises?
4. Which parts of the argument are only represented in the existing workflow?
5. What exactly would be required to establish or refute non-identifiability?
6. Where does the seven-construct language express the reasoning naturally, and where does it encounter limitations?

Do not optimize for making every claim fit neatly into the pseudocode. Optimize for faithful representation, mathematical scrutiny, and visible uncertainty.

## 3. Use only the existing Phys Pseudo language

The complete vocabulary is:

```text
given NAME: <content>
define NAME := <meaning>
assume NAME: <premise>
claim NAME: <proposition>
derive NAME: <explicit result> from [NAMES] | <reasoning>
if <condition>:
    then <consequence>
    else <alternative>
? <what is unresolved and what would resolve it>
```

Follow `PSEUDO.md` exactly.

- Introduce names before they are referenced. Use distinct identifiers and exact name matches.
- Every `derive` must state an explicit result and reference at least one previously introduced name in its premise list.
- Do not write `from []`.
- Definitions establish meanings; they must not smuggle in physical laws, assumptions, existence, or uniqueness claims.
- Claims remain propositions under examination. Their presence in the document does not establish them.
- Conditional conclusions remain inside their branch. Do not reference branch-local names outside that branch.
- Place `?` according to the specification's exact attachment and indentation rules.
- Use ordinary prose or `#` comments for source attribution and explanatory metadata. The word `from` outside a `derive` has no premise-list meaning.
- Do not invent constructs for evidence, provenance, status, proof, confidence, or scientific truth.
- Do not add author-assigned statuses such as `PROVEN` or `VERIFIED`. Existing claim-register descriptions may be retained as clearly attributed prose, not as new language constructs.

If a distinction cannot be faithfully expressed with these constructs, explain the limitation in ordinary prose. Do not change the language to accommodate this one problem.

## 4. Reconstruct the target question and conventions

The working title is:

*Spatial Backreaction and Light-Cone Observables in LTB Cosmology: An Identifiability Analysis.*

The investigation does not settle the question. Its purpose is to determine what a fixed past-light-cone distance observation implies about present-day Buchert backreaction on a specified comoving domain.

The central question is:

Given an admissible LTB model class and a fixed past-light-cone distance observation, what does that observation determine about \(Q_D(t_0)\)?

Identifiability is defined by the singleton criterion:

\[
\mathcal Q[D_A^*]
=
\{Q_D^M(t_0): M \text{ satisfies the stated admissibility and observation constraints}\}.
\]

Backreaction is identifiable exactly when this set contains one value.

Represent this criterion precisely. Do not confuse it with a statement that a particular model produces a particular value. Do not replace the singleton criterion with a vague statement that the model is underdetermined.

Preserve these declared conventions:

- \(M(r)=r^3/2\) means exactly \(r^3/2\), not \(r^{3/2}\).
- The area radius satisfies \(R=D_A\) on the central cone.
- \(R'(t_0,0)=1\) is a declared normalization.
- \(t_0=2/3\) is the declared constitution.

Inspect the fixture to establish how these statements are used. Distinguish a mathematical definition from a chosen normalization, physical assumption, source assertion, or input convention.

Do not invent the complete admissible model class, foliation, domain constraints, or normalization conditions when their details are unavailable. Record material omissions as unresolved questions.

## 5. Represent the four claim-register entries without promoting them

Reconstruct the four entries from the supplied reference and actual `claim.go` where available:

- **ZEH-Q-01:** the MHE background literature claim requiring verification.
- **ZEH-Q-02:** the incomplete candidate construction, with O1, O2, and O3 open.
- **ZEH-Q-03:** the open non-identifiability conjecture, with O1, O3, O4, O5, O6, and O7 open. No theorem artifact establishes it.
- **ZEH-Q-04:** the deferred branch outside this slice.

Use the exact propositions and descriptions from the existing source wherever recoverable. Do not invent the meanings of the O1–O7 obligations if they are not documented.

The central conjecture should be represented as a `claim`, with an appropriately attached `?` describing what remains unresolved and what kind of mathematical result would resolve it.

In particular, do not infer non-identifiability merely from the existence of metric freedom or from counting free functions. The critical unresolved issue includes establishing that the relevant \(Q_2[h]\) contribution is nonzero under the exact admissibility and observation constraints.

Do not assume that a proposed perturbation is admissible, that it preserves the exact observed distance, or that it changes \(Q_D(t_0)\). Each is a substantive mathematical obligation.

## 6. Independently reconstruct the supplied mathematical examples

Represent the following material as named pseudocode reasoning, not merely a transcription of final expressions. Re-derive consequential algebra independently and attribute the supplied reference appropriately in ordinary prose.

### A. Target distance series

The supplied binomial expansion is

\[
(1+z)^{-1/2}
=
1-\frac z2+\frac{3z^2}{8}-\frac{5z^3}{16}+\cdots.
\]

The stated numerator is

\[
2\left[1-(1+z)^{-1/2}\right]
=
z-\frac{3z^2}{4}+\frac{5z^3}{8}+\cdots.
\]

Dividing by \(1+z\) gives the target expansion

\[
D_A^*(z)
=
z-\frac{7z^2}{4}+\frac{19z^3}{8}+\cdots.
\]

Independently check the multiplication of series and every coefficient through third order. The \(19/8\) coefficient corrects an earlier \(23/8\) error caught by a composition check.

Do not simply assert that the corrected coefficient is right because it appears in the supplied reference. Show the mathematical dependency in the pseudocode.

### B. EdS vertex profile

Use

\[
Z_0(r)=(1-r/2)^{-2}
=
1+r+\frac{3r^2}{4}+\frac{r^3}{2}+\cdots,
\]

so that

\[
z(r)=Z_0(r)-1
=
r+\frac{3r^2}{4}+\frac{r^3}{2}+\cdots.
\]

The stored finite-order coefficients are therefore \(z_2=3/4\) and \(z_3=1/2\).

Represent these coefficients as baseline results supported by the supplied reference. Do not generalize them beyond the displayed series or claim that they establish the candidate recursion for arbitrary \(\beta\).

The candidate relation

\[
z_3=\frac12+\frac{2\beta}{3}
\]

has the correct supplied \(\beta=0\) specialization. The general \(\beta\)-dependence remains a candidate, not an independently established result or a golden value. Inspect the source for the definition of \(\beta\); do not invent one.

### C. EdS cone identity

The supplied definitions are

\[
u=1-r/2,\quad V_0=r/u,\quad Q_0=1/u,
\]

\[
R_{c0}=ru^2,\qquad P_0=u^2.
\]

The proposed identity is

\[
2V_0Q_0
=
\frac{3r^2}{R_{c0}}
-
\frac{r^3P_0}{R_{c0}^2}.
\]

The displayed algebra reduces the left side to \(2r/u^2\) and the right side to \(3r/u^2-r/u^2=2r/u^2\).

Check this identity independently. Crucially, inspect the domain of the original expressions, not just the simplified forms. Do not silently cancel factors and assume the original expressions are defined at points where their denominators vanish.

Determine and report all necessary restrictions on \(r\) and \(u\) for the displayed rational expressions to be defined. Assess the supplied assertion that the identity holds identically whenever \(u\ne0\). If the displayed formula leaves an endpoint or degenerate case undefined, distinguish that from whether a suitably defined limit or extension might exist. Do not assert such an extension without separate reasoning.

### D. Gauge derivative

For the exact convention

\[
M(r)=\frac{r^3}{2},
\]

independently derive

\[
\frac{dM}{dr}=\frac{3r^2}{2}.
\]

The supplied workflow reports this derivative as executed through `DIFFERENTIATE-001`, replayed, and bound to a hand-derived golden through a stored equality relation and theorem-conclusion gate.

Inspect the source to understand precisely what this recorded execution establishes. In the pseudocode, distinguish the mathematical derivation from ordinary-prose notes about the reported execution. Do not claim that this task executed or replayed the Go implementation.

### E. EdS expansion construction and variable identity

The supplied workflow reports canonicalization of the EdS construction \(\theta=H+2H\) through `EXPR-CANON-001`.

Inspect the existing construction to establish the exact expression and output actually recorded. Do not infer that canonicalization proves a physical equation or a more general algebraic identity unless the source and operation semantics support that claim.

Preserve the variable-identity limitation: production `H` is an ephemeral symbol whose encoded identity follows its display string. Byte-identical operand encodings establish syntactic sameness in that representation, not bound-parameter identity or physical meaning. The synthetic control involving different `ParameterID` values must not be presented as evidence that the production artifact has bound-parameter identity.

## 7. Preserve the existing evidence boundaries

The reference distinguishes executed work from represented-only material.

The existing workflow reports as executed:

- the gauge derivative described above;
- canonicalization of the EdS \(\theta=H+2H\) construction;
- pointwise Go-rational corroboration of the EdS cone identity and supplied series coefficients.

It reports the following as represented only:

- spatial averaging and the volume measure, with no integration primitive added;
- shear vanishing beyond the factored structure;
- the off-cone extension;
- the \(Q_2\) functional;
- the claim statuses.

Treat these as descriptions of the supplied workflow. Do not independently certify the execution history. Inspect the code and tests to clarify what each reported operation and test actually establishes.

Pointwise rational corroboration is not symbolic proof. Stored representation is not execution. Replay is not proof that the physical assumptions apply. Mathematical validity is not empirical support.

Keep source-stated material, supplied conventions, independent reconstruction, reported execution, representational limitations, and open conjecture separate using ordinary prose or comments around the pseudocode.

## 8. Apply the MRC adversarial review

After drafting the pseudocode, review it against `MRC_REVIEW_PROTOCOL.md`.

Examine all consequential steps independently. Use counterexample-first reasoning and test the simplest applicable cases before accepting a general identity.

Check, proportionally to the argument:

- whether each listed premise really suffices for its derivation;
- missing or circular dependencies;
- the difference between definitions, assumptions, inputs, source claims, and derived results;
- exact powers, coefficients, signs, series composition, and operator conditions;
- denominator domains, boundary points, degenerate cases, and normalization;
- whether a finite-order example supports only the stated finite-order result or an unjustified generalization;
- whether a candidate perturbation preserves the exact constraint before being used as evidence of non-identifiability;
- whether a conditional conclusion is incorrectly treated as unconditional;
- whether theoretical consistency is being mistaken for physical applicability or empirical confirmation.

Do not mechanically demand every kind of check in every derivation. Identify which checks are material to this specific argument.

When a claim is known to be false, refute it with the relevant counterexample or contradictory derivation. Use `?` for genuinely unresolved questions—not for a failure already established.

Each material finding should identify the affected construct or derivation, explain the defect and supporting reasoning, and state the minimum useful correction or evidence needed. Cosmetic matters must not be inflated into major scientific defects.

## 9. Stress-test the language, not just the mathematics

The purpose is also to discover whether Phys Pseudo can accommodate a realistic physics investigation without being distorted.

After the pseudocode, include a concise section in ordinary prose evaluating:

1. Which parts of ZEH/LTB were easy to express using the seven constructs?
2. Which distinctions depended on source notes or comments rather than the formal reasoning statements?
3. Were there places where conditional reasoning, the proposed premise list, or `?` attachment made an important dependency difficult to communicate?
4. Could the language express the difference between the exact mathematical criterion for identifiability and the physical conjecture that the observed data fail to determine the value?
5. Could the distinction between a candidate construction and an established derivation be preserved without inventing a status system?
6. Which essential facts were unavailable from the supplied reference or accessible files?
7. Did any real limitation require a prose explanation, or was any part genuinely impossible to represent faithfully within the existing language?
8. What did the MRC review discover that merely writing the pseudocode would not have exposed?

Do not recommend a new construct just because a statement is difficult to write. State the friction and assess whether the existing language and surrounding prose handle it adequately. Any proposed future language change would require a separate task and review.

## 10. Required output and stopping conditions

Return one standalone `ZEH_LTB.phys-pseudo.md` containing:

1. A brief scope and source-attribution preamble.
2. The core ZEH/LTB pseudocode using only the seven authorized constructs.
3. Appropriate source notes and explicit unresolved questions.
4. A concise MRC review of material findings.
5. A short evaluation of how well Phys Pseudo handles this stress test.
6. An evidential-boundary statement explaining what was checked, how it was checked, what was not independently checked, and what remains open.

The document must be useful to a physicist or AI agent who has not seen this conversation.

Do not modify `phys-pseudo` or `phys-lib/gr/ltb`. Do not create or change `AGENTS.md`, `manifest.json`, `protocol/derivation_test.go`, or any Go code. Do not add schema fields, language constructs, proof rules, or status vocabularies. Do not produce an implementation-ready handoff.

Do not claim that ZEH-Q-03 has been proved, that non-identifiability follows from function counting, or that the existing test suite settles the LTB identifiability question.

The success criterion is not a polished conclusion. It is whether Phys Pseudo can help expose precisely what the argument establishes, where its premises may be insufficient, and what remains necessary to settle the conjecture.