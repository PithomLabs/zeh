# ZEH-5 Submission — Independent Agent

**Compliance box.** Every claim below carries a status tag: **[1]** established in literature, **[2]** derived in this investigation, **[3]** conditional on stated assumptions, **[4]** conjecture, **[5]** unsupported/falsified — and an MRC category: **[census]** (degrees of freedom, data), **[grammar]** (exact identities), **[constitution]** (declared framework choices), **[shield]** (falsifiable restriction). **The numerical implementation was not executed. No numerical-validation claim is made anywhere; all numbers printed are analytic results or labeled estimates.** This submission was produced without seeing other agents' outputs.

---

## 1. Executive verdict

**Partially derived.** The benchmark question — can past-light-cone data determine \(Q_{\mathcal D}(t_0)\) in general LTB, and does the simultaneous-bang restriction change the answer? — receives the following analytic answer:

1. **General LTB (Case A): \(Q_{\mathcal D}(t_0)\) is NOT determined by \(D_A(z)\) data.** The inverse problem has a one-function degeneracy, established constructively at linear order by a Volterra-kernel argument [2, with finite-amplitude status conditional [3]]. The degeneracy is realizable inside the benchmark's own profile family: each bang-time profile \(\tilde t_B(r)\) admits (conditionally) a unique compensating \(E(r)\); different profiles (or different \(\Delta\) at the same profile shape) give distinct admissible models fitting the same target with different \(Q_{\mathcal D}\).
2. **Simultaneous bang (Case B): \(Q_{\mathcal D}(t_0)\) IS determined, conditionally** — locally unique near the reference branch [3, linearly rigorous [2]] — and since the target *is* the EdS solution, the branch answer is exact and analytic: \(E(r)\equiv 0\), \(Q_{\mathcal D}\equiv 0\), with all held-out channels ( \(H_\parallel(z)\), redshift drift) equal to the EdS values.
3. **The mechanism is structural, not technical:** the bang-time function is **cone-invisible** — it enters the inverse problem only as an output of the shell orbits, never in the on-cone observables. Imposing \(t_B\equiv 0\) is precisely the closure condition that absorbs the one-function freedom.
4. **No Outcome C.** No closed new relation between \(\mathcal Q_{\mathcal D}\) and cone observables was found; the support obstruction identified in the prior turn (slice-supported variance vs. cone-supported observables) stands. The strongest positive content is the demonstrated **non-redundancy of the drift channel**, which is model-discrimination (Outcome B strengthened), not a new relation.
5. **A quantitative surprise relevant to adjudication:** the benchmark's 100 Mpc domain corresponds to \(z \lesssim 0.0237\) on the cone [2]. \(Q_{\mathcal D}(t_0)\)-identifiability therefore rests on a very narrow data sliver; the bulk of the \(z\le 1\) dataset constrains structure outside the domain.
6. Two errors in the prior thread's derivations were caught by the mandated control checks and are corrected here (the integrability-condition coefficient; documented in §4.3), plus two transcription errors caught mid-derivation in this submission by the EdS checks — reported transparently in §8 as evidence that the control discipline functions.

---

## 2. Applicable regime and scales

- **Theory** [constitution]: classical GR, irrotational dust, \(\Lambda=0\), \(c=G=1\), \(H_0=1\), \(t_0 = 2/3\). Synthetic mathematical control; no claim that EdS describes our universe.
- **Averaging scale** [census]: comoving spherical domain with present-day physical boundary \(R(t_0,r_{\mathcal D}) = 0.0233\) (100 Mpc at \(H_0=70\)). This is a geometric coarse-graining scale, **not an RG momentum scale**. No renormalization group statement appears anywhere in this submission; the prior thread's RG language is explicitly bracketed out as underived.
- **Observational scale** [census]: one past light cone, \(0\le z\le 1\).
- **Distinctions maintained:** (i) no RG scale is invoked; (ii) the physical scale is \(R_{\mathcal D}\), a domain definition, not a flow parameter; (iii) cone data are parametrized by \(z\), spatial averages by \(t=t_0\) — different curves in the \((t,r)\) plane, intersecting only at the vertex; (iv) \(\langle\cdot\rangle_{\mathcal D}\) is an exact operation on an exact solution, not an effective field theory. Nothing below touches quantum gravity, particle content, or the Born rule.

