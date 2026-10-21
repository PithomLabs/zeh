**Per Math Reality Check: applied throughout. Classification per task.**

### 1. Executive verdict

**Not derived as a closed, nontrivial spatial-to-null relation constraining $Q_{\cal D}$ from past-light-cone observables alone without extra assumptions. Partially derived conditional on $t_B=const$ and fixed domain/foliation, with independent predictive content only in that conditional class. Falsified as universal proportionality $C_{CBL}\propto Q_{\cal D}$ or drift-shear $\to$ full $Q_{\cal D}$.**

Outcome A [common-metric consistency] holds trivially. Outcome B [fixed LTB predicts multiple observables] holds. Outcome C [new closed relation removing free functions and specifically constraining $Q_{\cal D}$] does NOT hold in full LTB without closure.

### 2. Applicable regime and RG/physical scales

* Regime: late-time, classical GR, $c=1$, irrotational pressureless dust $T_{\mu\nu}=\rho u_\mu u_\nu$, optional $\Lambda$ as constant parameter, no rotation. No quantum, no particle generation, no Born rule.
* Physical spatial scale: averaging domain ${\cal D}$ Mpc to $100$s Mpc. Cosmic web scale.
* Averaging scale $L\sim V_{\cal D}^{1/3}$ is NOT RG momentum scale $k$. $k$ is field theory cutoff. Do not call $\langle\cdot\rangle_{\cal D}$ RG flow. Emergence shines as EFT autonomy [emergence.md Shines 3] but does NOT fix couplings [Graveyard 7].
* Cosmological redshift/time: $z$ is null observable, $t$ is foliation time. They are not interchangeable. Foliation is choice, not derived.
* Classical spacetime vs coarse-grained: $g_{\mu\nu}$ exact LTB vs $\langle g\rangle$ does not exist. Only scalars averaged. Buchert is scalar averaging, not metric averaging.

### 3. Definitions and assumptions

**Theory:** GR. No modified gravity.

**Metric, LTB, $c=1$, comoving synchronous gauge:**

