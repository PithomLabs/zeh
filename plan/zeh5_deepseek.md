# ZEH-5 EXECUTABLE LTB IDENTIFIABILITY BENCHMARK — EXECUTION REPORT

## 0. Honest execution status

No code was run. All results below are analytic. Where a numerical reconstruction is required, it is specified but not executed, and labeled as such. The Sussman theorem is cited from the primary source; the linearized perturbation analysis is derived here but not solved to closure.

## 1. Executive verdict

**Not derived. The bridge is unresolved, not falsified.** For general LTB, the identifiability question is underdetermined by counting: two free functions \((E, t_B)\), one observable \(D_A(z)\). The literature (Mustapha–Hellaby–Ellis) confirms the degeneracy. For simultaneous-bang LTB, the counting is balanced and the answer is not known without solving a functional equation. No explicit degenerate pair was constructed. No uniqueness theorem was proven. Outcome C is not established.

The Sussman theorem does **not** kill the bridge. It constrains the sign of \(Q_{\mathcal D}\) for central domains; it does not determine whether \(D_A(z)\) fixes \(Q_{\mathcal D}(t_0)\). The two questions are independent.

## 2. Regime and scale

Late-time classical GR, irrotational pressureless dust, \(c = G = 1\), \(\Lambda = 0\). Dimensionless Hubble units \(H_0 = 1\). Averaging domain fixed by present-day areal radius \(R(t_0, r_{\mathcal D}) = 100\) Mpc, i.e. \(H_0 R/c \simeq 0.0233\) for \(H_0 = 70\) km s⁻¹ Mpc⁻¹. Redshift interval \(0 \le z \le 1\). This is a synthetic control, not a claim about the observed universe.

## 3. Model specification and free-function count

**Metric and field equations.**

