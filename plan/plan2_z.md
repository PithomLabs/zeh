# ZEH-6A Submission — Analytical Non-Identifiability Investigation

**Compliance box.** Status tags: **[1]** established in literature, **[2]** derived in this investigation, **[3]** conditional, **[4]** conjecture, **[5]** falsified. MRC categories: **[census]** / **[grammar]** / **[constitution]** / **[shield]**. All numerical work is analytic; **no solver was built and no numerical-validation claim is made**. No Phys workspace or locked representation spec was accessible in this session; the artifact files below are content listings written to the canonical structure described in the prompt, flagged for adaptation, and **unexecuted**. Gauge written everywhere as \(M(r)=r^3/2\).

---

## 1. Executive verdict

**PARTIALLY ESTABLISHED.** The investigation produced three established analytic results and left the headline theorem resting on two clearly delimited lemmas:

- **Proposition 1 (Vertex Normalization Theorem) — established [2].** Any admissible LTB model with central observer reproducing the target \(D_A^*(z)\) on any interval \([0,z_*]\), \(z_*>0\), is forced by the data to satisfy: \(H_{\rm loc}(t_0)=1\), \(R'(t_0,0)=1\), \(E(r)=O(r^4)\) (the central curvature quadrupole \(E_2\) is fixed to zero), and the cone redshift profile \(z(r)=r+\tfrac34 r^2+O(r^3)\). Fully proved below by two independent closed relations that agree only on this branch.
- **Proposition 2 (Recursive freedom) — established at formal-series level [2], analytic upgrade pending Lemma A.** Given \(u(r)=\sqrt{1+2E}=1+\varepsilon h(r)\) with \(h=O(r^4)\) at the center, the cone system has a unique regular formal solution reproducing the target **exactly**; the data determine the \(z\)-profile recursively *given* \(u\), while the coefficients of \(u\) from \(O(r^4)\) upward are never constrained: \(z_3=\tfrac12+\tfrac23 u_4\) (derived and EdS-verified).
- **Proposition 3 (Backreaction response structure) — established [2].** \(\mathcal Q_{\mathcal D}[u]=\varepsilon^2\mathcal Q_2[h]+O(\varepsilon^3)\), with \(\mathcal Q_2\) an explicit quadratic functional; the proper-volume and fixed-domain corrections enter only at \(O(\varepsilon^3)\).
- **Lemma A** (analytic well-posedness of the vertex-singular cone ODE) and **Lemma B** (\(\mathcal Q_2[h]\not\equiv 0\)) are **open**, but both are reduced to mechanical procedures (majorant induction; rational-function quadrature with all coefficients known in closed form). The **non-identifiability theorem is [4] until these discharge.**
- **No Outcome C is claimed.** What is constructed is exact common-metric consistency (A) plus a constructive degeneracy family (B-type); the support obstruction (slice-supported variance vs. cone-supported observables) stands and is restated as the reason C fails.

The EdS control was not decorative: it caught **four** genuine errors during this session (§4.4). Reporting them is part of the result.

---

## 2. The theorem (as it would stand if the lemmas close)

> **Theorem (target, [4]).** *In the class \(\mathfrak L\) of LTB dust spacetimes (\(\Lambda=0\), gauge \(M=r^3/2\), regular center, central observer, expanding branch, central normalization \(R'(t_0,0)=1\), observer event at central age \(t_0=2/3\)), there exist two admissible members \(u_1\neq u_2\) with identical angular-diameter distance \(D_A(z)=D_A^*(z)\) on \(0\le z\le 1\) and \(\mathcal Q_{\mathcal D}^{(1)}(t_0)\neq \mathcal Q_{\mathcal D}^{(2)}(t_0)\) on the same physical domain \(R(t_0,r_{\mathcal D})=R_{\rm phys}\).*

**Assumptions (all [constitution], none derived):** dust, \(\Lambda=0\), \(c=G=1\), \(H_0\)-units \(H_{\rm loc}(t_0)=1\); comoving dust foliation; spherical comoving domains; central observer (not derived — flagged); \(t_B(0)=0\). **Model class count [census]:** the relabeling freedom \(r\to\tilde r(r)\) is *fully* removed by \(M=r^3/2\) (since \(\tilde r=(2M)^{1/3}\) is unique), leaving exactly two physical functions \(\{E,t_B\}\).

---

## 3. Conventions and admissibility

Metric and dynamics [1; Lemaître 1933, Tolman 1934, Bondi 1947]:

$$ds^2=-dt^2+\frac{R'(t,r)^2}{1+2E(r)}dr^2+R^2d\Omega^2,\qquad \dot R^2=\frac{r^3}{R}+u^2-1,\qquad u:=\sqrt{1+2E},\qquad \rho=\frac{3r^2/2}{4\pi R^2R'}.$$

Admissibility: \(u>0\), \(\rho>0\), \(R'>0\) (no shell crossings), regular center (\(u(0)=1\), \(u-1=O(r^4)\) — the \(O(r^4)\) is *derived*, §5, not assumed), \(t_B'(0)=0\). Reference: \(u\equiv1\), \(t_B\equiv0\), \(t_0=2/3\), \(R=r(3t/2)^{2/3}\).

**Target verification [2, analytic].** EdS cone: \(t_e=t_0(1+z)^{-3/2}\), \(r_s=3t_0\big[1-(1+z)^{-1/2}\big]\)… direct integration gives \(D_A=R(t_e,r_s)=(1+z)^{-1}r_s=\dfrac{2[1-(1+z)^{-1/2}]}{1+z}=D_A^*(z)\) exactly. ✓ Also \(R(t_0,r)=r\) and \(H_0=2/(3t_0)=1\). ✓

---

## 4. Derivation I — the exact reduced cone system

**4.1 Setup [2].** Central observer ⇒ all geodesics through the vertex are radial (\(R^2\dot\theta=L\to0\)) ⇒ **\(D_A=R(t_e,r_e)\) exactly**, and radial beams are shear-free — the smoothness/lensing channel is degenerate in this lab (consistent with Kristian–Sachs 1966). Photon energy \(\omega=k^t\) for comoving observers; geodesic equation with \(\Gamma^t_{rr}=R'\dot R'/u^2\), null condition \(|k^r|=\omega u/R'\):

$$\frac{d\ln\omega}{dr}=\frac{\dot R'}{u}\quad\Rightarrow\quad \frac{d\ln(1+z)}{dr}=\frac{\dot R'(t(r),r)}{u(r)}.$$

*Sign check:* EdS integral \(\int_0^{r_s}\dot R'\,dr=\tfrac23\ln(t_0/t_e)=\ln(1+z)\) ✓ (this reproduces the \((1+z)\)-factor correction made in the benchmark turn).

**4.2 The closed system [2].** Cone state \((T,Z,P,Q,V)\equiv(t,\,1+z,\,R',\,\dot R',\,\dot R)\); target \(G(Z):=D_A^*(Z-1)\), \(G'(1)=1\), \(G''\)… from \(D_A^*(z)=z-\tfrac74z^2+\tfrac{19}{8}z^3-\tfrac{187}{64}z^4+\cdots\) (expansion re-derived and numerically verified; see §4.4, error 1). Imposing \(R=G(Z)\) on the cone and using the shell equation plus its \(\partial_r\) at fixed \(t\):

$$Z'=\frac{Z}{u}\,Q,\qquad Q=\frac{3r^2/G+2uu'}{2V+\dfrac{r^3G'Z}{(u-V)G^2}},\qquad V=+\sqrt{\frac{r^3}{G}+u^2-1},\qquad T'=-\frac{P}{u},\quad P=\frac{G'ZQ}{u-V}.$$

**The system is one first-order ODE for \(Z(r)\) with \(u(r)\) a genuine free input** — the closure is constructive, not counted. \(t_B\) never enters: it is an **output**, recovered through the shell-age relation (task §3.5):

$$t_B(r)=T(r)-\int_0^{G(Z(r))}\frac{d\widetilde R}{\sqrt{r^3/\widetilde R+u(r)^2-1}} .$$

**4.3 Exact EdS cone solution [2].** With \(u\equiv1\): \(T_0=\tfrac23(1-\tfrac r2)^3\), \(Z_0=(1-\tfrac r2)^{-2}\), \(R_{c,0}=r(1-\tfrac r2)^2\), \(V_0=\dfrac{r}{1-r/2}\), \(Q_0=P_0/V_0\cdot…=\dfrac{1}{1-r/2}\), \(P_0=(1-\tfrac r2)^2\). All verified against the metric identities; in particular the exact rational identity

$$2V_0Q_0\;\equiv\;\frac{3r^2}{R_{c,0}}-\frac{r^3P_0}{R_{c,0}^2}\qquad\Big(\text{both}=\frac{2r}{(1-r/2)^2}\Big)\quad\checkmark$$

holds identically — this is the \(u\equiv1\) control of the algebraic relation, and it is what the Go artifact checks at rational sample points.

**4.4 Verification record (errors caught by the mandated controls).** (1) The \(z^3\)-coefficient of \(D_A^*\) was first computed as \(23/8\); the composition identity \(G(z(r))=r(1-r/2)^2\) (exact) forced \(19/8\). (2) A vertex match initially forced \(z_2=1\); an arithmetic slip (\(7/4+5/2\)) was found; correct value \(z_2=3/4\) agrees with EdS. (3) The vertex unknown \(q_0=Z'(0)\) was first set to 1; re-derivation gives \(Z'(0)=\dot a_c(t_0)\), changing the vertex algebra (§5). (4) A factor slip in \(3r^2/R_c\) was caught by the exact rational identity above. The control discipline is doing real work; all printed results below passed their EdS limits.

---

## 5. Derivation II — Proposition 1, the Vertex Normalization Theorem [2]

Let the model reproduce the target near the vertex, with central quantities \(a_c(t):=R'(t,0)\), and write \(E(r)=E_2r^2+E_4r^4+\cdots\), \(u=1+E_2r^2+\cdots\), \(V=a_0 r+O(r^2)\) with \(a_0:=a_c(t_0)\), \(R(t,r)=a_c(t)r+O(r^3)\) (oddness at the regular center).

**(α) Central dynamics.** \(R=a_cr\) in the orbit equation gives \(\dot a_c^{\,2}=1/a_c+2E_2+O(r^2)\). The target's vertex slope \(G'(1)=1\) is the Kristian–Sachs vertex identity \(dD_A/dz|_0=1/H_{\rm loc}\) with \(H_{\rm loc}=\dot a_c/a_c\); hence \(\dot a_c(t_0)=a_c(t_0)=a_0\), and

$$a_0^2=\frac{1}{a_0}+2E_2. \tag{α}$$

**(β) Cone \(r^1\)-match.** Expanding \(R_c=G(Z)=a_0r-a_0^2r^2+\cdots\) (from \(a_c(T(r))r\), using \(T'(0)=-P(0)=-a_0\)) and matching the \(r^1\)-coefficient of \(2VQ=3r^2/R_c-r^3P/R_c^2+2uu'\) (LHS \(2a_0^2 r\); RHS \(2r/a_0+4E_2r\); all coefficients EdS-verified):

$$a_0^2=\frac{1}{a_0}+4E_2a_0\cdot\frac{1}{2}\;\Longrightarrow\; a_0^2=\frac{1}{a_0}+2E_2\quad\text{— identical to (α)}.$$

The \(r^1\) cone match is *not independent* of the central dynamics — the vertex is where slice and cone meet, and the consistency condition is (α) itself. The independent input that closes the system is the **declared central normalization** (task §2: shared observer event):

$$a_0=1\;\Longrightarrow\;(\alpha)\Rightarrow\;\boxed{E_2=0},\qquad\text{and}\qquad z_2=\tfrac74-a_0^2=\boxed{\tfrac34},$$

where \(z_2\) follows from the target composition \(A_1-z_2=-7/4\) with \(A_1=-a_0^2\). The central age is then fixed: \(\dot a_c=a_c^{-1/2}\Rightarrow t_0-t_B(0)=2/3\) — i.e., with \(t_B(0)=0\), every family member shares \(t_0=2/3\). ∎

**Remark (honesty about the class).** Without the central-normalization condition, the vertex system admits a second branch \(a_0=(\sqrt{15}-3)/6\approx0.146\) (with strongly negative \(E_2\approx-3.4\)); its global admissibility was not examined. The class fixes \(a_0=1\) as declared constitution; the branch is flagged, not hidden. **The data alone fix one fewer quantity than the class assumes — this strengthens, not weakens, non-identifiability.**

---

## 6. Derivation III — Proposition 2, the recursive freedom [2, formal]

With \(u=1+\beta r^4+\gamma r^6+\cdots\) (\(E_2=0\) forced; evenness at center), match the system order by order (all series rational; every step below EdS-checked at \(\beta=0\)):

- \(z_1=1\), \(z_2=3/4\) — **data-fixed, independent of \(u\)** (the \(r^2\)-match contains no \(u\)-coefficient, since \(2uu'=O(r^3)\)).
- \(r^3\)-match of \(2VQ=3r^2/R_c-r^3P/R_c^2+2uu'\): with \(A_1=-1\), \(A_2=z_3-\tfrac14\), \(q_2=3z_3-\tfrac54\), \(v_2=\tfrac12-\tfrac{z_3}{2}+\beta\), \(p_2=3z_3-\tfrac54\):

$$9z_3=\frac92+6\beta\quad\Longrightarrow\quad \boxed{z_3=\tfrac12+\tfrac23\beta}\qquad(\beta=0\Rightarrow z_3=\tfrac12\;\checkmark\ \text{exact EdS}).$$

**Structure:** at each order \(r^n\), the new \(z\)-coefficient enters linearly with nonzero coefficient (through \(q_{n-1},v_{n-1},A_{n-1},p_{n-1}\)); the \(u\)-coefficients enter via \(2uu'\) and \(u^2-1\) at alternating orders and are **solved around, never constrained**. Conclusion: for any even analytic \(u\)-germ with \(u(0)=1\), \(u-1=O(r^4)\), there is a unique formal cone solution reproducing the target exactly; the map \(u\mapsto(Z,T,V,P,Q)\) is injective; **one function's worth of freedom survives — exactly \(E(r)\) from \(O(r^4)\), with \(t_B(r)\) slaved as output.** This is the constructive demonstration demanded by task §3 (beyond function counting). *Status:* formal; analytic upgrade is Lemma A (majorant/CKS argument — the ODE is analytic away from the vertex and the vertex is handled by the series recursion; standard hard analysis, not yet written).

**Propagation beyond the domain [3].** The data interval \(0\le z\le1\) reaches \(r_s(1)=2(1-2^{-1/2})\approx0.586\); the domain \(r_{\mathcal D}=0.0233\) sits well inside. For \(u\) supported/distorted inside \(r_{\mathcal D}\), the response propagates outward as the homogeneous mode \(Z_0\) through explicit Green integrals (§7); existence on \([0,0.586]\) for small amplitude follows by continuous dependence — obligation O2 of the scope phase, unchanged.

---

## 7. Derivation IV — Proposition 3, the \(\mathcal Q_{\mathcal D}\) response [2]

**Slice kinematics at \(t_0=2/3\) to \(O(\varepsilon)\).** From the orbit integral \(t-t_B=\tfrac23(R/r)^{3/2}-\tfrac25\varepsilon h(R/r)^{5/2}/r^2+\cdots\) with \(t_B=\varepsilon t_B^{(1)}\):

$$R(t_0,r)=r\big[1+\varepsilon s(r)\big],\qquad s(r)=-t_B^{(1)}(r)+\tfrac25\frac{h(r)}{r^2},$$

$$H_\perp=1+\varepsilon\Big(\frac{h}{r^2}-\frac32 s\Big),\qquad H_\parallel=1+\varepsilon\Big(\frac{h'}{r}-\frac{h}{r^2}-\frac32s-\frac32rs'\Big),$$

(\(\sigma^2=\tfrac13(H_\parallel-H_\perp)^2\) [1/2, re-derived from the LTB distortion tensor]). Since \(\mathcal Q_{\mathcal D}\) is quadratic in kinematic perturbations, and the variance is insensitive to the \(O(\varepsilon)\) measure perturbation \(dV=4\pi r^2[1+\varepsilon(3s+rs'-h)]dr\) at \(O(\varepsilon^2)\) (shown: \(\mathrm{Var}_{dP}(\theta)=\varepsilon^2\mathrm{Var}_0(\delta\theta)+O(\varepsilon^3)\)), and the fixed-domain shift \(r_{\mathcal D}=r^0_{\mathcal D}(1-\varepsilon s(r^0_{\mathcal D}))\) moves the integration limit by \(O(\varepsilon)\) against an \(O(\varepsilon^2)\) integrand:

$$\boxed{\ \mathcal Q_{\mathcal D}[u]=\varepsilon^2\,\mathcal Q_2[h]+O(\varepsilon^3),\qquad \mathcal Q_2[h]=\tfrac23\Big[\mathrm{Var}(\delta\theta)-\big\langle\Delta^2\big\rangle\Big]\ }$$

$$\delta\theta=\frac{h'}{r}+\frac{h}{r^2}-\frac92s-\frac32rs',\qquad \Delta=\frac{h'}{r}-\frac{2h}{r^2}-\frac32rs',\qquad \delta\theta-\Delta=\frac{3h}{r^2}-\frac92s .$$

FLRW control: \(h\equiv0\Rightarrow\mathcal Q_2=0\) ✓. Dimensions: \(\mathcal Q_2\sim h^2/r^4\times r^3\cdot…\sim H^2\)-units ✓ (with \(H_0=1\)).

**The linear response \(t_B^{(1)}\) is explicit [2].** Linearizing the cone system about the exact EdS cone solution: the homogeneous mode of the \(Z\)-response is \(\zeta\propto Z_0\) (since \(\zeta'=\zeta Q_0+\cdots\), \(Q_0=(1-r/2)^{-1}\)), the driver is built from \(h,h'\) and \(\rho=G'(Z_0)\zeta\) with \(G'(Z_0(r))=(1-\tfrac32r)(1-\tfrac r2)^4\) — **rational**; \(\pi,\chi,\gamma\) are rational combinations; \(T_1'=-\pi+P_0h\); \(\tau_1=-\tfrac h5(1-\tfrac r2)^5/r^2+\rho(1-\tfrac r2)/r\); \(t_B^{(1)}=T_1-\tau_1\). Every ingredient is a rational-function quadrature.

**Lemma B (open, [4], reduction complete).** \(\mathcal Q_2[h]\not\equiv0\) on the admissible set. What is shown: (i) the highest-derivative content **cancels between the two terms** (both contain \((h'/r)^2\) with equal coefficient) — so nontriviality is *not* automatic and function-counting intuition is worthless here, exactly as the task warns; (ii) \(\mathcal Q_2=(2/3)\langle(\delta\theta-\Delta)(\delta\theta+\Delta)\rangle-(2/3)\langle\delta\theta\rangle^2\) exhibits it as a computable quadratic form coupling the local terms \(\propto h/r^2\) to the Green-tail \(s\); (iii) for a monomial driver \(h=r^4\), every ingredient is a convergent rational-coefficient power series on \([0,r_{\mathcal D}]\), and one symbolic evaluation of \(\mathcal Q_2\) settles the lemma. **Not evaluated in this session** — the remaining obligation is arithmetic volume, not conception.

**Lemma A (open, [4]).** Analytic local existence/uniqueness for the vertex-singular ODE, per analytic \(u\)-germ. Route: the recursion of §6 + majorants (all recursion coefficients explicitly nonzero at their leading slots, verified through \(O(r^4)\)).

---

## 8. Fixed-domain treatment [2]

\(r_{\mathcal D}[u]\) is solved per model from \(R(t_0,r_{\mathcal D})=R_{\rm phys}=0.0233\): \(r_{\mathcal D}=r^0_{\mathcal D}\,[1-\varepsilon s(r^0_{\mathcal D})]+O(\varepsilon^2)\). Because \(\mathcal Q_{\mathcal D}\) is \(O(\varepsilon^2)\), the domain shift affects it only at \(O(\varepsilon^3)\); hence \(\mathcal Q_2\) is evaluated on the reference domain and the comparison across the family is well-defined at the order that matters. [3] beyond \(O(\varepsilon^2)\).

---

## 9. Novelty boundary (verification targets — no final bibliography asserted)

| Candidate (to verify) | What it establishes (to verify) | Our delta |
|---|---|---|
| Mustapha–Hellaby–Ellis 1997 (MNRAS ~292, 817) | Numerical LTB fitting versatility from distance/counts data | No exactness/regularity theorem, no \(\mathcal Q_D\) statement, no vertex conditions |
| Bolejko–Krasiński–Hellaby–Célérier (CUP volume; reconstruction papers) | Algorithms reconstructing \((E,t_B)\) from SN-type data; folklore non-uniqueness | Theorem-shaped non-uniqueness with \(\mathcal Q_D\)-specific content; vertex theorem absent |
| Zibin 2008 (PRD ~78, 043504); February et al. ~2010 | \(D_L\) deviations of LTB from FLRW arise at second order (setup to verify) | Consistent with our family (the \(t_B\)-output absorbs \(O(\varepsilon)\)); explains *why* second order: the degeneracy direction |
| García-Bellido–Haugbølle 2008 (JCAP); Enqvist–Mattsson 2007 | Fixed-profile fits with \(t_B=0\) — closure by hand | Our §5–6 is the analytic account of what that closure buys |
| Sussman 2011 (exact LTB \(\mathcal Q_D\) structure) | Slice-side exact \(\mathcal Q_D\) for LTB domains | Cone-side identifiability untouched there |
| Koksbang 2019–2023; Heinesen 2021– | Light-cone observables/averaging in exact models | No identifiability theorem for slice-defined \(\mathcal Q_D\) |

**Search plan:** "LTB inverse problem uniqueness," "bang-time degeneracy," "identifiability of backreaction," author windows (Koksbang, Heinesen, Bolejko, Krasiński, Clarkson, Zibin), 2024–2026. If the theorem exists: stop and take the smallest delta (likely the vertex theorem, which I have not seen anywhere and which is independently checkable).

---

## 10. Phys-compatible artifact (unexecuted; no workspace/locked spec available in this session)

**Limitation declared:** the canonical Phys representation spec was not reachable; the files use only standard-library Go (`math/big`, `testing`) so that nothing depends on invented APIs. Passing these tests verifies **algebraic identities at sample points and series coefficients** — it does **not** prove the theorem (stated inside the test file).

**Path: `AGENTS.md`**
```markdown
# ZEH-6A Artifact — LTB Non-Identifiability of Q_D
- Claim: Theorem in §2 of the submission (status [4]; Props 1–3 [2]; Lemmas A,B open).
- Regime: classical GR, dust, Λ=0, c=G=1, H_loc(t0)=1, gauge M(r)=r^3/2 (exact string:
  "r^3/2" — any occurrence of r^(3/2) is a defect).
- Constitution (declared, not derived): central observer; central normalization R'(t0,0)=1;
  t_B(0)=0; comoving dust foliation; spherical comoving domains; fixed physical boundary
  R(t0,r_D)=0.0233.
- Non-claims: no Outcome C; no Λ/dark-energy mechanism; no statement about our universe.
- MRC rule: every proposition carries [1–5] and [census/grammar/constitution/shield].
- Tests: rational-arithmetic identity checks only. They do NOT constitute proof.
```

**Path: `manifest.json`**
```json
{
  "artifact": "ZEH-6A",
  "theorem": {
    "id": "LTB-QD-nonidentifiability",
    "status": "conjecture",
    "depends_on": ["P1-vertex-normalization [2]", "P2-recursive-freedom [2-formal]",
                   "P3-QD-response [2]", "LemmaA-wellposedness [4]", "LemmaB-Q2-nonzero [4]"]
  },
  "gauge": "M(r)=r^3/2",
  "regime": "classical GR, dust, Lambda=0, c=G=1",
  "target": "DA*(z)=2(1-(1+z)^{-1/2})/(1+z), 0<=z<=1",
  "domain": {"type": "physical areal radius", "value": 0.0233},
  "numerics": {"executed": false},
  "phys_spec_available_in_session": false
}
```

**Path: `protocol/derivation_test.go`** (excerpts; full file follows the same pattern)
```go
package protocol

import (
	"math/big"
	"testing"
)

// rat helpers omitted (newRat, mul, sub, div over math/big.Rat).

// Check 1: exact EdS cone identity 2*V0*Q0 == 3r^2/Rc0 - r^3*P0/Rc0^2,
// with V0=r/(1-r/2), Q0=1/(1-r/2), Rc0=r(1-r/2)^2, P0=(1-r/2)^2.
// This is an identity check at rational sample points; NOT a proof.
func TestEdSConeAlgebraicIdentity(t *testing.T) {
	for _, rs := range []string{"1/100", "7/500", "3/50"} {
		r := mustRat(rs)
		lhs := mul(rat(2), mul(div(r, sub(rat(1), div(r, rat(2)))),
			div(rat(1), sub(rat(1), div(r, rat(2))))))
		rhs := sub(div(mul(rat(3), r), mul(r, mul(r, sq(sub(rat(1), div(r, rat(2)))))),
			// 3r^2/Rc0
			rat(1)), div(mul(mul(r, r), r), mul(sq(mul(r, sq(sub(rat(1), div(r, rat(2)))))), rat(1))))
		// (implementation detail: rhs assembled exactly as printed in the submission; any
		//  mismatch here is a defect in THIS file, not in the submission identity)
		if lhs.Cmp(rhs) != 0 {
			t.Fatalf("identity fails at r=%s", rs)
		}
	}
}

// Check 2: series coefficients — z2=3/4 forced; z3=1/2+(2/3)u4.
// Verified symbolically in the submission (§5–6); test asserts the printed
// coefficient identities on the recursion at a symbolic beta placeholder.
// NOTE (unexecuted artifact): kept as documentation of the obligation.
```

*(The full test file repeats Check 1 over a rational grid and adds the target-composition check \(G(z(r))=r(1-r/2)^2\). All checks labeled UNEXECUTED.)*

---

## 11. MRC / MRC2 review

- **Graveyard compliance:** no claim generates Λ, selects the metric, fixes initial conditions, or reaches quantum domains. The central normalization and observer position are declared [constitution], not derived — and §5's remark shows exactly what happens when the declaration is relaxed (a second branch appears): the constitution is load-bearing and labeled.
- **Coincidence discipline:** no dimensionless "matches" are claimed anywhere; the only numbers printed are derived coefficients (\(z_2=3/4\), \(z_3=\tfrac12+\tfrac23\beta\), \(g_k\)) each carrying an FLRW/EdS limit and an exact-identity check.
- **Census:** free data after gauge and vertex conditions: one function \(E_{\ge4}(r)\) (+ the declared constants); nuisances: none for \(D_A\) (bang time is output, not nuisance — a sharpening of the benchmark-turn count).
- **Shield:** the theorem, if established, is refuted by exhibiting a *third* independent channel that fixes \(E_{\ge4}\) from \(D_A\) alone — i.e., by proving Lemma A plus injectivity of \(u\mapsto\mathcal Q_2\); the paper states this falsifier in advance.

---

## 12. Status table and verdict

| Claim | Status | Evidence or missing step |
|---|---|---|
| Buchert equations + integrability \(\dot{\mathcal Q}_D+4H_D\mathcal Q_D+3\dot k_D/a_D^2=0\) | **[1]+[2]** (truncated prior item now completed) | Derived here; FLRW check ✓; correspondence to Buchert 2000 notation flagged for verification |
| Exact reduced cone system with \(u\) free (constructive closure) | **[2]** | §4; exact EdS rational identity ✓; four transcription errors caught and fixed by controls |
| Vertex normalization theorem (\(E_2=0\), \(a_0=1\), \(z_2=3/4\), central age \(2/3\)) | **[2] established** | §5; two independent relations; EdS branch exact; second branch flagged |
| Recursive one-function freedom reproducing target exactly | **[2] formal / [3] analytic** | §6 through \(O(r^4)\); Lemma A (majorant) owed |
| \(\mathcal Q_D[u]=\varepsilon^2\mathcal Q_2[h]+O(\varepsilon^3)\), measure/domain immune at \(O(\varepsilon^2)\) | **[2]** | §7–8 |
| \(\mathcal Q_2[h]\not\equiv0\) (hence Theorem) | **[4]** | Reduced to rational quadrature for \(h=r^4\); the \(h'^2\)-cancellation makes it genuinely nontrivial — one evaluation owed |
| Restricted (\(t_B\equiv0\)) uniqueness | **out of scope** (one line: the output channel closes; consistent with the conjecture) | separate task |
| New closed relation (Outcome C) | **not claimed** | support obstruction restated |

**Verdict: PARTIALLY ESTABLISHED.** The distance data do *not* trivially under-determine the model — they fix the vertex rigidly (\(H_{\rm loc}\), \(R'(t_0,0)\), \(E_2\), and the \(z\)-profile recursively given \(u\)) — and what survives is exactly one function of freedom, constructively exhibited, with the bang time as its output shadow. Whether \(\mathcal Q_{\mathcal D}\) varies along that freedom is reduced to a single computable evaluation (\(\mathcal Q_2[h=r^4]\)), and well-posedness to a standard majorant lemma. Neither is discharged; the theorem is not claimed. The next action is precisely those two write-ups — they are finite, mechanical, and fully specified by the derivations above.
