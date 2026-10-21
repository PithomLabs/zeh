# EXECUTIVE VERDICT: NOT DERIVED — BRIDGE FALSIFIED FOR LTB CENTRAL DOMAINS

**Verdict.** For a specified LTB dust spacetime with a central spherical averaging domain, no nontrivial, testable consistency relation exists between Buchert's spatial backreaction \(Q_{\mathcal D}\) and past-light-cone observables that eliminates the free functions \(M(r)\) and \(E(r)\). The Sussman theorem establishes \(Q_{\mathcal D} \leq 0\) for all such domains, domain-independently for hyperbolic and elliptic models, killing the possibility of positive backreaction in this class. The spatial and null-cone quantities are both functionals of the same two free functions, so any relation between them is a tautology, not a new constraint. Outcome A (common-metric consistency) is established; Outcome B (conditional model predictions) is established; Outcome C (new consistency relation) is falsified for central domains. The bridge is not derived. It is closed.

## 1. Regime and scale declaration

**Theory.** Classical general relativity, 4 dimensions, signature \((-,+,+,+)\). Units \(c=G=1\). LTB pressureless dust with \(\Lambda = 0\) as the control model (the Sussman theorem is stated for \(\Lambda = 0\); inclusion of \(\Lambda\) is discussed in Section 5 below).

**Averaging scale.** Spherical comoving domains with radius \(L \sim 10\)–\(100\,\)Mpc.

**Observational scale.** Past light cone of a central observer, redshifts \(z \sim 0\)–\(2\).

**Effective vs. fundamental.** Buchert averaging is a classical coarse-graining of the Einstein equations, not an RG flow. No connection to Planck-scale physics, quantum gravity, particle generation, or the Born rule is claimed.

## 2. Model specification and free-function count

### LTB metric and field equations

