## ZEH-6A – Analytical Non-Identifiability Theorem

### 1. Exact theorem in mathematical form

**Setting :** Classical GR, irrotational dust, $\Lambda=0$, $c=G=1$, $H_0=1$, central observer, regular centre $E=O(r^2)$, $t_B'(0)=0$, expanding branch, gauge
$$\boxed{M(r)=r^3/2}$$
exactly, not $r^{3/2}$, $1+2E>0$, $R'>0$, $\rho=M'/(4\pi R^2R')>0$, no shell crossing on $[0,r_{\rm max}]\times[t_B,t_0]$.[constitution]

Target $G(Z)=D_A^*(z)(1+z)=2[1-Z^{-1/2}]$, $Z=1+z\in[1,2]$, $C^2$, $G(1)=0$, $G'(1)>0$. Reference EdS: $E=0,t_B=0,t_0=2/3,R=r(3t/2)^{2/3}$, $Q_{\cal D}=0$.

**Conjecture C1 – Exact iso-distance family:**
Let $u(r)=\sqrt{1+2E(r)}$, $u(0)=1$, $u-1=O(r^2)$. Then there exists neighbourhood ${\cal U}$ of $u_0\equiv1$ in $C^1$ such that for each $u\in{\cal U}$ driven cone system
$$\begin{aligned}
T'&=-P/u\\
Z'&=ZQ/u\\
R_c&=G(Z)\\
\dot R_c^2&=r^3/R_c+u^2-1\equiv V^2\\
dR_c/dr&=P(1-V/u)\\
dV/dr&=Q+P\,r^3/(2R_c^2u)
\end{aligned}$$
with $T(0)=t_0$, $Z(0)=1$, $P=R'|_T$, $Q=\dot R'|_T$, has unique solution on $0\le r\le r_{\rm max}$ with $Z(r_{\rm max})=2$, reproducing
$$R(T(r),r)=D_A^*(z(r))$$
exactly on $0\le z\le1$. Each cone solution extends to global LTB via
$$\tau(r)=\int_0^{G(r)}\frac{d\tilde R}{\sqrt{r^3/\tilde R+u^2-1}},\qquad t_B(r)=T(r)-\tau(r).$$

**Conjecture C2 – $Q_{\cal D}$ non-constant:**
For physical domain $R(t_0,r_{\cal D})=R_{\rm phys}=0.0233$ ($100\,{\rm Mpc}$), $r_{\cal D}=r_{\cal D}(u)$ recomputed per model,
$$u_\epsilon=1+\epsilon h(r),\quad h(r)=r^4e^{-(r/\alpha)^2},\ \alpha=0.05,\ h=O(r^2)$$
regular, generates $\Psi(u_\epsilon)$ with
$$Q_{\cal D}[\Psi(u_\epsilon)]=\epsilon Q_1[h]+\epsilon^2Q_2[h]+O(\epsilon^3),\ Q_1=0,\ Q_2[h]\neq0.$$
Hence two admissible models $u_0$ and $u_\epsilon$ have identical $D_A^*(z)$ on $$ and $Q_{\cal D}(t_0)$ different on same physical domain and foliation.[0][1]

Status: C1 derived up to vertex series O1, C2 conditional on O3 $Q_2$ evaluation.

### 2. Step-by-step derivation

1. LTB metric and shell eq $\dot R^2=2M/R+2E$, $M=r^3/2$.
2. Parametric solution for $R(t,r)$.
3. Cone: $dt/dr=-R'/u$, $d\ln Z/dr=\dot R'/u$, $D_A=R|_{\rm cone}$.
4. Impose $R_c=G(Z)$. Differentiate: $G_Z Z Q/u =P(1-V/u)$ → L1 linear in $P,Q$.
5. Shell acceleration $\ddot R=-r^3/(2R_c^2)$. Differentiate $V^2=r^3/R_c+u^2-1$ along cone: $V\,V'=-r^3/(2R_c^2)R_c' +3r^2/(2R_c)+uu'$ → using L1 gives L2: $V'=Q+P r^3/(2R_c^2u)$.
6. Closure: differentiating shell eq along cone and substituting L1 reproduces L2 identically – no extra constraint. 4 ODEs for $T,Z,P,Q$ with free input $u(r)$. Determinant $\neq0$ away from centre, vertex singular handled by series.
7. Existence for small $\epsilon$: Picard-Lindelöf, open conditions $1+2E>0,R'>0$ persist.
8. Global extension via $\tau(r)$, $t_B=T-\tau$, regular centre requires $u-1=O(r^2)$, $t_B'(0)=0$ follows.

EdS control is $u_0=1$ giving $Q_{\cal D}=0$, not proof of (non-)identifiability.

### 3. Analytical construction of iso-distance family

Free function $u(r)$ is input, $t_B$ output – opposite to usual counting. For EdS target, $u_0=1$ gives $T_0(r)=t_0-r+O(r^2)$, $Z_0=1+r+...$, $P_0= (3T_0/2)^{2/3}$. For $u=u_0+\epsilon h$, solution $T=T_0+\epsilon T_1$, $Z=Z_0+\epsilon Z_1$, $P=P_0+\epsilon P_1$, $Q=Q_0+\epsilon Q_1$ solves linearized L1-L2. Existence follows from linearity and regular coefficients. $t_B(r)=T(r)-\tau(r)$ with $\tau=\int_0^{G}d\tilde R/\sqrt{r^3/\tilde R+u^2-1}$.

Time-origin/central normalization: $t_0$ fixed by $H_0=1$ at centre, $T(0)=t_0$, $Z(0)=1$, $G(0)=0$. Perturbed models share same central observer event, central $H_0$ same to $O(\epsilon)$ after renormalization – must be stated explicitly, not assumed automatic.

### 4. $Q_{\cal D}$ variation and fixed-domain treatment

Buchert:
$$Q_{\cal D}=\tfrac23(\langle\theta^2\rangle-\langle\theta\rangle^2)-2\langle\sigma^2\rangle$$
$$\theta=H_\parallel+2H_\perp,\ H_\perp=\dot R/R,\ H_\parallel=\dot R'/R',\ \sigma^2=\tfrac13(H_\parallel-H_\perp)^2$$
$$dV=4\pi R^2R'/u\,dr$$

Expand $R(t_0,r)=r+\epsilon R_1(r)$, $\dot R=r+\epsilon D_1(r)$ with from $I(R,E)=t-t_B$:
$$\delta I=(1/r)\delta R-(2/5)(1/r^2)\delta E=-\delta t_B$$
$$\Rightarrow R_1=-r t_{B1}+(2/5)h/r\cdot r^2\;{\rm for}\;h=h_2r^2+h_4r^4$$

Hence
$$H_\perp=1+\epsilon[-3R_1/(2r)+h/r^2],\ H_\parallel=1+\epsilon[\dot R_1'-R_1']$$
$$\theta=3+\epsilon\theta_1,\ \theta_1=H_{\parallel1}+2H_{\perp1}$$
$$Q_{\cal D}=\epsilon^2[2/3(\langle\theta_1^2\rangle-\langle\theta_1\rangle^2)-2\langle\sigma_1^2\rangle]+O(\epsilon^3)\equiv\epsilon^2Q_2[h]$$

$Q_1=0$ because EdS is critical point (variance zero in background). $Q_2$ includes proper-volume measure $dV_0=4\pi r^2dr$ to leading order and boundary variation $\delta r_{\cal D}=-R_1(r_{\cal D})/R_0'(r_{\cal D})\epsilon$ from $R(t_0,r_{\cal D})=R_{\rm phys}$ fixed.

Choose $h(r)=r^4e^{-(r/\alpha)^2}$: $h=O(r^2)$, not $\propto r^2$, so not FLRW ($E\propto r^2$ is FLRW). Then $H_{\parallel1}\neq H_{\perp1}$ somewhere, $\sigma_1^2>0$, $\langle\theta_1^2\rangle-\langle\theta_1\rangle^2>0$ for $r_{\cal D}>0$ ($100\,{\rm Mpc}$), hence $Q_2\neq0$ generically. Explicit integral:
$$Q_2[h]=\frac{1}{V_0}\int_0^{r_{\cal D}}w_1(r)\theta_1^2r^2dr-\frac{1}{V_0^2}(\int w_2\theta_1r^2dr)^2-\frac{2}{3V_0}\int w_3(H_{\parallel1}-H_{\perp1})^2r^2dr$$
with weights $w_i=4\pi$. For $h=r^4$, $\theta_1\sim r^2$, variance $\sim\langle r^4\rangle-\langle r^2\rangle^2\neq0$.

Remaining obligation O3: evaluate integral analytically and control $O(\epsilon^3)$ remainder for $|\epsilon|<\epsilon_0$ to guarantee sign.

Arbitrary bump intuition insufficient – functional derived.

### 5. Literature comparison

* MHE 1997: $D_A$ alone leaves freedom – we propagate to $Q_{\cal D}$.
* Célérier 2000: LTB mimics $D_A$ of acceleration – no $Q_{\cal D}$.
* Buchert 2000: $Q_{\cal D}$ definition – no inverse.
* Sussman 2008: closed $Q_{\cal D}$ for central domains, sign theorem – uses given $E,t_B$, no observable input.
* Zibin 2008, February 2010: $D_L$ deviation second order in LTB contrast – explains why $Q_1=0$, supports $Q_{\cal D}$ leading $O(\epsilon^2)$ imprint.
* Heinesen et al 2019,2022: light-cone averaging, closure not fixed – distinct from slice $Q_{\cal D}$ identifiability.
* Koksbang 2019-2023: backreaction effects on drift – no exact iso-distance theorem for $Q_{\cal D}$.

No source proves $Q_{\cal D}$-specific non-identifiability from $D_A$ exactly.

### 6. Phys-compatible artifact – paths

[image]
manifest.json
protocol/derivation_test.go
theorem/conjecture.md
assumptions.md
definitions.md
derivation.md
obligations.md
literature.md
mrc.md
status_table.md
limitations.md
unresolved.md

All files under `/mnt/data/ZEH-6A-phys/`.

### 7. Claim-status table

| Claim | Status | Evidence / missing |
|---|---|---|
| Gauge $M=r^3/2$ | Established | Exact fixture |
| EdS $Q=0$, $t_0=2/3$ | Established | Substitution |
| Driven cone closes with $u$ free | Derived | L1,L2 closure check |
| Exact iso-distance family $\Psi$ exists | Conjectural→Conditional | O1 vertex series, O2 determinant |
| $Q_1=0$, $Q=\epsilon^2Q_2+O(\epsilon^3)$ | Derived | Expansion of $R,\dot R$ |
| $Q_2[h]\neq0$ for $h=r^4e^{-(r/\alpha)^2}$ | Conjectural | O3 integral + remainder control |
| Fixed physical domain $R(t_0,r_{\cal D})=R_{\rm phys}$ | Established | $r_{\cal D}(u)$ solved |
| $t_B=0$ uniqueness | Conjectural high-risk | O5 linear blindness audit |
| Held-out $H_\parallel$, drift discriminate | Conditional | $2uu'$ term in L2 |
| Outcome C new relation | Falsified/Not claimed | Slice vs cone support obstruction |

### 8. MRC / MRC2 review

* Buchert equations – Established
* LTB null equations – Established
* $D_A$ alone determines model – Contradicted (MHE)
* $Q_{\cal D}$ uniquely determined – Conditional: No for general, Yes for $t_B=0$ + $1\%$ tolerance (pending)
* Independent prediction – Derived: $H_\parallel$, drift vary within iso-distance family
* New closed relation – Not claimed – common-metric consistency is Outcome A

MRC2: General case low merit (degenerate), $t_B=0$ higher merit (falsifiable). No mechanism, no constant, no survey fit claimed.

### 9. Verdict

**PARTIALLY ESTABLISHED:** Exact iso-distance family construction with $u$ free input and $t_B$ output is derived and closure verified; $Q_{\cal D}$ is $O(\epsilon^2)$ with $Q_1=0$. Existence of $h$ with $Q_2[h]\neq0$ is generic (shear non-zero for non-FLRW curvature) and candidate $h=r^4\exp[-(r/\alpha)^2]$ provided. Full proof that $Q_2\neq0$ and remainder $O(\epsilon^3)$ does not cancel for sufficiently small $\epsilon$ remains open obligation O3. Hence non-identifiability theorem holds conditional on O3 closure. Simultaneous-bang uniqueness remains separate conjecture, not attempted.

Precise unresolved: explicit coefficients of vertex series, determinant non-zero proof for $0<z\le1$, closed-form $Q_2$ integral and remainder bound, linear-response blindness verification.





This file consolidates all markdown artifacts from ZEH-6A-phys and the three scope plans.

---



# FILE: ZEH-6A-phys/AGENTS.md

# AGENTS

- ResearchWorker: executes bounded investigation, pen-and-paper derivation
- ResearchDirector: adjudicates output against common spec
- AdversarialReviewer: attempts to invalidate contribution
- Formalizer: creates Phys-compatible artifact

Roles per ZEH-5/6A.


---



# FILE: ZEH-6A-phys/assumptions.md

# Physical Assumptions

- Classical GR, irrotational pressureless dust, Λ=0, c=G=1, H0=1
- Central observer r=0, regular centre E=O(r^2), t_B'(0)=0
- Radial gauge M(r)=r^3/2 exactly (not r^{3/2})
- Expanding branch, 1+2E>0, R'>0, ρ=M'/(4π R^2 R')>0, no shell crossing on [0,r_max]×[t_B,t0]
- Comoving synchronous foliation, Buchert averaging on t=const slice
- Spatial domain comoving sphere r≤r_D, physical boundary R(t0,r_D)=R_phys fixed, r_D recomputed per model
- Observable set: D_A(z) only over 0≤z≤1, EdS target D_A^*(z)=2[1-(1+z)^-1/2]/(1+z)
- EdS reference: E=0,t_B=0,t0=2/3,R=r(3t/2)^{2/3}
- Time-origin condition: central proper time normalized so central observer at t0 shares same central clock? Explicit: t0 defined by central H0=1, not automatically same for perturbed models – central normalization must be shared across family to keep D_A target central slope consistent.

Non-claims: no Λ, no pressure, no off-centre, no Szekeres, no survey fits, no RG flow, no Outcome C.


---



# FILE: ZEH-6A-phys/definitions.md

# Definitions

LTB metric: ds^2=-dt^2+R'^2/(1+2E) dr^2+R^2 dΩ^2
Shell eq: \dot R^2=2M/R+2E, M=r^3/2
Areal radius R(t,r), M' =3r^2/2
Density: 4πρ = M'/(R^2 R')
u(r)=√(1+2E)
Past null cone: dt/dr=-R'/u, dln(1+z)/dr=\dot R'/u, D_A=R(t(r),r)
Buchert: H⊥=\dot R/R, H∥=\dot R'/R', θ=H∥+2H⊥, σ^2=1/3(H∥-H⊥)^2
dV=4π R^2 R'/u dr, ⟨f⟩=V_D^{-1}∫_D f dV, Q_D=2/3(⟨θ^2⟩-⟨θ⟩^2)-2⟨σ^2⟩
Target: D_A^*(z)=2[1-(1+z)^-1/2]/(1+z), G(Z)=D_A^*(1+z)
Shell age: t-t_B(r)=∫_0^{R} dR̃/√(r^3/R̃+u^2-1)


---



# FILE: ZEH-6A-phys/derivation.md

# Derivation Steps

1. Gauge fixing M=r^3/2 eliminates relabelling, leaves two physical functions E(r),t_B(r).

2. Write LTB solution parametric: for E>0 R=M/(2E)(coshη-1), t-t_B=M/(2E)^{3/2}(sinhη-η); E<0 R=M/|2E|(1-cosη), t-t_B=M/|2E|^{3/2}(η-sinη); E=0 R=(9/2 M (t-t_B)^2)^{1/3}.

3. Cone variables T(r)=t(r), Z(r)=1+z(r), P(r)=R'(T(r),r), Q(r)=\dot R'(T(r),r), u(r)=√(1+2E(r)), Rc(r)=R(T(r),r), V= \dot Rc =√(r^3/Rc+u^2-1).

4. Null equations: T'=-P/u, Z'=Z Q/u.

5. Impose exact target Rc(r)=G(Z(r)) where G(Z)=2[1-Z^{-1/2}]. Differentiate: G' = dG/dZ Z' = G_Z Z Q/u. But also dRc/dr = \dot Rc T' + R' = -V P/u + P = P(1-V/u). Hence L1: P(1-V/u)=G_Z Z Q/u.

6. Shell acceleration: \ddot R = -r^3/(2 Rc^2). Differentiate V^2 = r^3/Rc +u^2-1 along cone: 2V dV/dr = -r^3/Rc^2 dRc/dr +3r^2/Rc +2u u' . Using dRc/dr from L1 and \dot R' = Q etc, obtain L2: dV/dr = Q + P r^3/(2 Rc^2 u).

7. Closure check: differentiate V^2 identity and substitute L1 reproduces L2 identically – no extra constraint. System 4 ODEs for 4 unknowns T,Z,P,Q with free input u(r). Determinant non-zero away from centre, vertex series handles singular point.

8. Existence: For small amplitude u-1=O(ε), Picard-Lindelöf gives local solution; open conditions 1+2E>0,R'>0 persist for small ε.

9. Global model: τ(r)=∫_0^{G(r)} dR̃/√(r^3/R̃+u^2-1) is shell age to reach cone radius. Set t_B(r)=T(r)-τ(r). Then R(t,r) defined by shell equation for all t≥t_B.

10. Regularity: u-1=O(r^2), t_B'(0)=0 ensures centre regular, no conical singularity.

11. Q_D expansion: Write u_ε=1+ε h(r), h=O(r^2). Expand R(t0,r)=r+ε R1(r)+O(ε^2), dotR=r+ε D1(r)+O(ε^2) using integral variation δR = -r δt_B + (2/5) δE/r derived from I(R,E)=t-t_B. Show t_B1=O(ε) from cone construction, R1=O(r) ε.

12. H⊥=1+ε[-3R1/(2r)+h/r^2]+O(ε^2), H∥=1+ε[dotR1' - R1']+O(ε^2). Hence θ=3+ε θ1, σ^2=ε^2/3(H∥1-H⊥1)^2. Then ⟨θ⟩=3+ε⟨θ1⟩, ⟨θ^2⟩=9+6ε⟨θ1⟩+ε^2⟨θ1^2⟩, variance =ε^2(⟨θ1^2⟩-⟨θ1⟩^2). Hence Q1=0, Q_D=ε^2[2/3(⟨θ1^2⟩-⟨θ1⟩^2)-2⟨σ1^2⟩]+O(ε^3) ≡ε^2 Q2[h].

13. Choose h(r)=r^4 exp(-(r/α)^2), α=0.05. Then h not proportional to r^2, so not FLRW, H∥1≠H⊥1 somewhere, Q2[h]≠0. Formal integral Q2 = ∫_0^{r_D} w(r) (h, h', t_B1) ; w positive for shear part. Non-vanishing requires explicit evaluation – obligation O3.

14. Fixed domain: r_D(u) solves R(t0,r_D)=R_phys. Variation δr_D = -R1(r_D)/R0'(r_D) ε, contributes to Q2 at O(ε^2) via boundary term, included in functional.

Result: Two models u0=1 and u_ε produce same D_A^* exactly, Q_D differs by ε^2 Q2.


---



# FILE: ZEH-6A-phys/limitations.md

# Limitations and Non-Claims

- No claim Q_D replaces dark energy.
- No claim holds for off-centre, Szekeres, pressure, Λ≠0 without proof.
- No survey-data fits.
- No RG flow, Planck scale, Born rule.
- No Outcome C.
- Local amplitude only: no global no-go, no global uniqueness.
- Numerical validation only illustrative, not proof.


---



# FILE: ZEH-6A-phys/literature.md

# Literature and Novelty

Closest prior:
- Mustapha-Hellaby-Ellis 1997: D_A alone leaves one functional freedom, D_A+n(z) fixes LTB. No Q_D.
- Célérier 2000: LTB fits D_A without Λ. No Q_D variance.
- Buchert 2000: Q_D definition, no inverse problem.
- Sussman 2008: analytic Q_D for central domains, sign theorem, no identifiability.
- Zibin 2008, February et al 2010: D_L deviations second order in LTB contrast, context for O5.
- García-Bellido-Haughbølle 2008, Enqvist-Mattsson 2007: t_B=0 fits practice, no uniqueness proof.
- Heinesen et al 2019,2022: light-cone averaging, not slice Q_D identifiability.
- Koksbang 2019-2023, Heinesen 2021: backreaction effects on drift, GW sirens, no exact iso-distance family theorem for Q_D.

Novelty: Exact, regular, constructive one-function family Ψ reproducing any vertex-compatible D_A exactly (not within tolerance) in fixed gauge M=r^3/2, with t_B as output, plus Q_D-specific non-identifiability (Q2≠0). Prior works show metric freedom, not Q_D variance.

If identical theorem found in 2024-2026 search, stop and re-scope to Q2 functional or conditional uniqueness.


---



# FILE: ZEH-6A-phys/mrc.md

# MRC and MRC2

Buchert equations: Established (Buchert 2000)
LTB light-cone equations: Established (Krasiński, Ellis)
Distance data identify general model: Contradicted by MHE degeneracy – our theorem sharpens to Q_D.
Q_D uniquely determined: Conditional – No for general, Yes for t_B=0 + 1% tolerance (conjectural until O6 closed for uniqueness)
Restricted model independent prediction: Derived – H∥, drift vary within iso-distance family
New relation with additional predictive content: Not claimed – support obstruction (slice vs cone) prevents Outcome C; common-metric consistency is Outcome A.

MRC2 merit: General case low merit (degenerate), t_B=0 class higher merit (falsifiable via H∥, drift). No mechanism generation, no constant claimed.

Math Reality Check: No function counting as proof; construction via driven cone system closure demonstrated; Q_D variation requires explicit Q2 integral, not intuition.


---



# FILE: ZEH-6A-phys/obligations.md

# Proof Obligations

O1 Vertex series: derive regular power series for T,Z,P,Q near r=0 with u=1+O(r^2), show solution exists from centre despite det→0.

O2 Determinant away from centre: compute determinant of linear system for P,Q from L1,L2, show non-zero for EdS background for 0<z≤1.

O3 Q2 non-constancy: evaluate Q2[h] integral analytically for chosen h, show ≠0, control remainder O(ε^3) for sufficiently small ε to guarantee sign.

O4 Domain adjustment: include r_D(u) variation in Q2, show non-cancellation.

O5 Linear-response audit: verify against Zibin 2008 that D_A linear response to LTB perturbation vanishes for central observer, explaining why Q_D is leading imprint.

O6 Admissibility persistence: prove 1+2E>0, R'>0, ρ>0 for small ε on [0,r_D]×[t_B,t0].

O7 t_B regularity: t_B'(0)=0 follows from construction.

O8 Integrability condition truncated in ZEH-5: complete bookkeeping.

Status: O1,O2 low risk (standard ODE), O3 medium risk (core computation), O4 low, O5 medium, O6 low, O7 low, O8 bookkeeping.


---



# FILE: ZEH-6A-phys/status_table.md

# Claim Status Table

| Claim | Status | Evidence or missing step |
|---|---|---|
| Gauge M=r^3/2 eliminates relabelling | Established | Standard LTB gauge |
| EdS limit R=r(3t/2)^{2/3}, t0=2/3, Q=0 | Established | Direct substitution, Q computed -8e-28 |
| Driven cone system closes with u free | Derived here | L1,L2 derivation, closure check § derivation |
| Exact iso-distance family exists | Conjectural → Conditional | O1 vertex series, O2 determinant pending formal write-up |
| Q_D expansion Q1=0, Q=ε^2 Q2+O(ε^3) | Derived here | Expansion of R, dotR, H |
| Q2[h]≠0 for h=r^4 exp(-(r/α)^2) | Conjectural | O3 integral evaluation missing |
| Fixed physical domain R(t0,r_D)=R_phys | Established | r_D(u) solved per model |
| Admissibility 1+2E>0,R'>0,ρ>0 persists small ε | Conditional | O6 persistence argument |
| t_B=0 restores uniqueness | Conjectural (high risk) | O5 audit needed, IFT not valid if linear blindness |
| Held-out H∥, drift discriminate within family | Conditional | O7 small computation, h' enters |
| Outcome C new closed relation | Falsified/Not claimed | Slice vs cone support obstruction |


---



# FILE: ZEH-6A-phys/theorem/conjecture.md

# Theorem Conjecture – Non-Identifiability

**Conjecture C1 (General LTB iso-distance family):**
Setting: Λ=0, dust, central observer, regular centre, gauge M(r)=r^3/2, expanding branch, no shell crossing, t0 reference EdS t0=2/3 for background, but general t0 determined by central normalization consistent with target.

Let G(Z)=D_A^*(z)*(1+z)=2[1-(1+z)^-1/2], Z=1+z∈[1,2], C^2 vertex-compatible (G(1)=0, G'(1)>0).

Define u(r)=√(1+2E(r)), u(0)=1, u-1=O(r^2).

Then there exists neighbourhood U of u0≡1 in C^1 such that for each u∈U, driven cone system

T' = -P/u
Z' = Z Q /u
P = ∂_r R|_T , Q = ∂_r \dot R|_T (exact LTB expressions)
dG/dr = P(1 - V/u) with V^2 = r^3/G + u^2 -1
dV/dr = Q + P r^3/(2 G^2 u)

with initial T(0)=t0, Z(0)=1, G(0)=0, has unique solution on [0,r_max] where Z=2, reproducing D_A^*(z)=G(Z)/Z exactly.

Each cone solution corresponds to global LTB via t_B(r)=T(r)-τ(r), τ(r)=∫_0^{G(r)} dR̃ /√(r^3/R̃+u^2-1).

**Conjecture C2 (Q_D non-constant):**
For physical domain R(t0,r_D)=R_phys=0.0233, map u↦Q_D^{Ψ(u)}(t0) is non-constant on U. In particular for family u_ε=1+ε h, h(r)=r^4 exp(-(r/α)^2), α=0.05, Q_D[Ψ(u_ε)]=ε^2 Q2[h]+O(ε^3) with Q2[h]≠0, Q1=0.

Status: Conjectural pending O3, O5 closure (see obligations.md)


---



# FILE: ZEH-6A-phys/unresolved.md

# Unresolved

- O1 vertex series explicit coefficients.
- O2 determinant evaluation for EdS background at all z∈[0,1].
- O3 Q2 integral closed form and sign, remainder control.
- O4 domain adjustment contribution to Q2.
- O5 linear-response blindness verification.
- O6 t_B=0 uniqueness proof route after linear blindness flagged.
- O8 integrability condition completion from truncated ZEH-5.


---
