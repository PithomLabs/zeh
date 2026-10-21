# ZEH-6A — ANALYTICAL NON-IDENTIFIABILITY THEOREM AND PHYS FORMALIZATION

## 1. Executive verdict

**UNRESOLVED.** The claim that a fixed \(D_A(z)\) does not uniquely determine \(Q_{\mathcal D}(t_0)\) in general LTB is **plausible but not proved**. The Mustapha–Hellaby–Ellis (MHE) degeneracy establishes that \(D_A(z)\) does not determine the model functions \((E, t_B)\). But the question of whether \(Q_{\mathcal D}(t_0)\) is invariant under the MHE degeneracy is a distinct mathematical question that has not been resolved in the literature or in this investigation. A constructive proof requires either (a) an explicit degenerate family with different \(Q_{\mathcal D}(t_0)\), or (b) a proof that the MHE direction is orthogonal to the \(Q_{\mathcal D}\) gradient. Neither was completed. The obstruction is identified precisely in Section 6.

## 2. Exact theorem or conjecture in mathematical form

**Conjecture (Non-Identifiability of \(Q_{\mathcal D}\)).** Let \(\mathcal{M}\) be the class of regular, expanding LTB dust spacetimes with \(M(r) = r^3/2\), \(\Lambda = 0\), simultaneous bang \(t_B(r) = 0\), central observer, and a fixed present-day areal-radius domain \(R(t_0, r_{\mathcal D}) = R_{\text{phys}}\). Let \(D_A^*(z)\) be any fixed distance–redshift function on \(z \in [0,1]\) compatible with a regular EdS vertex. Then there exist at least two distinct admissible models \(\mathcal{M}_1, \mathcal{M}_2 \in \mathcal{M}\) with

\[
D_A^{\mathcal{M}_1}(z) = D_A^{\mathcal{M}_2}(z) = D_A^*(z) \quad \forall z \in [0,1],
\]

but

\[
Q_{\mathcal D}^{\mathcal{M}_1}(t_0) \neq Q_{\mathcal D}^{\mathcal{M}_2}(t_0).
\]

**Status: conjectural.** The MHE degeneracy provides the freedom in \((E, t_B)\). Whether this freedom extends to \(Q_{\mathcal D}(t_0)\) is not established.

## 3. Physical assumptions, conventions, regime

