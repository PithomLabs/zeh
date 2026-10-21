# ZEH-6A-AR — Adversarial Mathematical and Phys Artifact Review

## Role

Independently audit the complete output of ZEH-6A, including the mathematical derivation, theorem statements, literature claims, and Phys-compatible research artifact.

Assume the submitted conclusions may be wrong, the derivation may contain hidden assumptions, and the formal artifact may claim more than the evidence warrants.

Your role is to determine what survives scrutiny. Do not defend the proposed result merely because it was the objective of the research.

## Primary review question

Has the work actually established that two admissible general-LTB models can reproduce the same specified angular-diameter distance function \(D_A^*(z)\) exactly, while yielding different present-day Buchert backreaction \(Q_{\mathcal D}(t_0)\) for the same physical domain and foliation?

If not, identify precisely which implications have been proved and which have not.

## 1. Reconstruct the logic independently

Do not rely solely on the submitted summary, status table, executive verdict, or theorem labels.

Trace the argument from:
- The LTB metric and shell equation.
- The null-geodesic and redshift-propagation equations.
- The imposed distance constraint.
- The proposed cone-variable system.
- The regular-center conditions.
- The reconstruction of the off-cone spacetime and bang-time function.
- The evaluation of \(Q_{\mathcal D}(t_0)\).

For each major inference, state the premises, intermediate equations, and conclusion. Identify any circular reasoning, missing implication, or equation used outside its domain of validity.

## 2. Equation and convention audit

Independently check:

### LTB framework
\[
ds^2=-dt^2+\frac{R'^2}{1+2E}dr^2+R^2d\Omega^2,
\qquad
\dot R^2=\frac{2M}{R}+2E.
\]

The required gauge is \(M(r)=r^3/2\), not \(M(r)=r^{3/2}\). Check the entire artifact for this and other convention inconsistencies.

Check the density equation, radial-gauge implications, center regularity, dimensions, signs, and the distinction between coordinate functions and invariant physical quantities.

### Light-cone equations

Check the sign convention and validity of

\[
\frac{dt}{dr}=-\frac{R'}{\sqrt{1+2E}},
\qquad
\frac{d\ln(1+z)}{dr}
=\frac{\dot R'}{\sqrt{1+2E}},
\qquad
D_A(z)=R(t(z),r(z)).
\]

Verify the differentiated target-distance equation from the chain rule. Check whether the claimed system is actually closed and whether its constraints are independent.

If the argument says that a differentiated shell equation supplies no new constraint, demand an explicit algebraic demonstration. A claim that two expressions agree is not a proof that they are identical.

### Reconstruction and existence

Check that the proposed free input \(u(r)=\sqrt{1+2E(r)}\) genuinely remains free after the imposed distance condition and all center-normalization constraints.

Check the center-series expansion. Picard–Lindelöf cannot be invoked without specifying a closed initial-value problem and verifying appropriate regularity and local-Lipschitz conditions away from any singular vertex.

Determine whether a formal cone solution corresponds to a realizable LTB spacetime. The reconstructed \(t_B(r)\), shell evolution, expanding branch, and required regularity conditions must be consistent.

Do not confuse first-order preservation of \(D_A(z)\) with exact equality over the whole redshift interval.

## 3. Buchert-backreaction audit

Independently reconstruct the calculation from

\[
Q_{\mathcal D}=
\frac23\left(
\langle\theta^2\rangle_{\mathcal D}
-\langle\theta\rangle_{\mathcal D}^2
\right)
-2\langle\sigma^2\rangle_{\mathcal D},
\]

with

\[
\theta=\frac{\dot R'}{R'}+2\frac{\dot R}{R},
\qquad
\sigma^2=\frac13
\left(\frac{\dot R'}{R'}-\frac{\dot R}{R}\right)^2,
\]

and

\[
dV=\frac{4\pi R^2R'}{\sqrt{1+2E}}\,dr.
\]

Check:
- Whether the homogeneous EdS limit gives \(Q_{\mathcal D}=0\).
- Whether the perturbative expansion begins at the order claimed.
- Whether \(Q_2[h]\) is actually derived, rather than inferred from generic statements about shear or curvature.
- Whether cancellations between expansion variance and shear are considered.
- Whether a specific admissible profile gives a demonstrably nonzero leading contribution.
- Whether the remainder term is sufficiently controlled to infer a difference for small but finite perturbations.
- Whether the physical domain is held fixed while the coordinate boundary changes appropriately from model to model.

**A different metric with the same \(D_A(z)\) does not suffice. The \(Q_{\mathcal D}\)-specific nonconstancy must be proved.**

If that proof is missing, the main theorem remains open.

## 4. Admissibility and hidden assumptions

Audit all conditions required for the claimed family:
- Regularity at the central observer.
- Correct low-redshift normalization and time-origin conventions.
- \(1+2E>0\).
- \(R'>0\) on the relevant interval.
- Positive dust density.
- Shell-crossing avoidance.
- Compatibility between the prescribed target distance and the central vertex series.
- Existence of the spatial slice and its physical domain for each member of the family.

Do not accept “small perturbations preserve regularity” without stating the function space, interval, open conditions, and argument supporting the claim.

Determine whether fixing \(t_0=2/3\) for every member of the family is justified, or whether this is only the EdS reference normalization.

## 5. Perturbation and functional-identifiability audit

Examine the claimed mapping

\[
u\longmapsto \Psi(u)
\longmapsto Q_{\mathcal D}^{\Psi(u)}(t_0).
\]

Ask:

1. Is \(\Psi\) defined on a nontrivial set of admissible functions?
2. Does every member reproduce the same target distance exactly?
3. Is the mapping into admissible spacetime models actually proved?
4. Is \(Q_{\mathcal D}\circ\Psi\) proved to be nonconstant?
5. Does any asserted result rely only on counting functions?
6. Does the construction establish the theorem only for the EdS target, or genuinely for a larger target class?
7. Are conclusions restricted to the interval, domain, and subclass for which they were derived?

If the submitted work proves only metric non-uniqueness, explicitly reject any stronger conclusion about \(Q_{\mathcal D}\) until its nonconstancy is established.

## 6. Literature and novelty audit

Check the cited prior work against the exact claims attributed to it, especially LTB inverse reconstruction, Buchert spatial averaging, and analytical LTB backreaction results.

Distinguish:
- What is already established in the literature.
- What follows directly from those results.
- What is newly derived in the submission.
- What is only conjectured.
- What remains unresolved.

Do not accept a novelty claim merely because the exact words “\(Q_{\mathcal D}\)-identifiability theorem” were not found. Conversely, do not reject a potentially meaningful theorem solely because it uses known equations; determine whether the particular conclusion is already established.

If the literature references cannot be verified, mark them as unresolved verification obligations rather than confirmed prior art.

## 7. Phys artifact and scientific traceability audit

Review the actual artifact against the applicable workspace and package instructions.

Verify:
- `AGENTS.md`, `manifest.json`, and `protocol/derivation_test.go` are present at the correct locations.
- The gauge, equations, assumptions, units, foliation, domain, and target are consistent across all files.
- The manifest states exactly what each claim asserts and what evidence supports it.
- Conjectures and unresolved proof obligations have not been marked as established.
- Derivation steps have explicit dependencies.
- The artifact distinguishes analytical proof from executable checks.
- No nonexistent PhysMath object, PhysLib quantity, API, or completed workflow is invented.
- Any tests actually run are distinguished from tests merely specified.
- The artifact preserves failed approaches and limitations without disguising them as results.

Do not accept a generic successful Go test as proof of a physics theorem. Do not demand Go implementations of mathematics that are better expressed through an analytical derivation.

## 8. MRC and MRC2

Apply the Math Reality Check:
- Census: are the true physical degrees of freedom and constraints accounted for?
- Grammar: are the equations, signs, dimensions, and limiting cases correct?
- Constitution: are assumptions, gauge, domain, foliation, and regime explicit?
- Shield: what exact derivation or counterexample supports the result?
- Generator/selector: does the manuscript avoid treating a kinematic restriction as a causal mechanism?

Then assess scientific merit:
- Is the contribution genuinely new relative to prior work?
- Does it answer the stated research question?
- Does it add explanatory or predictive content?
- Are the claims proportionate to the evidence?
- Is the paper still meaningful if an optional theorem or generalization fails?

## 9. Required review output

Return a concise but technically substantive referee report containing:

1. **Verdict:** ACCEPT AS ESTABLISHED, ACCEPT WITH LIMITATIONS, REVISE, or REJECT THE CLAIM.
2. A claim-by-claim table: claim, submitted status, independently adjudicated status, evidence, and missing obligations.
3. Every mathematical error or unsupported inference, ranked as BLOCKER, MAJOR, or MINOR.
4. The exact equations or proof steps needing correction.
5. A separate judgment on the exact iso-distance family and the \(Q_{\mathcal D}\)-nonconstancy result.
6. A separate judgment on whether the Phys artifact correctly represents the scientific status.
7. The minimum corrections required to make the result auditable.
8. A clear statement of what can responsibly be claimed in a physics paper now.

Do not silently repair the submission and then grade the repaired version as if the original had been correct. Identify the defect first, explain its consequence, and propose the smallest valid correction.

Do not broaden the project, add a new research program, require numerical simulations without a specific mathematical justification, or promote an unresolved conjecture because it would make the paper more impressive.

The objective is to protect the scientific result, not the proposed conclusion.
