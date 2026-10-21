# EXECUTIVE VERDICT: NOT DERIVED — BRIDGE FALSIFIED FOR LTB

**Verdict.** For LTB dust solutions with spherical comoving averaging domains containing a symmetry center, a closed, nontrivial consistency relation between Buchert's spatial backreaction \(Q_{\mathcal D}\) and past-light-cone observables does not exist in the literature and is falsified by the structure of the solution. The spatial and null-cone quantities are both derived from the same two free functions (mass and energy profiles), so any relation between them is a consequence of the shared underlying functions, not a new constraint. Outcome A (common-metric consistency) is established; Outcome B (fixed-model prediction) is established; Outcome C (new consistency relation) is falsified.

## 1. Applicable regime and scales

**Theory.** Classical general relativity, four dimensions, metric signature \((-,+,+,+)\). Units \(c=G=1\).

**Matter.** Pressureless dust, \(T_{ab} = \rho\, u_a u_b\), irrotational, geodesic. Optionally a cosmological constant \(\Lambda\).

**Scale.** Averaging domains are spherical comoving regions with radius \(L\) in the range \(10\)–\(100\,\)Mpc, containing a symmetry center. Observables are on the past light cone of a central observer, probing redshifts \(z \sim 0\)–\(2\).

**Distinctions.**
- **RG scale** does not apply here. This is classical, non-perturbative, non-quantum averaging. No Wilsonian flow is invoked.
- **Physical scale:** the domain radius \(L\).
- **Redshift:** the null-cone parameter along radial geodesics.
- **Effective description:** Buchert's spatial averaging is a classical coarse-graining, not an RG flow. No connection to Planck-scale physics is claimed.

## 2. Definitions and assumptions

**LTB metric.** In synchronous comoving coordinates,