---

## 3. Definitions and assumptions

Metric and dynamics [1; Lemaître 1933, Tolman 1934, Bondi 1947]:

$$ds^2=-dt^2+\frac{R'(t,r)^2}{1+2E(r)}dr^2+R^2(t,r)d\Omega^2,\qquad \dot R^2=\frac{2M(r)}{R}+2E(r),\qquad \rho=\frac{M'}{4\pi R^2R'}$$

**Gauge count** [census, 2]: the relabeling freedom \(r\to\tilde r(r)\) is **fully removed** by \(M(r)=r^3/2\) (preserving the form forces \(\tilde r=r\)). Remaining physical functions: exactly two, \(E(r)\) and \(t_B(r)\). Center regularity imposes constraints (not freedoms): \(E=O(r^2)\), \(t_B'(0)=0\), \(M\sim r^3/2\).

**Declared assumptions:** (A1) central observer \(r_o=0\) — assumption, not derived; (A2) regular center; (A3) no shell crossings (\(R'>0\)) on the tested interval; (A4) no caustics on the cone; (A5) \(t_0=2/3\) fixed — the same foliation and evaluation time in all models, per specification.

**Bang-time profile** [constitution — test choice, not theorem, per specification]:

$$t_B(x)=\Delta\left[e^{-(x/\alpha)^2}-1\right],\qquad \alpha=0.05,\qquad \Delta\in\{0.02,\ 0.05,\ 0.1\}\ \text{declared}.$$

Note \(t_B(0)=0\), \(t_B(\infty)=-\Delta\): inner shells bang later. Within the domain (\(r\le 0.0233 < \alpha\)) the profile is parabolic: \(t_B\approx-\Delta(r/\alpha)^2\), with steep gradient \(|t_B'|\lesssim 0.93\) at the domain edge for \(\Delta=0.05\) — flagged as an admissibility risk (§8).

---

## 4. Equation audit

### 4.1 Target verification [2]

For EdS (\(E=0\), \(t_B=0\)): \(R=(9/4)^{1/3}r\,t^{2/3}\), so \(R(t_0,r)=r\) and \(r_{\mathcal D}=0.0233\) in coordinates. Central null ray: \(dt/dr=-R'\Rightarrow r_s=3(9/4)^{-1/3}(t_0^{1/3}-t_e^{1/3})\). With \(1+z=(t_0/t_e)^{2/3}\):

$$D_A=R(t_e,r_s)=\tfrac{9}{4}^{1/3}r_st_e^{2/3}=3t_0\frac{1-(1+z)^{-1/2}}{1+z}=\frac{2[1-(1+z)^{-1/2}]}{1+z}=D_A^*(z)\quad\checkmark$$

exact, as required, before any reconstruction. Also \(r(z)=2[1-(1+z)^{-1/2}]\) on the reference branch, and \(R'(t_e,r_s)=(1+z)^{-1}\).

### 4.2 The on-cone system [2, EdS-verified]

Central observer ⇒ all rays radial (zero angular momentum at the center), hence **\(D_A=R(t_e,r_s)\) exactly** [2; consistent with Kristian–Sachs 1966]. Photon energy \(\omega=k^t\) for comoving observers; with \(\Gamma^t_{rr}=\tfrac12\partial_t g_{rr}=R'\dot R'/(1+2E)\) and the null condition, the incoming-ray equation gives \(d\ln\omega/dr=\dot R'/\sqrt{1+2E}\), integrated along the cone. Define \(u(r)\equiv\sqrt{1+2E}\). The exact on-cone system, parametrized by \(r\):

$$\text{(E1)}\quad t'=-R'/u \qquad\qquad \text{(E2)}\quad \frac{d\ln(1+z)}{dr}=\frac{\dot R'}{u}$$

$$\text{(E3)}\quad R=D_A^*(z)\qquad\quad \text{(E4)}\quad \dot R^2=\frac{r^3}{R}+u^2-1$$

$$\text{(E5)}\quad 2\dot R\dot R'=\frac{3r^2}{R}-\frac{r^3R'}{R^2}+2uu' \qquad\quad \text{(E6)}\quad R'\Big(1-\frac{\dot R}{u}\Big)=(1+z)\,D_A^{*'}(z)\,\frac{\dot R'}{u}$$

where (E5) is \(\partial_r\) of (E4) at fixed \(t\), (E6) is the chain rule on (E3) using \(w'(r)=R'(1-\dot R/u)\), and \(D_A^{*'}(z)=[3-2\sqrt{1+z}]/(1+z)^{5/2}\) [2].

**Verification record (mandated by the task; reported because it caught real errors):** two transcription errors were made and caught during this derivation, both by the EdS control: (i) (E2) was first written as \(z' = z\dot R'/u\); the EdS integral check \(\int_0^{r_s}\dot R'/u\,dr = \ln(1+z)\) passed while the differentiated form failed — the correct factor is \((1+z)\), since the integral form differentiates to \(z'=(1+z)\dot R'/u\). (ii) (E6) initially used the same wrong factor and failed its EdS check (LHS 0.8204 vs RHS 0.0746 at \(z=0.1\)); with the correction, LHS = RHS = 0.8203 to four digits. **All six equations verified on the reference branch.**

**Solvability of the algebraic subsystem** [2]: given \(u,u'\), equations (E4)–(E6) are three algebraic equations for \((\dot R, R', \dot R')\). The Jacobian determinant at the EdS point, \(z=0.1\): \(\det = 8R'\dot R^2 - 2(1+z)D_A^{*'}\dot R' r^3/R^2 = -0.115\neq 0\) — locally solvable; degenerate only at the vertex, where regularity conditions replace the algebra (integration starts at small finite \(r\) with series-matched central data).

### 4.3 Spatial averaging machinery [grammar]

With \(H_\perp\equiv\dot R/R\) (transverse) and \(H_\parallel\equiv\dot R'/R'\) (radial; **not interchanged**): \(\theta = 2H_\perp+H_\parallel\), and the LTB shear [2, derived from \(B^r_r=\dot R'/R'\), \(B^\theta_\theta=\dot R/R\), traceless part]:

$$\sigma^2\equiv\tfrac12\sigma_{ab}\sigma^{ab}=\tfrac13\,(H_\parallel-H_\perp)^2\qquad\Rightarrow\qquad \mathcal Q_{\mathcal D}=\tfrac23\big(\langle\theta^2\rangle-\langle\theta\rangle^2\big)-\tfrac23\big\langle(H_\parallel-H_\perp)^2\big\rangle$$

with proper-volume weights \(\langle f\rangle=\int_0^{r_{\mathcal D}} f\,R^2R'/u\,dr \big/ \int_0^{r_{\mathcal D}}R^2R'/u\,dr\), all evaluated at \(t=t_0\), comoving domain [per specification]. FLRW control: \(\theta=2/t\), \(\mathrm{Var}(\theta)=0\), \(\sigma^2=0\) ⇒ \(\mathcal Q_{\mathcal D}=0\) ✓.

**Averaged Hamiltonian** [2, derived here; matches Buchert 2000]. Using the exact Gauss identity \(^{(3)}R=16\pi G\rho-\tfrac23\theta^2+\sigma_{ab}\sigma^{ab}-2\Lambda\) [2; sign fixed by the FLRW check \(^{(3)}R=6k/a^2\) — an initial sign error was caught by this check] and \(\langle\theta\rangle = \dot V_{\mathcal D}/V_{\mathcal D}\) (exact for comoving domains):

$$3H_{\mathcal D}^2=8\pi G\langle\rho\rangle_{\mathcal D}+\Lambda-\tfrac12\mathcal Q_{\mathcal D}-\tfrac12\langle{}^{(3)}R\rangle_{\mathcal D}\qquad\checkmark$$

**Averaged Raychaudhuri** [1, Buchert 2000]: \(\ddot a_{\mathcal D}/a_{\mathcal D}=-\tfrac{4\pi G}{3}\langle\rho\rangle+\tfrac13\mathcal Q_{\mathcal D}+\tfrac{\Lambda}{3}\), with \(\langle\dot\rho\rangle=-3H_{\mathcal D}\langle\rho\rangle\) exact [2].

**Integrability condition — correction to the prior turn** [2, derived here]. Requiring \(\frac{d}{dt}(3H_{\mathcal D}^2)\) from
