# ZEH-PAPER-SCOPE-1: Literature, Novelty, and Contribution Lock

## 1. Recommended provisional title

**Identifiability and Functional Degeneracy of Buchert Kinematical Backreaction from Past-Light-Cone Distance-Redshift Observations in Central-Observer Lemaître-Tolman-Bondi Cosmology**

## 2. One-sentence primary research question

Within central-observer LTB dust with fixed gauge $M(r)=r^3/2$, does $D_A(z)$ alone on $0\le z\le1$ uniquely determine the present-day Buchert scalar $Q_{\cal D}(t_0)$ on a comoving dust slice for a fixed physical domain $R(t_0,r_{\cal D})=100\,{\rm Mpc}$, and what changes under the explicit structural restriction $t_B(r)\equiv0$?

## 3. Research gap, supported by primary literature

LTB inverse theory and Buchert averaging are disjoint in the literature.

| Source | What it actually proves | Leaves unresolved | Difference that matters |
|---|---|---|---|
| **Mustapha-Hellaby-Ellis 1997, Lu-Hellaby 2007** | $D_A(z)$ + redshift-space mass density $\mu(z)$ or number counts $n(z)$ determine two free LTB functions $E(r),t_B(r)$; $D_A(z)$ alone leaves one functional freedom. Algorithmic, not theorem form. | No statement about $Q_{\cal D}(t_0)$, which is defined on $t=t_0$ slice, not on cone. | Our gap: propagate that one-function light-cone degeneracy into explicit variance of slice integral $Q_{\cal D}(t_0)$. |
| **Célérier 2000** | LTB can fit $D_A(z)$ of $\Lambda$CDM without $\Lambda$. | Does not compute $Q_{\cal D}$, does not quantify degeneracy range. | We quantify $Q_{\cal D}$ variance at fixed $D_A$. |
| **Buchert 2000,2001** | Exact non-perturbative $Q_{\cal D}=2/3(\langle\theta^2\rangle-\langle\theta\rangle^2)-2\langle\sigma^2\rangle$, integrability condition. $E(r),t_B(r)$ given. | No inverse problem, no light-cone reconstruction. | Bridge: $E(r),t_B(r)$ are not given but reconstructed from $D_A$. |
| **Sussman 2008, 2011 [arXiv:0807.1145, arXiv:1102.2663]** | Closed analytic expression for $Q_{\cal D}$ for central spherical domains containing symmetry centre; sign fixed by curvature type: $Q_{\cal D}\le0$ elliptic, $Q_{\cal D}\ge0$ hyperbolic for that domain class. Does not link to observables. | No identifiability theorem; no observable input. | Uses Sussman formula for $Q_{\cal D}$ evaluation, but asks whether observable $D_A$ fixes its arguments. |
| **Green&Wald 2011,2015** | Backreaction negligible in high-frequency small-amplitude limit. | Excludes long-wavelength exact LTB voids, non-perturbative $E(r),t_B(r)$. | Our regime is non-perturbative LTB, not covered. |
| **Heinesen-Mourier-Buchert 2019, Buchert et al 2018 CQG 35 24LT02, Heinesen 2021** | Covariant light-cone averaging formalism, closure conditions not fixed by equations alone. Focus on drift, area distance as light-cone averages, not slice $Q_{\cal D}$ identifiability from $D_A$. | Does not prove whether slice $Q_{\cal D}$ is determined by cone data. | Distinguish slice $Q_{\cal D}$ vs light-cone backreaction; our question is about slice quantity reconstructed from cone. |
| **Koksbang 2019-2023, Heinesen 2021a,b, recent 2024-2026 constraints** | Effects of inhomogeneities on drift, GW sirens, machine-learning backreaction; first observational constraints on total backreaction consistent with zero. | No LTB exact non-identifiability theorem for $Q_{\cal D}$ from $D_A$ alone. | Closest to observable constraints, but uses template metrics, not LTB inverse uniqueness. |

**Gap synthesis:** No primary source proves analytically that fixing $D_A(z)$ exactly over $0\le z\le1$ leaves $Q_{\cal D}(t_0)$ undetermined, nor proves conditional uniqueness under $t_B\equiv0$. Sussman gives $Q_{\cal D}$ formula, MHE gives degeneracy of metric functions, but their composition — the map $D_A\to Q_{\cal D}$ — is not addressed. This is a pen-and-paper gap, not requiring new physics.

## 4. One principal candidate contribution [conjectural until obligations close]

**Theorem pair conjectural:**