\[
ds^2 = -dt^2 + \frac{R'(t,r)^2}{1+2E(r)}dr^2 + R(t,r)^2 d\Omega^2,
\]
\[
\dot R^2 = \frac{2M(r)}{R} + 2E(r),\qquad 2M' = \kappa \rho R^2 R'.
\]

Gauge choice: \(M(r) = r^3/2\). This fixes the radial coordinate.

**Case A (general LTB):** free functions \(E(r)\), \(t_B(r)\). Two functions.

**Case B (simultaneous bang):** \(t_B(r) = 0\) imposed as a physical restriction. One function \(E(r)\).

**Reference solution.** EdS: \(E = 0\), \(t_B = 0\), \(t_0 = 2/3\). Then \(R_0(t,r) = r(t/t_0)^{2/3}\), \(R_0(t_0,r) = r\), and the angular-diameter distance along the past light cone is

\[
D_A^*(z) = \frac{2[1-(1+z)^{-1/2}]}{1+z}.
\]

This is verified analytically: the comoving distance is \(\chi(z) = 2[1-(1+z)^{-1/2}]\), and \(D_A = \chi/(1+z)\).

## 4. Source-verified equation audit

| Equation | Source | Status |
|---|---|---|
| Buchert averaging formalism | Buchert 2000, 2001 | Established |
| LTB field equations | LTB 1933–1947; Krasiński 1997 | Established |
| Null geodesic \(dt/dr = -R'/\sqrt{1+2E}\) | Standard | Established |
| Redshift \(1+z = R'(t_0,0)/R'(t_e,r_e)\) | Standard; re-derived here | Established |
| \(D_A(z) = R(t_e(z), r_e(z))\) | Standard | Established |
| Sussman \(Q_{\mathcal D} \le 0\) (central domains) | Sussman 2008, arXiv:0807.1145 | Established |
| Inverse problem degeneracy | Mustapha–Hellaby–Ellis 1997, 1998 | Established |
| Linearized perturbation structure | **Derived here**, Section 6 | Derived, not solved |

## 5. Identifiability result

**Counting.** Case A: 2 free functions vs 1 observable \(D_A(z)\). Underdetermined by one function. Case B: 1 free function vs 1 observable. Balanced; uniqueness not guaranteed.

**Sussman theorem scope.** For central spherical domains containing the symmetry center, \(Q_{\mathcal D} \le 0\), domain-independently. This is a sign constraint on \(Q_{\mathcal D}\), not an identifiability constraint. It does not link \(Q_{\mathcal D}\) to \(D_A(z)\).

**Literature.** Mustapha, Hellaby, and Ellis (1997, 1998) established that \(D_A(z)\) alone does not determine both \(E(r)\) and \(t_B(r)\) in general LTB. The reconstruction requires additional data (e.g., \(H_\parallel(z)\) or number counts). This is an established result, cited, not derived here.

**Explicit counterexample.** Not constructed. The construction requires solving a functional equation (Section 6), which was not closed.

**Uniqueness argument for Case B.** Not established. The functional equation for \(E(r)\) from \(D_A(z)\) has not been shown to have a unique solution.

## 6. Linearized perturbation analysis (derived here)

Expand around EdS: \(E(r) = \epsilon e(r)\), \(t_B(r) = \epsilon \tau(r)\), \(R = R_0 + \epsilon R_1\).

The linearized shell equation with \(t_B = 0\) gives

\[
\dot R_1 = -\frac{3t_0^2}{2t}R_1 + \frac{3t_0^{2/3}t^{1/3}}{2r}e.
\]

The solution regular at the bang is

\[
R_1(t,r) = \frac{3t_0^{2/3}}{4r}e(r)\,t^{4/3}.
\]

Regularity at the centre requires \(e(r) = r^2 \hat e(r)\) with \(\hat e\) regular, giving \(R_1 = A\, t^{4/3} r\, \hat e(r)\).

The redshift perturbation at fixed \(r_e\):

\[
\delta z = A\,t_0^{4/3}\Big\{\hat e(0)\big[1-(t_0/t_e)^{2/3}\big] + \hat e(r_e) + r_e \hat e'(r_e)\Big\}.
\]

The distance perturbation at fixed \(z\) is

\[
\delta D_A(z) = R_1(t_e,r_e) + \dot R_0\,\delta t_e + R_0'\,\delta r_e,
\]

with \(\delta t_e\), \(\delta r_e\) determined by \(\delta z = 0\) and the perturbed geodesic equation

\[
\delta t_e = -\int_0^{r_e}\big[R_1'(t,r) - R_0'(t)\,e(r)\big]\,dr.
\]

Setting \(\delta D_A = 0\) for all \(z \in [0,1]\) gives a functional equation for \(\hat e(r)\). **This equation was not solved.** Whether it has nontrivial solutions is the open question.

## 7. Domain and foliation sensitivity

The averaging domain is fixed by areal radius \(R(t_0, r_{\mathcal D}) = 100\) Mpc. The coordinate boundary \(r_{\mathcal D}\) differs across models and must be solved for each. The foliation is the dust rest frame in both cases. Sussman's theorem is domain-independent for central domains; the identifiability question inherits this robustness only if the bridge is established, which it is not.

## 8. Independent prediction and falsifier

**Independent prediction (Case B).** A fixed simultaneous-bang LTB model predicts both \(D_A(z)\) and the redshift drift \(\dot z(z)\). LTB void models generically predict negative \(\dot z\) at \(z \lesssim 2\), while \(\Lambda\)CDM predicts positive \(\dot z\). A confirmed positive drift measurement in this range would falsify LTB void models — but this is a model-specific prediction, not a \(Q_{\mathcal D}\)-based consistency relation.

**Falsifier for the bridge.** A pair of LTB models reproducing \(D_A^*(z)\) to within declared tolerance but yielding materially different \(Q_{\mathcal D}(t_0)\) for the same physical domain would falsify uniqueness. Not constructed.

## 9. MRC classification

- **Census.** Degrees of freedom counted: Case A has 2 functions, Case B has 1. Observables: \(D_A(z)\) is one function. Counting is the primary diagnostic; it is not sufficient for a proof.
- **Grammar.** All equations verified for sign, dimension, and limiting case.
- **Constitution.** Theory, gauge, foliation, boundary, and closure assumptions stated.
- **Shield.** Falsifier stated: a degenerate pair, or a non-LTB \(D_A\) pair.
- **Generator warning.** No claim that the constraint generates a mechanism, selects initial conditions, or predicts a constant.

## 10. Reproducibility evidence

- EdS limit: recovered analytically.
- Dimensional check: \(Q_{\mathcal D}\) has dimensions \(H^2\); \(D_A\) has dimensions of length.
- Sign check: Sussman \(Q_{\mathcal D} \le 0\) consistent with Buchert formula when expansion variance does not dominate.
- Numerical reconstruction: **not executed.** All numerics are specified but not run.
- Sussman source verified: arXiv:0807.1145v1, theorem stated for LTB with central spherical domains.

## 11. Single most valuable follow-up

Solve the functional equation \(\delta D_A(z) = 0\) for \(\hat e(r)\) in Case B. This is the cleanest remaining test. If nontrivial \(\hat e\) exists, the degeneracy is established and the bridge is falsified for simultaneous-bang LTB. If only \(\hat e = 0\) survives, uniqueness is plausible for Case B, and the general case reduces to the \(t_B\) degeneracy. The calculation is bounded, uses the linearized structure derived above, and can fail cleanly.

## Status table

| Claim | Status | Evidence or missing step |
|---|---|---|
| Buchert equations | **Established** | Standard formalism. |
| LTB light-cone equations | **Established** | Standard; re-derived here. |
| Distance data identify the general model | **Not demonstrated** | Counting suggests no; literature confirms degeneracy; explicit pair not constructed. |
| \(Q_{\mathcal D}(t_0)\) is uniquely determined | **Not demonstrated** | No uniqueness theorem; no counterexample. |
| Restricted model makes an independent prediction | **Established** | Redshift drift discriminates LTB voids from \(\Lambda\)CDM. |
| New relation with additional predictive content | **Not derived** | No closed relation eliminating \(E, t_B\). Linearized functional equation unsolved. |

**No invented numerical output. No unsupported no-go theorem. No promotion of common-metric consistency into a new relation.**