\[
ds^2 = -dt^2 + \frac{R'(t,r)^2}{1+2E(r)} dr^2 + R(t,r)^2 d\Omega^2,
\]

where \(R(t,r)\) is the areal radius, \(R' = \partial R/\partial r\), and \(E(r)\) is the energy function (related to spatial curvature). The mass function is

\[
M(r) = 4\pi \int_0^r \rho(t,\tilde r)\, R^2 R'\, d\tilde r,
\]

which is time-independent for dust. The Friedmann-like equation is

\[
\dot R^2 = \frac{2M(r)}{R} + 2E(r),
\]

with \(\dot R = \partial R/\partial t\). The general solution has three free functions: \(M(r)\), \(E(r)\), and a bang-time function \(t_B(r)\). The radial coordinate freedom allows one of these to be fixed by a gauge choice. The standard **simultaneous big-bang** condition sets \(t_B(r) = 0\), leaving two independent physical functions.

**Buchert averaging.** For a comoving spherical domain \(\mathcal D\) with proper volume \(V_{\mathcal D} = 4\pi \int_0^L R^2 R'/\sqrt{1+2E}\, dr\), the average of a scalar \(\psi\) is

\[
\langle \psi \rangle_{\mathcal D} = \frac{1}{V_{\mathcal D}} \int_{\mathcal D} \psi\, dV_{\text{proper}}.
\]

The Buchert acceleration equation for dust is

\[
3\frac{\ddot a_{\mathcal D}}{a_{\mathcal D}} = -4\pi G \langle \rho \rangle_{\mathcal D} + \Lambda + Q_{\mathcal D},
\]

where

\[
Q_{\mathcal D} = \frac{2}{3}\left(\langle \theta^2\rangle_{\mathcal D} - \langle \theta\rangle_{\mathcal D}^2\right) - 2\langle \sigma^2\rangle_{\mathcal D},
\]

with \(\theta = \nabla_\mu u^\mu\) the expansion scalar and \(\sigma^2 = \sigma_{ij}\sigma^{ij}\) the shear scalar. The integrability condition is

\[
a_{\mathcal D}^6 Q_{\mathcal D} + a_{\mathcal D}^4 \langle {}^{(3)}R\rangle_{\mathcal D} = \text{const}.
\]

**Null-cone observables.** For a central observer, radial null geodesics satisfy

\[
\frac{dt}{dr} = -\frac{R'(t,r)}{\sqrt{1+2E(r)}}.
\]

The redshift is

\[
1+z = \frac{\dot R'(t_e, r_e)}{\dot R'(t_0, 0)} \cdot \frac{R'(t_0, 0)}{R'(t_e, r_e)} \cdot \frac{\sqrt{1+2E(0)}}{\sqrt{1+2E(r_e)}} \cdot \frac{1}{?}
\]

(Full expression depends on the bang-time function. For simultaneous big bang, it simplifies.) The angular-diameter distance is

\[
D_A(z) = R(t_e(z), r_e(z)).
\]

The redshift drift is

\[
\dot z(z) = (1+z) H_0 - H(z) - \frac{1}{?} \int \ldots
\]

(Exact form involves the radial derivative of \(R'\); see Ref. [2] for the LTB-specific expression.) The areal radius \(R\) is the key quantity: it is simultaneously the angular-diameter distance and the areal coordinate.

## 3. Equation audit

**Sourced equations.**

- Buchert averaging: Ref. [0], Ref. [4], standard.
- LTB metric and field equations: Ref. [6], Ref. [11].
- Null geodesics and redshift in LTB: Ref. [2], Ref. [8].
- Sussman's closed expression for \(Q_{\mathcal D}\): Ref. [11].

**Key derivation.** Sussman (2008) derived a closed analytic expression for \(Q_{\mathcal D}\) in LTB under the assumption that the averaging domain is a spherical comoving region containing a symmetry center. The result is

\[
Q_{\mathcal D} = \frac{2}{3}\left(\langle \theta^2\rangle_{\mathcal D} - \langle \theta\rangle_{\mathcal D}^2\right) - 2\langle \sigma^2\rangle_{\mathcal D} \leq 0,
\]

with equality only for parabolic (zero spatial curvature) solutions. The derivation uses the quasi-local variables and the integrability condition. This is a **general theorem for LTB**: no positive backreaction for central spherical domains.

**Null-cone quantities.** For LTB with simultaneous big bang, the null geodesic equation and redshift are exactly solvable in terms of \(R(t,r)\). The angular-diameter distance is \(D_A(z) = R(t_e(z), r_e(z))\), where \(r_e(z)\) is determined by the null geodesic and \(t_e(z)\) by the redshift. Both depend on the full profile \(R(t,r)\), which is determined by \(M(r)\) and \(E(r)\).

**The bridge.** There is no known closed relation between \(Q_{\mathcal D}\) and \(D_A(z)\) that eliminates \(M(r)\) and \(E(r)\). Both quantities are functionals of the same two functions. Any relation between them is a consequence of the shared underlying functions, not a new constraint. The relation is tautological: \(Q_{\mathcal D} = Q_{\mathcal D}[M,E]\) and \(D_A(z) = D_A[M,E]\), so any equation relating them is a consequence of the shared \(M\) and \(E\), not a new physical restriction.

## 4. Bridge result

**The strongest relation actually established.** For LTB with central spherical domains:

- \(Q_{\mathcal D} \leq 0\) for all \(M(r), E(r)\) (Sussman). This is a theorem, not a relation to observables.
- \(D_A(z)\) is determined by the null geodesic in the same \(M(r), E(r)\).
- There is no closed relation \(F(Q_{\mathcal D}, D_A(z), \dot z(z), \ldots) = 0\) that removes \(M(r)\) and \(E(r)\).

**Outcome classification.** This is **Outcome A** (common-metric consistency): both sets of quantities are computed from the same metric and therefore agree with that metric. It is **not Outcome C** (new consistency relation). A new relation would require a constraint that removes or links otherwise independent quantities and has predictive content beyond solving the same metric twice. No such constraint exists for LTB.

## 5. Degrees-of-freedom audit

**Free functions.** LTB with simultaneous big bang has two independent physical functions after gauge fixing: \(M(r)\) and \(E(r)\). If the simultaneous-bang condition is relaxed, a third function \(t_B(r)\) is added.

**Observables.** The angular-diameter distance \(D_A(z)\) is one function of redshift. The redshift drift \(\dot z(z)\) is another. The combination \(D_A(z)\) and \(\dot z(z)\) provides two functions of \(z\). If \(D_A\) and \(\dot z\) are both measured, they provide two constraints on the two functions \(M(r)\) and \(E(r)\), at least in principle. However:

- The map from \((M,E)\) to \((D_A, \dot z)\) is not known to be invertible in closed form.
- The observables are statistically dependent; measurement errors correlate.
- The domain radius \(L\) and the observer position add parameters.
- The simultaneous-bang condition is an additional assumption, not a consequence.

**Identifiability.** With two observables and two free functions, the system is formally exactly determined (not overdetermined). Adding more observables (e.g., lensing, BAO) could overdetermine the system, but the inversion is not established in closed form, and the free-function count is not reduced by any known consistency relation. The parsimony condition \(N_f - N_c < N_o\) is not satisfied by any derived \(N_c > 0\).

**Dependence on assumptions.** If the simultaneous-bang condition is dropped, \(N_f = 3\). If a parametric profile is assumed (e.g., a Gaussian void), \(N_f\) drops to a few parameters, but this is an explicit additional assumption, not a consequence of the equations.

## 6. Adversarial claim table

| Claim | Verdict | Reason |
|---|---|---|
| Redshift drift and shear contribution to \(Q_{\mathcal D}\) automatically determines full \(Q_{\mathcal D}\) | **Falsified** | \(Q_{\mathcal D}\) involves both shear and expansion variance. Shear is not directly observable along a single line of sight without reconstruction. |
| Spatial-averaging commutation rule is equivalent to a boundary-flux law | **Falsified** | The commutation rule is an identity relating averages and their time derivatives. It does not reduce to a surface term because \(\theta\) and \(\sigma^2\) are not divergences (they are quadratic in first derivatives). |
| Stokes' argument directly produces an exact slice-to-null-cone matching equation | **Falsified** | Neither \(\theta^2\) nor \(\sigma^2\) is a divergence. The surface term does not exist in the form claimed. |
| Clarkson–Bassett–Lu or other FLRW null-test statistic is automatically proportional to \(Q_{\mathcal D}\) | **Falsified** | CBL tests test FLRW consistency; they are not proportional to backreaction. A non-zero CBL signal could arise from non-FLRW geometry without backreaction, or vice versa. |
| Nonzero FLRW null test uniquely identifies backreaction or establishes backreaction causes acceleration | **Falsified** | A null test violation indicates non-FLRW geometry. It does not identify the mechanism (backreaction, LTB void, modified gravity, etc.). |
| More observables than free parameters proves identifiability and predictivity | **Falsified** | The map from parameters to observables may be degenerate. Statistical dependence reduces the effective number of independent constraints. |
| Sussman's \(Q_{\mathcal D} \leq 0\) theorem proves all relativistic backreaction vanishes | **Falsified** | Sussman's theorem applies to LTB with central spherical domains. It does not apply to general inhomogeneous spacetimes, nor to non-central domains, nor to Szekeres models with non-zero magnetic Weyl tensor. |

## 7. Controls and falsifier

**FLRW limit.** When \(E(r) = -k r^2/2\) and \(M(r) = (4\pi/3)\rho_0 r^3\), the LTB solution reduces to FLRW. In this limit, \(Q_{\mathcal D} = 0\), and \(D_A(z)\) reduces to the standard FLRW angular-diameter distance. The equations pass the limit check.

**Dimensional and sign checks.** \(Q_{\mathcal D}\) has dimensions of \(H^2\). \(D_A\) has dimensions of length. The redshift is dimensionless. Signs: Sussman's \(Q_{\mathcal D} \leq 0\) is consistent with the standard Buchert formula when the expansion variance does not dominate. The Sussman result is a theorem, not an approximation.

**Domain dependence.** The Sussman theorem holds for any spherical comoving domain containing a symmetry center. If the domain is off-center, or if the domain shape is non-spherical, the theorem does not apply, and \(Q_{\mathcal D}\) may be positive. This is a domain-dependence: the result is prescription-dependent.

**Independent prediction.** A fixed LTB model with specified \(M(r)\) and \(E(r)\) predicts both \(D_A(z)\) and \(\dot z(z)\). An independent test would be to check whether a model that fits \(D_A(z)\) also fits \(\dot z(z)\) without retuning. This is Outcome B (model test), not Outcome C (new relation).

**Falsifier.** A realistic falsifier: if a measurement of \(\dot z(z)\) and \(D_A(z)\) simultaneously yields a pair that cannot be produced by any LTB model with \(Q_{\mathcal D} \leq 0\), then the LTB framework with central spherical domains is excluded. This would be a genuine restriction. However, no such pair has been identified, and the inversion from observables to \((M,E)\) is not established.

## 8. Literature

**Primary sources.**

- **Sussman, R. A.** (2008). "On spatial volume averaging in Lemaître–Tolman–Bondi dust models. Part I." arXiv:0807.1145. **Establishes:** closed expression for \(Q_{\mathcal D}\) in LTB, theorem \(Q_{\mathcal D} \leq 0\) for central spherical domains. This is the key negative result.

- **Buchert, T., van Elst, H., Heinesen, A.** (2022). "The averaging problem on the past null cone in inhomogeneous dust cosmologies." Gen. Rel. Grav. 55, 7. arXiv:2202.10798. **Establishes:** covariant area-averaged equations on past light cones, including effective angular-diameter distance and redshift drift. Does **not** establish a closed relation between spatial \(Q_{\mathcal D}\) and null-cone observables.

- **Gasperini, M., Marozzi, G., Veneziano, G.** et al. on geodesic light-cone (GLC) formalism. **Establishes:** observables directly on the null cone, without a spatial foliation. Suggests backreaction is a coordinate effect. **Does not** connect to Buchert's \(Q_{\mathcal D}\).

- **Heinesen, A., Clifton, T.** (2026). "Observational tests for distinguishing classes of cosmological models." Phys. Rev. D 114, 083510. **Establishes:** new null test for non-FLRW observational relations. **Does not** derive a relation involving \(Q_{\mathcal D}\).

- **Green, S. R., Wald, R. M.** (2011). "A new framework for analyzing the effects of small scale inhomogeneities in cosmology." Phys. Rev. D 83, 084020. **Establishes:** perturbative backreaction is small and traceless. **Does not** resolve the non-perturbative case.

**What each source actually establishes:** none derives a closed, nontrivial relation between spatial \(Q_{\mathcal D}\) and null-cone observables for LTB. Sussman's theorem constrains \(Q_{\mathcal D}\) from above but does not connect it to observables. Buchert et al. provide the formalism but identify additional variables and closure conditions that the equations alone do not fix.

## 9. Research recommendation

**The single most valuable next calculation.** Relax the central-domain assumption in LTB and compute \(Q_{\mathcal D}\) for off-center spherical domains. If \(Q_{\mathcal D} > 0\) is possible for off-center domains, then the Sussman theorem is domain-specific, and the relation between \(Q_{\mathcal D}\) and \(D_A(z)\) may become non-trivial for those domains. The null-cone observables for an off-center observer in LTB are known (the observer is displaced from the symmetry center). The calculation would determine whether there exists an off-center domain for which a closed relation between \(Q_{\mathcal D}\) and \(D_A(z)\) can be derived. If no such relation exists even for off-center domains, the bridge is falsified more generally.

**Why this follows.** The Sussman theorem kills the bridge for central domains by forcing \(Q_{\mathcal D} \leq 0\). But off-center domains have not been analyzed with the same rigor. The calculation is bounded, uses established LTB machinery, and can fail cleanly.

## Status table

| Claim | Status | Evidence or missing step |
|---|---|---|
| Spatial Buchert equations | **Established** | Standard formalism (Buchert 2000, 2001). |
| Light-cone propagation equations | **Established** | Null geodesics in LTB (Ref. [2], Ref. [8]). |
| LTB spatial-to-null relation | **Not derived** | No closed relation eliminates \(M(r), E(r)\). |
| Relation specifically constraining \(Q_{\mathcal D}\) | **Falsified** | Sussman: \(Q_{\mathcal D} \leq 0\) for central domains; no connection to \(D_A(z)\). |
| Independent predictive content | **Falsified** | Any relation is tautological (shared \(M, E\)). |
| Observational falsifier | **Conditional** | A \((D_A, \dot z)\) pair incompatible with any LTB model. Not identified. |

**Final principle.** The common spacetime guarantees mutual consistency of its calculated quantities. For LTB with central spherical domains, that consistency cannot be expressed as a new, closed, observable restriction without hiding the missing information in freely adjustable functions. The bridge is not derived. It is falsified for the specified class.