* **Theorem 1 – General LTB non-identifiability [conjecture, to be proved]:** In gauge $M=r^3/2$, regular centre, expanding branch, $R'>0$, $1+2E>0$, let $D_A^*(z)$ be $C^2$ vertex-compatible ($D_A^*(0)=0$, $dD_A^*/dz|_0>0$) e.g. EdS target $2[1-(1+z)^{-1/2}]/(1+z)$. Then there exists a $C^1$-neighborhood ${\cal U}$ of $u_0\equiv\sqrt{1+2E}=1$ such that each $u\in{\cal U}$ generates a regular LTB model reproducing $D_A^*(z)$ *exactly* on $$ via $R(t(r),r)=D_A^*(z(r))$, with bang time $t_B(r)$ as output $t_B=T(r)-\tau(r)$, where $T$ is cone time. The map $u\mapsto Q_{\cal D}^{\Psi(u)}(t_0; R_{\rm phys}=100\,{\rm Mpc})$ is non-constant.[0][1]

* **Theorem 2 – Simultaneous-bang conditional uniqueness [conjecture, highest risk]:** Under explicit restriction $t_B(r)\equiv0$, the same $D_A^*(z)$ determines $E(r)$ locally uniquely (Picard-Lindelöf for driven cone system with $u$ as unknown, not input), hence $Q_{\cal D}(t_0)$ is uniquely determined for fixed physical domain. If linear-response audit shows $D_A$ is second-order in LTB contrast [Zibin 2008, February et al 2010], Theorem 2 cannot use IFT from linearization and must use direct ODE uniqueness.

Why matters: Negative result prevents promoting common-metric consistency (Outcome A) into new predictive law (Outcome C). Positive companion makes negative informative: slice $Q_{\cal D}$ is not a cone observable except when universe is required to have begun everywhere at once.

## 5. Minimum mathematical obligations