$$ds^2=-dt^2+\frac{R'(t,r)^2}{1+2E(r)}dr^2+R(t,r)^2d\Omega^2$$

* $R(t,r)$ areal radius, $R'=\partial_r R$, $\dot R=\partial_t R$
* $E(r)$ energy/curvature function, dimensionless, $1+2E>0$
* $M(r)$ Misner-Sharp mass, $M\ge0$, dimension length
* Bang function $t_B(r)$: $R(t_B(r),r)=0$
* $u^\mu=\delta^\mu_t$, dust.

Field equations [Established result: Lemaitre 1933, Tolman 1934, Bondi 1947]:

$$\dot R^2 = \frac{2M(r)}{R}+2E(r)+\frac{\Lambda}{3}R^2 \tag{LTB-EoM}$$
$$4\pi\rho = \frac{M'}{R^2 R'}$$

**Coordinate freedom:** $r\to \tilde r=f(r)$ monotonic. Fixes one function. After gauge, 2 independent physical free functions, e.g. $E(r)$ and $M(r)$ with $t_B(r)$ then determined, or $E(r)$ and $t_B(r)$ after fixing $M\propto r^3$. Count is 2. [Derivation completed] Not 1. Removing a function without statement is extra assumption.[Constitution]

**Observer:** central $r=0$, regular center $R\sim a(t)r$, $R'\sim a$, $E\sim O(r^2)$.

**Domain ${\cal D}$:** spherical comoving $0\le r\le r_D$ at fixed $t=t_0$, $t_0>t_B$. Proper volume:

$$dV = \frac{R^2 R'}{\sqrt{1+2E}}\sin\theta dr d\theta d\phi$$
$$V_{\cal D}=4\pi\int_0^{r_D}\frac{R^2 R'}{\sqrt{1+2E}}dr$$
$$\langle f\rangle_{\cal D}=V_{\cal D}^{-1}\int_{\cal D} f\, dV$$

Foliation is $t=const$ comoving. Different foliation changes averages. Domain prescription is part of Constitution.

**Free functions audit:** 2 functions after gauge. Simultaneous bang $t_B=const$ is extra physical assumption reducing to 1 free function. Specific profile e.g. $E(r)=E_0 r^2\exp(-r^2/L^2)$ is extra assumption.

### 4. Equation audit

**Spatial Buchert - Established result [Buchert 2000,2001]:**

For irrotational dust, expansion $\theta=\nabla_\mu u^\mu$, shear $\sigma^2=\frac12\sigma_{\mu\nu}\sigma^{\mu\nu}$.

In LTB: [Derivation completed]

$$H_\perp = \frac{\dot R}{R},\quad H_\parallel = \frac{\dot R'}{R'}$$
$$\theta = H_\parallel+2H_\perp,\quad \sigma^2=\frac13(H_\parallel-H_\perp)^2$$

$$H_{\cal D}= \frac13\langle\theta\rangle_{\cal D}$$
$$Q_{\cal D}= \frac23(\langle\theta^2\rangle-\langle\theta\rangle^2)-2\langle\sigma^2\rangle \tag{Buchert Q}$$
Signs verified: variance positive, shear subtracts. Dimension $time^{-2}$. Do NOT replace variance with $\langle\theta^2\rangle$.

Averaged equations:

$$3H_{\cal D}^2 = 8\pi G\langle\rho\rangle_{\cal D}+\Lambda-\frac12\langle{}^{(3)}R\rangle_{\cal D}-\frac12 Q_{\cal D} \tag{Ham}$$
$$\partial_t\langle\rho\rangle+3H_{\cal D}\langle\rho\rangle=0$$
$$\dot Q_{\cal D}+6H_{\cal D}Q_{\cal D}+\dot{\langle R\rangle}+2H_{\cal D}\langle R\rangle=0 \tag{Integ}$$

 Integrability is Bianchi, not new physics. Does NOT fix $Q$.[Established]

**FLRW limit check:** $E=-k r^2/2$, $M=M_0 r^3$, $t_B=const$, $R=a(t)r$. Then $H_\parallel=H_\perp=H$, $\theta=3H$, $\sigma=0$, $\langle\theta^2\rangle=\langle\theta\rangle^2$, $Q_{\cal D}=0$, $\langle R\rangle=6k/a^2$. Recovers Friedmann. Dimensions ok.

**Past-light-cone - Established [Ellis et al, Mustapha-Hellaby-Ellis]**

Radial null incoming to central observer:

$$\frac{dt}{dr}= -\frac{R'}{\sqrt{1+2E}} \tag{null}$$
$$\frac{d}{dr}\ln(1+z)= \frac{\dot R'}{\sqrt{1+2E}} \tag{redshift}$$ with $z(r_o)=0$.

$$D_A(z)=R(t(r),r)|_{null}$$[Established]

$D_A$ observable. $H_\parallel(z)= \dot R'/R'|_{null}$, $H_\perp(z)=\dot R/R|_{null}$. $H_\parallel$ probed by radial BAO, $H_\perp$ by transverse BAO, but reconstruction needs assumptions.

Redshift drift for central observer [Derivation completed, Yoo et al]:

$$\dot z \equiv \frac{dz}{dt_0}= (1+z)H_0 - H_\parallel(z)(1+z) \times {\rm correction\ from\ } \dot R' \text{ lapse} \approx (1+z)H_0 - H_\parallel(z) \text{ to leading order for } t_B=const$$

Exact form needs $\partial_t$ of null integral, not just $H_\parallel$. So drift $\neq$ shear.

Do NOT substitute $a_{\cal D}$ into FLRW $D_A=\frac{1}{1+z}\int dz/H$. Invalid in LTB without proof. [Constitution warning]

### 5. Bridge result

**Which functions enter where?**

* Spatial: integrals over $r\in[0,r_D]$ at $t_0$ of $R,R',\dot R,\dot R',E$.
* Null: $R,R',E,\dot R'$ evaluated along curve $t(r)$ solving (null).

Both from same $M,E,t_B$. So Outcome A trivially holds: computed quantities are consistent because same metric.

**Exact relations:** No closed relation eliminating $M,E,t_B$ exists without extra data.

Attempt elimination: $D_A(z)=R$ gives $R$ on cone. $z(r)$ gives $\int \dot R'/\sqrt{1+2E}$. This is 2 equations for 3 unknown functions $M,E,t_B$ along cone. Off-cone values needed for $Q_{\cal D}$ which is integral at $t_0$, not on cone. So $Q_{\cal D}$ depends on $R(t_0,r)$ for $r\le r_D$, while null gives $R(t(r),r)$ with $t(r)<t_0$ for $r>0$. Without evolving backwards using EoM and assuming $t_B$, you cannot get $t_0$ values from null values alone.

**Strongest partial result, conditional:**

Assume $t_B=const$ [Conditional, reduces free functions to 1]. Fix gauge $M=M_0 r^3$. Then $E(r)$ alone determines all. $D_A(z)$ determines $E(r)$ via inversion [Mustapha-Hellaby-Ellis, Established that LTB can reproduce any $D_A(z)$]. Then:

$$Q_{\cal D}[E(r)] = \frac23(\langle\theta^2\rangle_{t_0}-\langle\theta\rangle_{t_0}^2)-2\langle\sigma^2\rangle_{t_0}$$

is now functional $Q_{\cal D}= {\cal F}[D_A(z), r_D]$ with $r_D$ corresponding to $z_D$ via null map. This is predictive: fit $D_A(z)$ (e.g. mimic $\Lambda$CDM), compute $Q_{\cal D}$, then predict $H_\parallel(z)$ and drift $\dot z(z)$ which are NOT used in fit. If measured $H_\parallel$ differs, model class $t_B=const$ LTB falsified.

Without $t_B=const$, $Q_{\cal D}$ remains 2-function freedom, can tune to fit both $D_A$ and $H_\parallel$ arbitrarily [Unsupported claim if you claim otherwise]. So no new relation specifically constraining $Q_{\cal D}$ alone emerges without that extra Constitution.

Thus Outcome C not achieved in full generality; Outcome B achieved conditionally.

### 6. Degrees-of-freedom audit

* Physical free functions after gauge: 2 [E and M, or E and t_B].
* After imposing $t_B=const$: 1.[E]
* Observables: $D_A(z)$ 1 function, $H_\parallel(z)$ 1 function, $H_\perp(z)$ not independent ($H_\perp$ related to $D_A$ derivative), $\dot z(z)$ derived from $H_\parallel$ and $H_0$, lensing shear from $\int\sigma$.
* Degeneracy: $D_A$ and $H_\parallel$ are not statistically independent in LTB, both from same $E$, but with 2 free functions you can fit both arbitrarily. Counting observables > parameters insufficient.[Shield]
* Priors: simultaneous bang is extra assumption, not consequence of Buchert. Scaling ansatz $Q\propto a^n$ is extra assumption.
* Identifiability: With $t_B=const$, model overdetermined by $D_A+H_\parallel$, so testable. Without it, underdetermined, can fit any $D_A,H_\parallel$ pair, not testable as $Q_{\cal D}$ constraint.

### 7. Adversarial claim table

| Claim | Verdict | Reason |
|---|---|---|
| Drift-shear -> full $Q_{\cal D}$ | **Falsified** | Drift gives $H_\parallel$, shear term is $2\langle\sigma^2\rangle$ part of $Q$. $Q$ also needs variance $\langle\theta^2\rangle-\langle\theta\rangle^2$. Drift does NOT give variance. |
| Commutation rule = boundary-flux law | **Partial, conditional** | $\partial_t\langle f\rangle-\langle\dot f\rangle=\langle f\theta\rangle-\langle f\rangle\langle\theta\rangle$. For spherical domain can be written as surface term $\propto\int_{\partial{\cal D}}f v\cdot n$, but this is spatial boundary at fixed $t$, not null flux. Not equivalent to slice-to-null matching. |
| Stokes -> exact slice-to-null matching | **Falsified** | Stokes relates integrals over same dimension boundaries. Spacelike ${\cal D}$ and null cone have different causal character, no exact identity without extra foliation choice. Requires off-cone data. |
| $C_{CBL}\propto Q_{\cal D}$ | **Falsified** | CBL $C(z)=1+H^2(DD''-D'^2)+HH'DD'$. For FLRW $C=0$. For LTB $C\neq0$ depends on $E',M'$ but not proportional to volume-averaged $Q_{\cal D}$ which depends on domain $r_D$. Dimensions match but functional dependence different. Approximation $C\sim Q/H^2$ only under small $L$ and specific profile. |
| Nonzero CBL uniquely identifies backreaction as cause of acceleration | **Falsified** | Nonzero CBL identifies departure from FLRW geometry, could be void, not backreaction causing acceleration. Backreaction is spatial averaging effect, CBL is light-cone effect. No theorem linking. |
| More observables than parameters => predictive | **Falsified** | Need independence and non-degeneracy. In LTB 2 free functions can fit $D_A$ and $H_\parallel$ arbitrarily [Mustapha et al]. Counting fails if observables degenerate or free functions infinite-dimensional. |
[Grammar][Derivation][Conjecture][Shield]

### 8. Controls and falsifier

**FLRW limit:** Above, $Q\to0$, $\langle R\rangle\to6k/a^2$, $H_{\cal D}\to H$, $D_A\to a r/(1+z)$, $C\to0$. Pass.

**Dimensional/sign:** $Q\sim H^2$, $\sigma^2\ge0$ subtracts, variance $\ge0$. $Q$ can be positive or negative. In LTB central void $H_\parallel>H_\perp$ -> variance dominates -> $Q>0$ possible. Sign check ok.

**Domain dependence:** $Q_{\cal D}$ depends strongly on $r_D$. Choose $r_D\to0$, $Q\to0$ (local FLRW). Choose $r_D$ encompassing void+wall, $Q\neq0$. Null observable at $z_D$ corresponds to $r(z_D)$, not same as $r_D$ unless $t_0$ chosen. Relation prescription-dependent. Must state domain.

**Independent prediction:** Conditional $t_B=const$ LTB fit to $D_A(z)$ mimicking $\Lambda$CDM predicts $H_\parallel(z)$ and $\dot z(z)$. $H_\parallel$ from radial BAO and drift from ELT are not used in fit, so testable.

**Falsifier:** Measure $D_A(z)$ from SNe, fit LTB with $t_B=const$ to reproduce it. Predict $H_\parallel(z)$. If radial BAO $H_\parallel^{obs}(z)$ disagrees beyond errors, or drift $\dot z^{obs}$ disagrees, class $t_B=const$ LTB ruled out. If $C(z)\neq0$ but $Q_{\cal D}$ computed from same LTB with same domain is $\approx0$, claimed proportionality $C\propto Q$ falsified.

### 9. Literature

* Buchert 2000 Gen Rel Grav 32:105, 2001: spatial averaging, Ham and integrability - Established, gives (Ham)(Integ), does NOT give light-cone.
* Buchert et al 2020 Class Quant Grav 37: - light-cone averaging with optical backreaction, identifies closure - Established that framework exists, does NOT close without assumptions.
* Lemaitre 1933, Tolman 1934, Bondi 1947 - LTB solution - Established.
* Mustapha, Hellaby, Ellis 1997 - LTB can reproduce any $D_A(z)$ - Established, shows D_A alone not restrictive.
* Clarkson, Bassett, Lu 2008 PRL - FLRW consistency $C(z)$, $\Omega_k(z)$ - Established as FLRW test, does NOT measure $Q$.
* Heinesen & Clifton 2026 Phys Rev D [cited in prompt] - new null test for non-FLRW observational relations - Established as active line, not yet spatial-null bridge.
* Yoo et al, Quartin & Amendola - LTB drift formulas - Established that drift depends on $H_\parallel$.

What each actually establishes is separated from our derivations above.

### 10. Research recommendation

**Single most valuable next calculation:** For fixed $t_B=const$ LTB with realistic void profile from N-body (e.g. $E(r)$ from $f_v=0.7$), numerically compute $Q_{\cal D}(r_D)$ at $t_0$ and $C(z)$ along central past cone, and plot $C(z)$ vs $Q_{\cal D}/H_{\cal D}^2$ as function of domain $r_D$ and $z$. This isolates obstruction: shows explicitly that $C(z)$ is light-cone curvature function, $Q_{\cal D}$ is volume variance, and their relation is domain-dependent and not proportional without extra profile assumptions. It directly tests claims 4-5 and provides falsifiable numbers for ELT drift and DESI $H_\parallel$.

**Why:** It uses same metric for both sets, respects reality check [no generation of $\Lambda$], quantifies domain dependence, and gives independent prediction $\dot z(z)$ not used in fit.

| Claim | Status | Evidence or missing step |
|---|---|---|
| Spatial Buchert equations | **Established** | Buchert 2000; derived with correct signs |
| Light-cone propagation equations | **Established** | null + redshift eqs, $D_A=R$ |
| LTB spatial-to-null relation | **Partial, conditional** | Only with $t_B=const$ + fixed domain, otherwise underdetermined |
| Relation specifically constraining $Q_{\cal D}$ | **Not derived** in general; conditional functional $Q_{\cal D}={\cal F}[D_A]$ under $t_B=const$ |
| Independent predictive content | **Conditional** | $H_\parallel(z)$, $\dot z(z)$ predicted after fitting $D_A$ if $t_B=const$ |
| Observational falsifier | **Derived** | $H_\parallel^{obs}$ vs $H_\parallel^{LTB}(D_A)$ mismatch, $C(z)$ vs $Q_{\cal D}$ proportionality failure |## meta