| Item | Specification |
|---|---|
| Theory | Classical GR, \(\Lambda = 0\), \(c = G = 1\) |
| Matter | Irrotational pressureless dust |
| Gauge | \(M(r) = r^3/2\) (exactly; not \(r^{3/2}\)) |
| Metric | \(ds^2 = -dt^2 + R'^2/(1+2E)\,dr^2 + R^2 d\Omega^2\) |
| Shell equation | \(\dot R^2 = 2M/R + 2E\) |
| Reference | EdS: \(E=0\), \(t_B=0\), \(t_0=2/3\), \(R = r(3t/2)^{2/3}\) |
| Observer | Central, \(r=0\) |
| Domain | Comoving, central, \(R(t_0, r_{\mathcal D}) = R_{\text{phys}}\) |
| Target | \(D_A^*(z) = 2[1-(1+z)^{-1/2}]/(1+z)\), \(0 \le z \le 1\) |
| Free functions | \(E(r)\) (Case B), \((E(r), t_B(r))\) (Case A) |
| Regularity | \(E(r) = O(r^2)\), \(1+2E>0\), \(R'>0\), \(\rho>0\), no shell crossing |

## 4. Derivation: the LTB light-cone system

**Null geodesic equation.** Along radial null geodesics:

\[
\frac{dt}{dr} = -\frac{R'(t,r)}{\sqrt{1+2E(r)}}.
\]

**Redshift.** The wave vector \(k^a\) satisfies the null condition and the geodesic equation. For radial geodesics with \(k^t < 0\) (past-directed), \(k^r > 0\):

\[
k^t = -\frac{R'}{\sqrt{1+2E}} k^r, \qquad
\frac{dk^t}{dr} = +\frac{\dot R'}{\sqrt{1+2E}} k^t.
\]

Integrating from the emitter at \((t_e, r_e)\) to the observer at \((t_0, 0)\):

\[
1+z = \exp\left(\int_0^{r_e} \frac{\dot R'(t(r), r)}{\sqrt{1+2E(r)}} \, dr\right).
\]

This reproduces the EdS limit \(1+z = (t_0/t_e)^{2/3}\).

**Distance.** The angular-diameter distance is

\[
D_A(z) = R(t_e(z), r_e(z)).
\]

**System summary.** The pair \((t_e(z), r_e(z))\) is determined by the coupled ODEs for \(dt/dr\) and \(d\ln(1+z)/dr\), with \(D_A = R(t_e, r_e)\). The free input is \(R(t,r)\), which is determined by \((E(r), t_B(r))\) through the shell equation

\[
t - t_B(r) = \int_0^{R(t,r)} \frac{d\tilde R}{\sqrt{2M(r)/\tilde R + 2E(r)}}.
\]

## 5. The MHE degeneracy and its relevance

**Established result (MHE 1997; MNC 2000).** The functional \(E(r), t_B(r) \mapsto D_A(z)\) is not injective. There exists a functional direction \((\delta E, \delta t_B)\) such that \(\delta D_A(z) = 0\) for all \(z\), with \((\delta E, \delta t_B) \not\equiv 0\).

**Scope.** The degeneracy is established for general LTB with central observer. The size of the degenerate family is at least one functional dimension.

**Relevance to \(Q_{\mathcal D}\).** The question is whether \(Q_{\mathcal D}(t_0)\) varies along this degenerate direction. This is a distinct question because \(Q_{\mathcal D}\) is a specific functional of \((E, t_B)\) and their derivatives; the MHE direction might be orthogonal to the \(Q_{\mathcal D}\) gradient, in which case \(Q_{\mathcal D}\) would be determined by \(D_A\) despite the model degeneracy.

## 6. The principal obstruction

**The calculation that would resolve the conjecture.** Compute the variation of \(Q_{\mathcal D}(t_0)\) along the MHE degenerate direction:

\[
\delta Q_{\mathcal D} = \left.\frac{d}{d\epsilon} Q_{\mathcal D}[E + \epsilon\, \delta E, t_B + \epsilon\, \delta t_B]\right|_{\epsilon=0}.
\]

If \(\delta Q_{\mathcal D} \neq 0\) for some admissible MHE direction, the conjecture is proved. If \(\delta Q_{\mathcal D} = 0\) for all MHE directions, the conjecture is refuted.

**Why this was not completed.** The MHE direction \((\delta E, \delta t_B)\) is not given in closed form; it is defined implicitly as the kernel of the functional derivative of \(D_A\) with respect to \((E, t_B)\). Computing it requires solving a functional equation that has not been solved in closed form in the literature. The linearized version of this equation (around EdS) is tractable but was not completed here.

**What is needed.** Either:
1. An explicit construction of the MHE kernel in a restricted class (e.g., linearized around EdS, or a specific parametric family), followed by an evaluation of \(\delta Q_{\mathcal D}\); or
2. A proof that the MHE kernel is contained in the kernel of \(\delta Q_{\mathcal D}\) (which would refute the conjecture).

## 7. Linearized structure (partial progress)

Expand around EdS: \(E(r) = \epsilon\, e(r)\), \(t_B(r) = \epsilon\, \tau(r)\). The linearized shell equation for simultaneous bang \((\tau = 0)\) gives

\[
R_1(t,r) = \frac{3 t_0^{2/3}}{4 r} e(r)\, t^{4/3}
\]

for the solution regular at the bang. The linearized distance perturbation is

\[
\delta D_A(z) = R_1(t_e, r_e) + \dot R_0(t_e, r_e)\, \delta t_e + R_0'(t_e, r_e)\, \delta r_e,
\]

with \(\delta t_e\) and \(\delta r_e\) determined by the linearized null geodesic and redshift equations:

\[
\delta t_e = -\int_0^{r_e} \left[R_1'(t(r), r) - R_0'(t(r))\, e(r)\right] dr,
\]

\[
\delta(\ln(1+z)) = \int_0^{r_e} \left[\delta \dot R'(t(r), r) - \dot R_0'(t(r))\, e(r)\right] dr.
\]

Setting \(\delta D_A(z) = 0\) for all \(z\) gives a functional equation for \(e(r)\) (simultaneous bang) or for \((e(r), \tau(r))\) (general).

**Status of the linearized equation.** Not solved. The equation is a linear integral equation for \(e(r)\) (or \((e, \tau)\)). Its kernel determines the linearized MHE degeneracy. The kernel's relationship to \(\delta Q_{\mathcal D}\) was not computed.

## 8. What would constitute success

**Constructive theorem.** Two admissible LTB models \(\mathcal{M}_1, \mathcal{M}_2\) with the same exact \(D_A^*(z)\) on \([0,1]\) and different \(Q_{\mathcal D}(t_0)\) on the same physical domain and foliation.

**Non-constructive theorem.** A proof that the MHE kernel contains a direction with nonzero \(\delta Q_{\mathcal D}\), without exhibiting the models explicitly.

**Refutation.** A proof that \(\delta Q_{\mathcal D} = 0\) for all MHE directions, i.e., that \(D_A(z)\) uniquely determines \(Q_{\mathcal D}(t_0)\) within the specified class.

## 9. Claim-status table

| Claim | Status | Evidence or missing step |
|---|---|---|
| Buchert equations | **Established** | Buchert 2000, 2001 |
| LTB light-cone equations | **Established** | Standard; re-derived here |
| Redshift formula \(1+z = \exp(\int \dot R'/\sqrt{1+2E}\,dr)\) | **Derived here** | Matches EdS limit |
| MHE degeneracy in \((E, t_B)\) | **Established** | Mustapha–Hellaby–Ellis 1997 |
| Sussman sign theorem | **Established** | Sussman 2008, arXiv:0807.1145 |
| Linearized shell solution for \(R_1\) | **Derived here** | Section 7 |
| Linearized functional equation for MHE kernel | **Stated, not solved** | Section 7 |
| \(\delta Q_{\mathcal D} \neq 0\) along MHE direction | **Unresolved** | Not computed |
| \(Q_{\mathcal D}(t_0)\) uniquely determined by \(D_A(z)\) | **Unresolved** | Depends on kernel computation |
| Constructive degenerate pair | **Not constructed** | Requires solving the functional equation |

## 10. MRC/MRC2 evaluation

**MRC classification.** The investigation asked mathematics to play the role of **constitution** (an identifiability constraint). This is a legitimate role. The result is a precise statement of the obstruction, not a derivation of a physical mechanism.

**MRC2 scientific merit.** The negative result (if established) would be a genuine contribution: it would show that the backreaction is not readable from distance data alone in the specified model class, even in principle. The positive result (if established) would be equally valuable: it would show that distance data do determine the backreaction, closing the identifiability question. The current status is **unresolved**, with the obstruction identified.

## 11. Literature comparison

| Source | What it establishes | What it leaves open |
|---|---|---|
| Mustapha–Hellaby–Ellis 1997; MNC 2000 | \(D_A(z)\) does not determine \((E, t_B)\) | Whether \(Q_{\mathcal D}(t_0)\) varies within the degenerate family |
| Sussman 2008 (arXiv:0807.1145) | \(Q_{\mathcal D} \le 0\) for central domains in elliptic LTB | Whether \(D_A\) determines \(Q_{\mathcal D}\) |
| Buchert–van Elst–Heinesen 2022 (arXiv:2202.10798) | Covariant null-cone averaging formalism | No connection to spatial \(Q_{\mathcal D}\) |
| ZEH-5 execution report | Linearized shell solution; MHE kernel not solved | Same obstruction |

**Novelty assessment.** The specific question "does \(D_A(z)\) uniquely determine \(Q_{\mathcal D}(t_0)\)?" has not been addressed in the primary literature. The MHE degeneracy addresses the model functions, not \(Q_{\mathcal D}\). The contribution is the sharpening of the question and the identification of the obstruction, not the resolution.

## 12. Phys-compatible artifact structure

The following paths would constitute the artifact. No code was executed; the artifact is specified but not built.

- `AGENTS.md` — mission, scope, MRC/MRC2 rules, status definitions
- `manifest.json` — theorem ID, dependency graph, status flags
- `protocol/derivation_test.go` — structural checks:
  - EdS limit: \(Q_{\mathcal D} = 0\) when \(E = 0\), \(t_B = 0\)
  - Dimensional consistency of \(Q_{\mathcal D}\) and \(D_A\)
  - Regularity: \(E(r) = O(r^2)\), \(1+2E>0\)
  - Redshift formula: matches EdS limit
  - **Not included:** verification of the MHE kernel or the \(\delta Q_{\mathcal D}\) computation, because these are not analytically closed

## 13. Limitations and non-claims

- **No claim** that the conjecture is true. It is plausible but unproved.
- **No claim** that the conjecture is false. The MHE degeneracy might be orthogonal to \(Q_{\mathcal D}\).
- **No claim** that the result extends to non-simultaneous-bang LTB, non-central domains, or Szekeres models.
- **No claim** of empirical relevance. This is a mathematical control problem.
- **No claim** that the linearized analysis is complete. The functional equation was stated, not solved.

## 14. Single most valuable follow-up

**Solve the linearized functional equation for the MHE kernel in simultaneous-bang LTB, then compute \(\delta Q_{\mathcal D}\) along the kernel.** This is the smallest bounded calculation that can resolve the conjecture. If \(\delta Q_{\mathcal D} \neq 0\) for some kernel direction, the conjecture is proved constructively. If \(\delta Q_{\mathcal D} = 0\) for all kernel directions, the conjecture is refuted. Either outcome is a paper-level result.

## 15. Verdict

**UNRESOLVED.** The conjecture is precisely stated. The MHE degeneracy provides the freedom in the model functions. Whether this freedom extends to \(Q_{\mathcal D}(t_0)\) is not established. The obstruction is a functional equation whose kernel has not been computed. The next step is to solve that equation in the linearized regime.

A precise unresolved result is preferable to an unsupported theorem claim. This is a precise unresolved result.