* **O1:** Exact LTB setup, gauge $M=r^3/2$, regular centre $E=O(r^2)$, $t_B'(0)=0$, admissibility $1+2E>0,\rho>0,R'>0$.
* **O2:** Driven on-cone system: state $(T,Z,P,Q)=(t,1+z,R',\dot R')$, $u=\sqrt{1+2E}$ free input, identities $T'=-P/u$, $Z'=ZQ/u$, $V^2=r^3/G+u^2-1$, $G=D_A^*(z)(1+z)$, and two linear relations L1 from $dG/dr=P(1-V/u)$ target differentiation, L2 from $\partial_r$ shell equation.
* **O3:** Closure check: $d/dr$ of shell eq along cone reproduces L2 identically when L1 imposed – would-be extra condition not independent, leaving $u(r)$ free. Write vertex series to handle determinant $\to0$ at $r=0$.
* **O4:** Realizability: cone $\to$ global model, $t_B(r)=T(r)-\tau(r)$ output, persistence of open conditions for small amplitude.
* **O5:** $Q_{\cal D}$ functional to $O(\epsilon^2)$: $Q_{\cal D}$ is quadratic (variance + shear), so non-constancy requires $Q_2$ computation; exhibit two profiles $u_1\neq u_2$ same $R_{\rm phys}$ different $Q$. Pre-registered falsifier: if $Q_2$ constant on ${\cal U}$, advertised non-identifiability fails.
* **O6:** Fixed physical domain: $r_{\cal D}(u)$ from $R(t_0,r_{\cal D})=R_{\rm phys}$.
* **O7:** Held-out: $H_\parallel=Q/P$ varies at $O(\epsilon)$ even when $D_A$ does not (via $2uu'$ term), drift varies via $Z(r)$ map.
* **O8:** FLRW limit $Q_{\cal D}=0$ recovery.

## 6. Assumptions, regime, scale, domain, foliation, observable set

Classical GR, dust, $\Lambda=0$ synthetic control, $c=G=1$, $H_0=1$, $t_0=2/3$, central observer $r=0$, $z\le1$, domain $\sim10-100\,{\rm Mpc}$ comoving sphere $R(t_0,r_{\cal D})=100\,{\rm Mpc}$ ($H_0R/c\simeq0.0233$), synchronous comoving foliation, Buchert convention. Physical domain vs coordinate boundary distinguished. Input for reconstruction $D_A(z)$ only; $H_\parallel(z),\dot z(z)$ held-out for discrimination, not used to fit in main theorem. EdS distance target controlled example, not mandatory for general theorem.

## 7. Explicit claims the paper will not make

* No claim $Q_{\cal D}$ replaces dark energy or explains acceleration.
* No claim holds for off-centre observers, Szekeres, non-dust, $\Lambda\neq0$, without proof.
* No claim $Q_{\cal D}$ gauge-invariant under non-comoving foliations.
* No claim empirical confirmation from survey catalogs; synthetic-target success is not nature.
* No Outcome C: no new closed local consistency relation $Q_{\cal D}=F[D_A]$ with extra predictive content beyond reconstruction; slice vs cone support obstruction stands.
* No claim LTB describes our universe.

## 8. Out-of-scope and stopping condition

Out: multi-centre models, pressure, scalar-tensor, modified gravity, N-body, CMB/BAO survey fitting, quantum gravity, RG flow, Born rule, software-engineering artifact.

Stopping condition: Pen-and-paper proofs of Theorems 1 and 2 plus quantification of functional degeneracy range $\Delta Q_{\cal D}(t_0)$ for controlled EdS target, with regularity and domain dependence stated. If O5 yields invariance branch, stop and re-scope to invariance theorem. If novelty check finds identical theorem, stop.

## 9. Proposed paper outline

1. Introduction: averaging problem, inverse problem, primary question
2. Framework: LTB gauge $M=r^3/2$, Buchert $Q_{\cal D}$, past-null geodesics, $D_A$
3. Non-identifiability in general LTB: driven cone system, closure analysis, family $\Psi$
4. $Q_{\cal D}$ variance: $Q_2$ functional, two profiles same $D_A$ different $Q$
5. Simultaneous-bang restriction: uniqueness argument[conditional]
6. Breaking degeneracy: $H_\parallel$, drift as discriminators
7. Relation to prior work: MHE, Célérier, Sussman, Heinesen, Koksbang
8. Conclusions: what cone data cannot know

## 10. Go / revise / stop recommendation

**GO (revised scope)** – analytical, bounded, literature gap genuine. No ZEH-6 numerics required to establish primary claims; optional illustrative plot of degeneracy bounds allowed only after theorems closed.

### Adversarial scope and novelty review

**Attack 1 – Already proved:** MHE 1997 already says $D_A$ alone does not determine metric, so $Q_{\cal D}$ non-identifiability is corollary. **Response:** MHE does not evaluate $Q_{\cal D}$; Sussman formula shows $Q_{\cal D}$ is $O(\epsilon^2)$ while $D_A$ deviation is $O(\epsilon^2)$, so non-constancy not automatic – needs O5 audit and $Q_2$ computation. Narrow scope to $Q_{\cal D}$-specific variance.[Zibin]

**Attack 2 – Hidden assumption – domain:** $Q_{\cal D}$ depends on $r_{\cal D}(u)$; if physical domain adjusted, $Q$ difference could be absorbed. **Response:** O6 explicitly solves $R(t_0,r_{\cal D})=R_{\rm phys}$ per model; non-constancy must survive adjustment, otherwise theorem fails – included as obligation.

**Attack 3 – Foliation ambiguity:** Buchert $Q_{\cal D}$ foliation-dependent; comparing different $u$ may compare different foliations. **Response:** Foliation fixed comoving dust; $E(r),t_B(r)$ variations are physical, not foliation change; stated as non-claim about other foliations.

**Attack 4 – Linear blindness:** If $D_A$ response to linear LTB is zero, IFT cannot prove uniqueness under $t_B=0$. **Response:** Flagged as high-risk O6; uniqueness must come from direct ODE structure, not linearization; fallback to monotone $E$ subclass or state as conditional.

**Attack 5 – Outcome C inflation:** Reconstructing $E(r)$ from $D_A$ then computing $Q_{\cal D}$ is Outcome A (common-metric consistency), not new law. **Response:** Paper explicitly will not claim Outcome C; support obstruction theorem that slice integral cannot be expressed as local function of cone data.

**Strongest objection:** Closest prior Sussman gives closed $Q_{\cal D}$ formula for central domains, and MHE gives $D_A$ degeneracy – composition may be considered trivial by referee. **Defence:** Composition not trivial because $Q_{\cal D}$ is $O(\epsilon^2)$ and $D_A$ degeneracy is exact/nonlinear; theorem requires constructive exact iso-distance family preserving regularity, which prior works do not provide.

**Narrowest viable scope:** Exact one-function iso-distance family $\Psi$ with $t_B$ output, plus $Q_2$ non-constancy for fixed $R_{\rm phys}$. If $Q_2$ constant, paper reduces to exact degeneracy structure alone – still publishable methods note.

**Abandonment criteria:** If literature search finds identical theorem (exact iso-distance family + $Q_{\cal D}$ variance) in Koksbang/Heinesen 2022-2024 or Bolejko-Krasiński volume; or if $Q_2$ identically constant; or if $t_B=0$ uniqueness fails and no restricted subclass restores it.
