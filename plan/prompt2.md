# ZEH-6A — Analytical Non-Identifiability Theorem and Phys Formalization

## Mission

Establish or refute the following specific mathematical claim:

**A fixed angular-diameter distance–redshift relation \(D_A(z)\) does not uniquely determine the present-day Buchert kinematical backreaction \(Q_{\mathcal D}(t_0)\) in the specified general Lemaître–Tolman–Bondi (LTB) dust model class.**

The objective is a meaningful physics-paper-level result. Do not expand into a general Theory of Everything, a complete observational cosmology program, or an infrastructure-building exercise.

Use pen-and-paper mathematics and logic as the primary research method. Numerical computation is a last resort, not a mandatory milestone.

Formalize the research as a Phys-compatible artifact. This is a conjecture-and-proof project: the theorem must remain unproved until its mathematical obligations have actually been discharged.

## 1. Central claim and scope

Use the fixed Einstein–de Sitter (EdS) distance relation as the controlled starting case:

\[
D_A^*(z)=
\frac{2[1-(1+z)^{-1/2}]}{1+z},
\qquad 0\le z\le1.
\]

The principal objective is to determine whether an exact family of admissible general-LTB spacetimes can reproduce this same \(D_A^*(z)\) while giving different values of \(Q_{\mathcal D}(t_0)\).

Do not assume the answer. Either establish the result under explicit assumptions or identify the mathematical obstruction.

The EdS control is not sufficient by itself: finding the homogeneous solution \(Q_{\mathcal D}=0\) does not establish non-identifiability or uniqueness.

Do not attempt the simultaneous-bang uniqueness theorem as a second principal result in this task. Keep it as a separate, optional future conjecture. Do not introduce additional observational channels, nonzero \(\Lambda\), off-center observers, or more general cosmological models.

## 2. Fixed physical framework

Work in late-time classical General Relativity with:
- Irrotational pressureless dust.
- \(\Lambda=0\).
- Units \(c=G=1\), with the reference normalization \(H_0=1\).
- A central observer and a regular center.
- Comoving synchronous dust coordinates.
- The radial gauge

\[
\boxed{M(r)=\frac{r^3}{2}}.
\]

**This gauge must be written exactly as \(r^3/2\), not \(r^{3/2}\).** Check every equation, document, and artifact field for consistency.

Use the LTB metric and shell equation:

\[
ds^2=-dt^2+\frac{R'(t,r)^2}{1+2E(r)}dr^2
+R(t,r)^2d\Omega^2,
\]

\[
\dot R^2=\frac{2M(r)}{R}+2E(r).
\]

The reference EdS solution is

\[
E(r)=0,\quad t_B(r)=0,\quad t_0=\frac23,
\quad R(t,r)=r\left(\frac{3t}{2}\right)^{2/3}.
\]

The numerical value \(t_0=2/3\) is established for the reference EdS model. Do not assume it automatically applies to every perturbed model. Explicitly determine which time-origin, central-normalization, and observer-event conditions must be shared across the family.

Keep the central observable normalization consistent with the target distance curve.

Require the regular-center conditions appropriate to the chosen gauge, including \(E(r)=O(r^2)\), and the appropriate regularity of \(t_B(r)\). State all further conditions needed for an expanding, admissible solution, including

\[
1+2E(r)>0,\qquad R'(t,r)>0,\qquad \rho(t,r)>0,
\]

and avoidance of shell crossings over the domain and time interval relevant to the construction.

The spatial domain is evaluated on a comoving dust proper-time slice, with a fixed present-day physical areal-radius boundary

\[
R(t_0,r_{\mathcal D})=R_{\mathrm{phys}},
\]

where the controlled example uses \(R_{\mathrm{phys}}=100\) Mpc, or \(H_0R_{\mathrm{phys}}/c\simeq0.0233\). Recompute \(r_{\mathcal D}\) separately for each model. Do not silently hold the coordinate radius fixed.

## 3. Derive the exact iso-distance construction

Introduce the parameterization

\[
u(r)=\sqrt{1+2E(r)}.
\]

Investigate whether a suitably regular choice of \(u(r)\) can be used as a free input while the LTB light-cone equations are solved subject to

\[
R(t(r),r)=D_A^*(z(r)).
\]

Derive the complete system from the metric, shell equation, radial null geodesic, and redshift propagation equations. Use a consistent radial orientation and sign convention.

If the target-distance constraint is differentiated along the past light cone, show every step. Derive the accompanying equations for the cone variables and identify which equations are independent and which follow from the others.

Do not merely count functions. Demonstrate the actual mathematical freedom, if present, by constructing the solution family.

Establish the following obligations:

1. The exact target-distance condition is satisfied throughout the required redshift interval, not merely to first order.
2. The system has an appropriate solution from the regular central vertex.
3. The center-series conditions are derived explicitly; a claimed nonzero determinant away from the center does not resolve a singular vertex.
4. Each resulting cone solution corresponds to a valid LTB spacetime, rather than only a formal solution of equations defined on the cone.
5. The bang-time function is recovered consistently from the shell evolution. For the expanding branch, use the shell-age relation

\[
t-t_B(r)=
\int_0^{R(t,r)}
\frac{d\widetilde R}
{\sqrt{2M(r)/\widetilde R+2E(r)}}.
\]

6. The required regularity and physical admissibility conditions hold over the stated domain and interval.

Do not claim a family exists merely because the equations appear to contain a free function. Prove local existence and the relevant regularity conditions, or state exactly where the construction fails.

At minimum, investigate the specified EdS target. Generalize the result to arbitrary vertex-compatible distance functions only if the derivation genuinely supports that broader statement.

## 4. The principal mathematical bottleneck: \(Q_{\mathcal D}\)

Use the standard Buchert kinematical backreaction definition

\[
Q_{\mathcal D}=
\frac23
\left(
\langle\theta^2\rangle_{\mathcal D}
-\langle\theta\rangle_{\mathcal D}^2
\right)
-2\langle\sigma^2\rangle_{\mathcal D},
\]

with

\[
\theta=H_\parallel+2H_\perp,
\qquad
H_\parallel=\frac{\dot R'}{R'},
\qquad
H_\perp=\frac{\dot R}{R},
\]

\[
\sigma^2=\frac13(H_\parallel-H_\perp)^2.
\]

Use the correct proper-volume measure

\[
dV=\frac{4\pi R^2R'}{\sqrt{1+2E}}\,dr.
\]

The key task is to determine whether \(Q_{\mathcal D}\) is nonconstant on the proposed exact iso-distance family.

Do not infer non-identifiability of \(Q_{\mathcal D}\) merely because distinct metrics or distinct free functions exist.

### Perturbative route

If useful, consider a smooth family about EdS,

\[
u_\epsilon(r)=1+\epsilon h(r)+O(\epsilon^2),
\]

where \(h(r)\) satisfies the derived regular-center and normalization conditions.

Derive the expansion

\[
Q_{\mathcal D}[\Psi(u_\epsilon)]
=\epsilon Q_1[h]+\epsilon^2Q_2[h]+O(\epsilon^3),
\]

or the correct expansion if the leading order differs.

Show analytically which terms vanish and why. Do not assume the leading order without deriving it.

Calculate the relevant functional \(Q_2[h]\), including the correct proper-volume measure and the change in coordinate boundary required to preserve \(R(t_0,r_{\mathcal D})=R_{\mathrm{phys}}\).

Then either:
- exhibit a regular profile \(h\) for which the first nonzero contribution to \(Q_{\mathcal D}\) is nonzero, with enough control of the remainder to establish a genuine difference for sufficiently small amplitude; or
- prove that this contribution vanishes for every admissible profile, investigate whether an invariance result follows, and revise the conjecture accordingly.

An arbitrary curvature bump or an intuitive expectation of nonzero shear is not sufficient. The relevant functional must actually be derived and evaluated analytically.

### Acceptance target

The preferred result is a constructive theorem: two admissible LTB models have the same exact \(D_A^*(z)\) over the specified interval and different \(Q_{\mathcal D}(t_0)\) on the same physical domain and foliation.

An analytical proof is sufficient. Do not build a numerical solver merely to satisfy an artificial requirement.

If the construction cannot be completed, deliver the strongest valid partial result and identify the exact missing proof obligation. Do not promote the conjecture to a theorem.

## 5. Novelty boundary

Perform a targeted primary-literature check on the precise proposed contribution, particularly existing LTB inverse-problem results and analytical LTB Buchert-backreaction results.

Determine whether the proposed \(Q_{\mathcal D}\)-specific non-identifiability statement has already been proved.

Do not present the established fact that distance data leave freedom in the LTB metric functions as our new contribution. The proposed extension must demonstrate something specific about \(Q_{\mathcal D}(t_0)\).

Cite sources and distinguish what they establish from what remains open. If an identical result already exists, stop and identify the smallest defensible extension rather than forcing novelty.

## 6. Required scientific artifact

Create a Phys-compatible research artifact following the existing workspace and package instructions, including the canonical formalization structure:

- `AGENTS.md`
- `manifest.json`
- `protocol/derivation_test.go`

Inspect the applicable workspace and package instructions and the locked Phys representation specification before editing. Follow their exact requirements; do not invent package conventions or APIs and do not modify frozen legacy instructions.

The artifact must include:

1. A precise, individually identifiable theorem conjecture.
2. Explicit physical assumptions, conventions, regime, scale, gauge, domain, and foliation.
3. All mathematical definitions and the derivation with dependencies between claims.
4. A status for each proposition: established, derived, conditional, conjectural, unsupported, or falsified.
5. The proof obligations and the exact evidence needed to satisfy each one.
6. A literature and novelty record.
7. An MRC and MRC2 evaluation.
8. Clear limitations and non-claims.
9. A record of what remains unresolved.

Use PhysMath representations and PhysLib quantities where the current implementations support them. If a required concept is not yet supported, document that limitation rather than creating a misleading representation.

The Phys artifact must trace the scientific claim and its reasoning; it does not require the proof to be rewritten as a software algorithm. Code may verify structural or algebraic properties where appropriate, but passing a test suite must not be described as automatically proving a general mathematical theorem.

Do not require the investigation to be written in Go. Analytical derivation is the primary method for this task.

## 7. Out of scope

Do not attempt:
- The simultaneous-bang uniqueness theorem.
- A new relation involving extra observables.
- Redshift-drift phenomenology.
- Nonzero \(\Lambda\), pressure, noncentral observers, or nonspherical geometries.
- A survey-data or parameter-fitting project.
- Large numerical simulations.
- Quantum gravity, Planck-scale extrapolation, or a Theory of Everything.
- Additional Phys infrastructure unrelated to recording and checking this result.

## 8. Final deliverable and decision

Return:

1. The exact theorem or conjecture in mathematical form.
2. A step-by-step derivation or proof, with every assumption explicit.
3. The analytical construction of the iso-distance family, if established.
4. The \(Q_{\mathcal D}\) variation calculation and fixed-domain treatment.
5. The relevant literature comparison.
6. The complete Phys-compatible artifact and a list of its paths.
7. A claim-status table showing established results, new derivations, open obligations, and failed attempts.
8. An MRC/MRC2 review.
9. A verdict: ESTABLISHED, PARTIALLY ESTABLISHED, REFUTED, or UNRESOLVED.

The task succeeds only if the conclusion follows from the mathematics. A precise unresolved result is preferable to an unsupported theorem claim.
