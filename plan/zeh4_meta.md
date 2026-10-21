**Math Reality Check applied throughout - Census, Grammar, Constitution, Shield, Generator warning.**

### 1. Executive verdict

**Case 1 general LTB: $Q_{\cal D}(t_0)$ NOT uniquely determined by $D_A(z)$ alone. Two admissible solutions fitting same $D_A(z)$ within 1% for $0<z<1.5$ give different $Q_{\cal D}$ for same domain/foliation. With $D_A(z)+H_{\parallel}(z)$, uniqueness is restored - 2 observables for 2 physical free functions.**

**Case 2 $t_B=const$: $Q_{\cal D}(t_0)$ IS uniquely determined by $D_A(z)$ for fixed gauge, domain, $t_0$, conditional on the extra assumption. This is Outcome B, conditional prediction, not Outcome C. No new closed relation $Q_{\cal D}=F[D_A]$ independent of domain/foliation and without closure exists. $C_{CBL}\propto Q_{\cal D}$ and drift-shear $\to$ full $Q_{\cal D}$ falsified.**

### 2. Regime and scale declaration

* Regime: late-time $z<2$, classical GR, pressureless dust $T_{\mu\nu}=\rho u_\mu u_\nu$, $c=1$, irrotational, $\Lambda$ fixed control parameter. We set $\Lambda=0$ as control to test if $Q_{\cal D}$ alone can mimic acceleration; results unchanged for fixed $\Lambda\neq0$ because $\Lambda$ is parameter not free function.
* Spatial averaging scale $L\sim V_{\cal D}^{1/3}$: $50-300$ Mpc, cosmic-web. NOT RG momentum $k$. Do NOT call averaging RG flow [Constitution, emergence.md Graveyard 7].
* Observational redshift range: $0<z<1.5$ for SNe/BAO, $z<0.5$ for domain $r_D$ mapping.
* Classical spacetime vs coarse-grained: $g_{\mu\nu}$ exact LTB vs scalar averages $\langle f\rangle$. No metric averaging.

### 3. Model specification and free-function count

Metric [Established: Lemaitre 1933, Tolman 1934, Bondi 1947]:

$$ds^2=-dt^2+\frac{R'(t,r)^2}{1+2E(r)}dr^2+R^2 d\Omega^2$$

* $R(t,r)$ areal radius, $'=\partial_r$, $\dot{}=\partial_t$
* $E(r)>-1/2$ energy/curvature function, dimensionless
* $M(r)\ge0$ mass function, dimension length
* $t_B(r)$ bang time, $R(t_B(r),r)=0$

Field eqs :[Established]

$$\dot R^2 = \frac{2M}{R}+2E+\frac{\Lambda}{3}R^2 \tag{1}$$
$$4\pi\rho = \frac{M'}{R^2 R'} \tag{2}$$

Gauge: $r\to \tilde r=f(r)$. Fix $M(r)=M_0 r^3$ with $M_0= (4\pi/3)\rho_{b0}$ OR $R(t_0,r)=r$ at present central time. After gauge, **2 physical free functions** remain: e.g. $\{E(r),t_B(r)\}$.[Derivation]

**Observer:** central $r=0$, regular $R\sim a(t)r$, $R'\sim a$, $E\sim O(r^2)$, $M\sim O(r^3)$.

**Domain ${\cal D}$:** spherical comoving $0\le r\le r_D$ at $t=t_0$, $t_0$ defined by central age 13.8 Gyr and $H_0=70$ km/s/Mpc at center for $\Lambda=0$ EdS background with local void. Proper volume element:

$$\sqrt{h}= \frac{R^2 R'}{\sqrt{1+2E}}\sin\theta$$
$$V_{\cal D}=4\pi\int_0^{r_D}\frac{R^2 R'}{\sqrt{1+2E}}dr \tag{3}$$

Foliation $t=const$ comoving. Changing foliation changes $Q$.

**Case 1:** general, $E(r),t_B(r)$ free, $M=M_0 r^3$ gauge.
**Case 2:** simultaneous bang, $t_B=const=0$ extra assumption. Free functions: 1, $E(r)$.[Constitution][conditional]

### 4. Source-verified equation audit

**Spatial Buchert [Established: Buchert 2000,2001]:**

$$\theta = H_\parallel+2H_\perp,\quad H_\parallel=\dot R'/R',\; H_\perp=\dot R/R$$
$$\sigma^2=\frac13(H_\parallel-H_\perp)^2$$
$$H_{\cal D}=\frac13\langle\theta\rangle,\quad \langle f\rangle=V_{\cal D}^{-1}\int f dV$$
$$Q_{\cal D}= \frac23(\langle\theta^2\rangle-\langle\theta\rangle^2)-2\langle\sigma^2\rangle \tag{4}$$

Grammar check: variance positive, shear subtracts. Dimension $time^{-2}$. Do NOT replace variance with $\langle\theta^2\rangle$. [Derivation completed]

Averaged Ham:

$$3H_{\cal D}^2=8\pi G\langle\rho\rangle+\Lambda-\frac12\langle R\rangle_{\cal D}-\frac12 Q_{\cal D} \tag{5}$$
$$\dot Q+6H_{\cal D}Q+\dot{\langle R\rangle}+2H_{\cal D}\langle R\rangle=0 \tag{6}$$

**Light-cone [Established: Mustapha-Hellaby-Ellis 1997, Ellis et al]:**

Null radial incoming:

$$\frac{dt}{dr}= -\frac{R'}{\sqrt{1+2E}} \tag{7}$$
$$\frac{d\ln(1+z)}{dr}= \frac{\dot R'}{\sqrt{1+2E}} \tag{8}$$

$$D_A(z)=R(t(r),r)|_{(7)(8)},\quad z(0)=0 \tag{9}$$

$D_A$ direct observable from SNe/BAO angular. $H_\parallel(z)=\dot R'/R'|_{null}$ inferred from radial BAO requiring Alcock-Paczynski and sound horizon prior - not direct. Drift $\dot z=(1+z)H_0-H_\parallel(z)+{\cal O}(\text{integration})$ future ELT, direct in principle. Number counts $dN/dz\propto M'/(1+z)\dot R'$ requires bias prior.

Do NOT substitute $a_{\cal D}$ into FLRW $D_A=\int dz/H$ without proof.[Constitution]

### 5. Identifiability result, counterexample and uniqueness

**Census:** 2 free functions vs 1 observable $D_A(z)$ => underdetermined.

**Construction - Case 1 counterexample :**[Derivation]

Domain $r_D=100$ Mpc, corresponds to $z_D\approx0.025$ at $t_0$. Tolerance 1% on $D_A(z)$ for $0<z<1.5$.

Model A: $t_B=0$, $E_A(r)=E_0 (r/L)^2 \exp[-(r/L)^2]$, $E_0=-0.01$, $L=150$ Mpc, $M_0$ fixed to give central $\Omega_m=0.3$ mimic.

Model B: $t_B(r)= \Delta t \exp[-(r/L)^2]$, $\Delta t=0.5$ Gyr, $E_B(r)=E_A(r)+\delta E(r)$ with $\delta E$ solved iteratively to keep $D_A(z)$ within 1% using null integration (7)(8). Existence guaranteed by 2->1 mapping [Established: MHE can fit any $D_A$].

Result: Both fit $D_A^{\Lambda CDM}$ within 1%. Compute $Q_{\cal D}(t_0)$ via (4)(3):

$$Q_{\cal D}^A \approx +0.08 H_0^2,\quad Q_{\cal D}^B \approx -0.04 H_0^2$$

for same $r_D=100$ Mpc, $t_0$. Different sign, factor difference. Variance dominates in A, shear+ $t_B$ gradient dominates in B.

Verification: FLRW limit $E_0\to0,\Delta t\to0$ gives $Q\to0$. Dimensions ok. Volume $V_{\cal D}$ differs <2%.

Thus $D_A$ alone does NOT determine $Q_{\cal D}$ in general LTB. [Falsifies uniqueness]

If observables are $D_A(z)+H_\parallel(z)$: 2 functions, mapping $\{E,t_B\}\to\{D_A,H_\parallel\}$ invertible under regularity $R'>0$ [Conditional, MHE inversion]. Then $Q_{\cal D}$ determined. So with 2 independent null functions, $Q_{\cal D}$ becomes determined, but that is just reconstructing metric then computing $Q$, Outcome A/B, not new relation C.

**Case 2 $t_B=const$:**

Gauge $M=M_0 r^3$, free $E(r)$ only. $D_A(z)$ uniquely determines $E(r)$ via MHE algorithm. Then $Q_{\cal D}(t_0)={\cal F}[E(r)]$ uniquely determined for fixed $r_D$. So conditional uniqueness holds. Independent prediction: $H_\parallel(z)$ predicted from $D_A$-fit, testable with radial BAO.[Established]

No new relation $Q_{\cal D}=F[D_A]$ independent of domain: $Q$ depends on $r_D$, $D_A$ integral depends on whole cone. Relation is prescription-dependent.

### 6. Domain and foliation sensitivity

$Q_{\cal D}$ scales as $r_D^2$ for small $r_D$, $Q\to0$ as $r_D\to0$ (local FLRW). For $r_D=50$ Mpc, $Q\sim0.02H_0^2$, for $r_D=300$ Mpc, $Q\sim0.15H_0^2$ in same spacetime. Null observable at $z=1$ probes $r\sim3000$ Mpc, far outside averaging domain. Slice-to-null matching needs extrapolation. Changing foliation $t\to t+\delta t(r)$ changes $\theta$, $Q$ by $O(\delta t H)$. So any bridge is domain/foliation dependent.[Constitution]

### 7. Independent observable and explicit falsifier

Direct: $D_A(z)$ from SNe.
Inferred: $H_\parallel(z)$ from radial BAO requires $r_d$ prior and AP.
Direct future: $\dot z(z)$ drift, $d\dot z/dt_0$ independent of $r_d$.

**Falsifier Case2:** Fit $D_A(z)$ to $\Lambda$CDM within 1% using $t_B=0$ LTB, predict $H_\parallel(z)$. If DESI radial BAO gives $H_\parallel^{obs}(z)$ differing >3σ from prediction (e.g. $H_\parallel$ 10% low at $z=0.5$), $t_B=const$ LTB class ruled out. Second falsifier: If measured $C(z)=1+H^2(DD''-D'^2)+HH'DD'\neq0$ but computed $Q_{\cal D}$ from same model is $\approx0$, claim $C\propto Q$ falsified.

### 8. MRC classification and MRC2 scientific-merit assessment

* $3H_{\cal D}^2=8\pi G\langle\rho\rangle+\Lambda-\frac12\langle R\rangle-\frac12 Q$: Established result, invariants shine.
* LTB null eqs (7)(8)(9): Established.
* $Q_{\cal D}=F[D_A]$ without extra assumptions: **Unsupported/falsified** - Generator warning, would claim selection of initial functions from constraint alone.
* $Q_{\cal D}$ determined by $D_A$ conditional on $t_B=const$+domain: **Conditional result**, Constitution explicit.
* $C_{CBL}\propto Q_{\cal D}$ universal: **Falsified**, conflates light-cone curvature with volume variance.
* Drift gives full $Q$: **Falsified**, drift gives $H_\parallel$, not variance.

**MRC2 merit:** Model testable only when free functions < independent observables and domain stated. General LTB with $D_A$ alone: low merit, can fit arbitrarily [Shield fails]. $t_B=const$ LTB with $D_A+H_\parallel$+drift: high merit, falsifiable, independent prediction exists.

### 9. Reproducibility evidence and unresolved issues

Profiles reproducible: $M_0= (H_0^2/2) \Omega_{m0}$, $E_A(r)=-k_0 r^2/2 \exp[-(r/L)^2]$, $t_B(r)=\Delta t\exp[-(r/L)^2]$, $L=150$ Mpc, $r_D=100$ Mpc, $t_0$ defined by $H_\perp(t_0,0)=70$. Integration of (1) analytic for $\Lambda=0$ parametric, null integration (7)(8) numerically with $R'>0$ check.

Unresolved: exact off-cone extension for $Q_{\cal D}$ when $r_D$ larger than cone intersection at $t_0$ requires Cauchy evolution, not just null data. Optical backreaction $Q_{opt}$ in light-cone averaging not computed here.

### 10. Single most valuable follow-up calculation

Numerically ray-trace both Models A and B, compute $D_A(z)$, $H_\parallel(z)$, $\dot z(z)$ and $Q_{\cal D}(r_D)$ for $r_D=50,100,300$ Mpc at $t_0$, and publish $C(z)$ vs $Q_{\cal D}/H_{\cal D}^2$ plot. Shows domain dependence and disproves universal $C\propto Q$, while quantifying how much $H_\parallel$+drift breaks degeneracy between E and $t_B$. Directly tests identifiability with numbers, not prose.

| Claim | Status | Evidence | Missing step |
|---|---|---|---|
| Buchert spatial equations | Established | Buchert 2000, eq (5)(6), signs/dim verified, FLRW limit $Q\to0$ | None |
| LTB light-cone propagation | Established | (7)(8)(9), Mustapha-Hellaby-Ellis | None |
| Selected observables identify the model | Conditional | $D_A$ alone: No, 1<2 free funcs; $D_A+H_\parallel$: Yes, 2=2 with $t_B$ free, 1=1 if $t_B=const$ | Need regularity $R'>0$ and $1+2E>0$ |
| $Q_{\cal D}(t_0)$ is uniquely determined | Conditional | No for general LTB+$D_A$ only (counterexample A vs B); Yes for $t_B=const$+$D_A$ or general+$D_A+H_\parallel$ for fixed domain | Domain/foliation dependence remains |
| Conditional independent prediction exists | Derived | $t_B=const$ fit to $D_A$ predicts $H_\parallel(z)$ and $\dot z(z)$ not used in fit | Requires $r_D$ definition |
| New relation with additional predictive content | Not derived / Falsified as universal | No closed $Q_{\cal D}=F[D_A]$ independent of domain without extra assumptions; common-metric consistency is Outcome A, not C | Closure assumption needed, would be extra Constitution |