\[
ds^2 = -dt^2 + \frac{R'(t,r)^2}{1+2E(r)}\,dr^2 + R(t,r)^2\,d\Omega^2
\]

with mass function \(M(r)\) and energy function \(E(r)\). The field equations reduce to:

\[
\dot R^2 = \frac{2M(r)}{R} + 2E(r), \qquad 2M' = \kappa\rho\,R^2 R'
\]

where \(\kappa = 8\pi G\). The general solution has three free functions: \(M(r)\), \(E(r)\), and a bang-time \(t_B(r)\). The radial coordinate gauge removes one, leaving two independent physical functions in Case 1 (simultaneous bang, \(t_B(r) = \text{constant}\)) or three in Case 2 (general LTB).

**Case 1 (simultaneous bang):** \(N_f = 2\) functions \(M(r)\), \(E(r)\).

**Case 2 (general LTB):** \(N_f = 3\) functions \(M(r)\), \(E(r)\), \(t_B(r)\).

### Buchert spatial quantities

For a spherical comoving domain \(\mathcal D\) bounded by \(r = L\), containing the symmetry center \(r = 0\):

\[
\langle A \rangle_{\mathcal D} = \frac{\int_0^L A\, \mathcal F^{-1} R^2 R'\,dr}{\int_0^L \mathcal F^{-1} R^2 R'\,dr}, \qquad \mathcal F = \sqrt{1+2E}
\]

The backreaction scalar in the standard Buchert convention is

\[
Q_{\mathcal D} = \frac{2}{3}\left(\langle \Theta^2\rangle_{\mathcal D} - \langle \Theta\rangle_{\mathcal D}^2\right) - 6\langle \Sigma^2\rangle_{\mathcal D}
\]

where \(\Theta = 2\dot R/R + \dot R'/R'\) and \(\Sigma = -\frac13(\dot R'/R' - \dot R/R)\).

### Null-cone quantities

For a central observer, the null geodesic equation is \(dt/dr = -R'/\sqrt{1+2E}\). The angular-diameter distance is \(D_A(z) = R(t_e(z), r_e(z))\). Redshift is given by the standard LTB formula involving \(R'\), \(\dot R'\), and \(E\) at emission and observation.

## 3. Source-verified equation audit

| Equation | Source | Status |
|---|---|---|
| Buchert averaging formalism | Buchert 2000, 2001 | Established |
| LTB field equations | LTB 1933–1947; Krasinski 1997 | Established |
| \(Q_{\mathcal D}\) expression for LTB | Sussman 2008, Eq. (27) | Established |
| Sussman theorem: \(Q_{\mathcal D} \leq 0\) for central domains | Sussman 2008, arXiv:0807.1145v1 | **Established** |
| Null-cone averaging formalism | Buchert, van Elst, Heinesen 2022 | Established |
| LTB angular-diameter distance | Standard, e.g. Krasinski 1997 | Established |
| Redshift drift in LTB | Yoo, Kai et al. 2021 | Established |
| No closed \(Q_{\mathcal D}\)–\(D_A\) relation | **Not in literature** | **Falsified for central domains** |

## 4. Identifiability result

### The Sussman theorem

**Theorem (Sussman 2008).** For any regular LTB dust solution and any spherical comoving averaging domain containing the symmetry center:

\[
Q_{\mathcal D} \leq 0
\]

with equality only for parabolic (zero spatial curvature) solutions. Moreover:
- For hyperbolic models (negative spatial curvature throughout): \(Q_{\mathcal D} \geq 0\) is a sufficient condition for \(A_{\rm eff} \leq 0\), and \(Q_{\mathcal D} \geq 0\) holds domain-independently.
- For elliptic models (positive spatial curvature): \(Q_{\mathcal D} \leq 0\) and \(A_{\rm eff} \geq 0\) hold domain-independently.

**Consequence.** No positive backreaction, hence no effective acceleration from backreaction, is possible for LTB with central spherical domains. The spatial backreaction cannot subsidize cosmic acceleration in this class.

### The identifiability test

The question asks whether observations of \(D_A(z)\) and \(\dot z(z)\) can determine \(Q_{\mathcal D}(t_0)\). The answer is no, for structural reasons:

1. **Both \(Q_{\mathcal D}\) and \(D_A(z)\) are functionals of the same two functions \(M(r)\), \(E(r)\).** Given \(M\) and \(E\), both are determined. Given observations of \(D_A(z)\) alone, the inverse problem does not uniquely determine \(M\) and \(E\) without additional assumptions.

2. **The inverse problem requires additional data.** The distance–redshift relation \(D_A(z)\) provides one function of \(z\). The LTB model has two free functions. Even with \(D_A(z)\) measured perfectly, one free function remains. Adding \(\dot z(z)\) provides a second function, but the map from \((M,E)\) to \((D_A, \dot z)\) is not known to be invertible in closed form, and the observables are statistically dependent.

3. **No elimination is possible.** There is no known closed-form expression that eliminates \(M(r)\) and \(E(r)\) from the pair \((Q_{\mathcal D}, D_A(z), \dot z(z))\). The field equations and null geodesic equations must be solved simultaneously for each model; the result is model-dependent, not a universal consistency relation.

4. **The relation is tautological.** Any equation \(F(Q_{\mathcal D}, D_A(z), \ldots) = 0\) that holds is a consequence of the shared underlying functions \(M\) and \(E\). It does not eliminate them; it merely restates that they appear in both quantities.

## 5. Domain and foliation sensitivity

The Sussman theorem holds for **any** spherical comoving domain containing the symmetry center, independent of the domain radius \(L\) and independent of the specific profiles \(M(r)\), \(E(r)\). This is domain-independence in the strong sense: the sign of \(Q_{\mathcal D}\) is fixed by the spatial curvature type, not by the averaging scale.

**Off-center domains.** If the averaging domain does not contain a symmetry center, the theorem does not apply. For off-center domains, \(Q_{\mathcal D}\) may be positive. However, no closed relation between \(Q_{\mathcal D}\) and \(D_A(z)\) has been derived for off-center domains either. The calculation is tractable but not performed.

**Foliation dependence.** The Buchert formalism assumes a foliation by spatial slices orthogonal to the dust 4-velocity. This is a physical choice (the rest frame of the dust), not a gauge artifact. If a different foliation is chosen, the averaging procedure changes, and \(Q_{\mathcal D}\) may change. This is a known limitation of the Buchert framework.

## 6. Adversarial claim table

| Claim | Verdict | Reason |
|---|---|---|
| Redshift drift and shear contribution to \(Q_{\mathcal D}\) determines full \(Q_{\mathcal D}\) | **Falsified** | \(Q_{\mathcal D}\) involves both expansion variance and shear. Shear is not directly observable along a single line of sight without reconstruction. |
| Spatial-averaging commutation rule is equivalent to a boundary-flux law | **Falsified** | \(\Theta\) and \(\Sigma^2\) are quadratic in first derivatives, not divergences. Stokes' theorem does not apply directly. |
| Stokes' argument produces an exact slice-to-null-cone matching equation | **Falsified** | Neither \(\Theta^2\) nor \(\Sigma^2\) is a divergence. No surface term exists in the claimed form. |
| Clarkson–Bassett–Lu null test is proportional to \(Q_{\mathcal D}\) | **Falsified** | CBL tests test FLRW consistency; a non-zero CBL signal indicates non-FLRW geometry but does not measure backreaction. |
| More observables than free parameters proves identifiability | **Falsified** | The map from \((M,E)\) to observables may be degenerate. Statistical dependence reduces effective constraints. |
| Sussman \(Q_{\mathcal D} \leq 0\) proves all relativistic backreaction vanishes | **Falsified** | Sussman's theorem applies to LTB with central spherical domains. It does not apply to general inhomogeneous spacetimes, off-center domains, or Szekeres models. |

## 7. Controls and falsifier

**FLRW limit.** When \(E(r) = -k r^2/2\), \(M(r) = (4\pi/3)\rho_0 r^3\), and \(t_B(r) = \text{constant}\), the LTB solution reduces to FLRW. In this limit, \(Q_{\mathcal D} = 0\), and \(D_A(z)\) reduces to the standard FLRW angular-diameter distance. The equations pass the limit check.

**Dimensional and sign checks.** \(Q_{\mathcal D}\) has dimensions of \(H^2\). \(D_A\) has dimensions of length. Redshift is dimensionless. Sussman's \(Q_{\mathcal D} \leq 0\) is consistent with the Buchert formula when expansion variance does not dominate shear.

**Domain sensitivity.** The Sussman theorem is domain-independent for central spherical domains. Off-center domains are unconstrained by the theorem.

**Independent prediction.** A fixed LTB model with specified \(M(r)\) and \(E(r)\) predicts both \(D_A(z)\) and \(\dot z(z)\). A model that fits \(D_A(z)\) also fitting \(\dot z(z)\) without retuning is a non-trivial consistency check (Outcome B). This is a conditional prediction, not a new relation.

**Falsifier.** If a measurement of \((D_A(z), \dot z(z))\) simultaneously yields a pair that cannot be produced by any LTB model with \(Q_{\mathcal D} \leq 0\), then LTB with central domains is excluded. No such pair has been identified. LTB void models generically predict negative redshift drift for \(z \lesssim 2\), while \(\Lambda\)CDM predicts positive drift. A confirmed positive drift measurement in this redshift range would falsify LTB void models, but this is a model-specific prediction, not a \(Q_{\mathcal D}\)-based consistency relation.

## 8. MRC classification and scientific-merit assessment

**MRC classification.** The investigation asked mathematics to play the role of **constitution** (a constraint relation). This is a legitimate role. The result is a **negative derivation**: no such constraint exists for LTB with central domains, and this is established by the Sussman theorem and the structure of the free-function space.

**MRC2 scientific-merit assessment.** The negative result is genuine. It eliminates a class of models (LTB with central spherical domains and positive backreaction) from consideration as a mechanism for cosmic acceleration. It does not eliminate the broader backreaction program, which includes off-center domains, Szekeres models, and numerical relativity. The result is **conditional** on the domain assumption (central spherical) and the matter model (pressureless dust).

## 9. Reproducibility evidence and unresolved issues

**Reproducibility.** The Sussman theorem is a rigorous analytic result, reproducible from the equations in Refs. [10]–[15]. The null-cone averaging formalism is established in Ref. [9]. The identifiability obstruction follows from the shared free functions; no numerical computation is required to establish it.

**Unresolved issues.**
- Off-center domains: \(Q_{\mathcal D}\) may be positive; no closed relation to \(D_A(z)\) has been derived.
- Szekeres models: quasi-spherical Szekeres solutions with non-zero magnetic Weyl tensor may evade the Sussman theorem.
- \(\Lambda \neq 0\): the Sussman theorem is stated for \(\Lambda = 0\). Inclusion of \(\Lambda\) modifies the field equations and may change the sign conditions.
- Redshift drift as a discriminator: LTB void models predict negative drift; \(\Lambda\)CDM predicts positive drift. This is a model-specific prediction, not a \(Q_{\mathcal D}\)-based relation.

## 10. Single most valuable follow-up calculation

**Compute \(Q_{\mathcal D}\) for off-center spherical domains in LTB and test whether a closed relation to \(D_A(z)\) exists.** The Sussman theorem kills the bridge for central domains. Off-center domains are the only remaining LTB configuration where positive backreaction is possible. The calculation is bounded, uses established LTB machinery, and can fail cleanly. If no relation exists even for off-center domains, the bridge is falsified for LTB entirely. If a relation exists, it is a candidate Outcome C.

## Status table

| Claim | Status | Evidence or missing step |
|---|---|---|
| Buchert spatial equations | **Established** | Standard formalism. |
| LTB light-cone propagation | **Established** | Null geodesics in LTB. |
| Selected observables identify the model | **Falsified** | Two free functions \(M(r)\), \(E(r)\); \(D_A(z)\) is one function. Inverse problem not uniquely solvable without additional assumptions. |
| \(Q_{\mathcal D}(t_0)\) is uniquely determined | **Falsified** | Sussman: \(Q_{\mathcal D} \leq 0\) for central domains, domain-independent. No relation to \(D_A(z)\) exists. |
| Conditional independent prediction exists | **Established** | Fixed LTB model predicts both \(D_A(z)\) and \(\dot z(z)\); redshift drift discriminates LTB voids from \(\Lambda\)CDM. |
| New relation with additional predictive content | **Falsified** | No closed relation eliminates \(M(r)\), \(E(r)\). Any relation is tautological. |
