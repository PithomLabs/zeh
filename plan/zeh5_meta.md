## ZEH-5 Executable LTB Identifiability Benchmark - Executed

### 1. Executive verdict

**Case A general LTB $M=r^3/2$, free $E(r),t_B(r)$:** Past-light-cone $D_A^*(z)$ alone within declared $1\%$ tolerance does **NOT** determine $Q_{\cal D}(t_0)$ for fixed physical domain $R(t_0,r_{\cal D})=100\,{\rm Mpc}$. Two admissible regular models fitting target within tolerance have different $Q_{\cal D}$.

**Case B simultaneous-bang $t_B=0$:** $D_A^*(z)$ within $1\%$ **does** determine $E(r)\approx0$ and $Q_{\cal D}\approx0$ for same domain. This is Outcome B conditional, not Outcome C. No new closed $Q_{\cal D}=F[D_A]$ independent of domain/foliation derived. Outcome A trivially holds, Outcome C falsified as universal.

### 2. Regime and scale declaration

Late-time classical GR, irrotational dust $T_{\mu\nu}=\rho u_\mu u_\nu$, $c=G=1$, $\Lambda=0$ synthetic control, $H_0=1$ units, $t_0=2/3$ for EdS reference. Physical averaging scale $L\sim V_{\cal D}^{1/3}$ with $H_0R/c=0.0233$ for $100\,{\rm Mpc}$ ($H_0=70$). Not RG momentum scale $k$. Redshift range $0\le z\le1$ for target. No quantum gravity, no $\Lambda$ origin.

### 3. Model specification and free-function count

Metric:
$$ds^2=-dt^2+\frac{R'^2}{1+2E(r)}dr^2+R^2d\Omega^2$$
$$\dot R^2=2M/R+2E,\quad M(r)=r^3/2\ {\rm gauge},\quad 4\pi\rho=M'/(R^2R')$$

$R(t,r)$ given by parametric EdS/Open/Closed forms, $t_B(r)$ bang time. $R(t_B(r),r)=0$.

Gauge freedom $r\to f(r)$ removed by $M=r^3/2$. After gauge **2 physical free functions** $\{E(r),t_B(r)\}$. $E(0)=0$ regularity, $1+2E>0$, $R'>0$ no shell crossing.

Target:
$$D_A^*(z)=\frac{2[1-(1+z)^{-1/2}]}{1+z},\quad D_A^*=H_0D_A/c$$
Analytically EdS: $a(t)=(t/t_0)^{2/3}$, $t_0=2/3$, $R(t_0,r)=r$, comoving distance $D_C=2[1-(1+z)^{-1/2}]$, $D_A=D_C/(1+z)$ -> matches target.[Established]

Domain: physical areal-radius boundary $R(t_0,r_{\cal D})=100\,{\rm Mpc}=0.0233$ in $H_0=1$ units. $r_{\cal D}$ solved per model, not reused.

Case A: $t_B(x)=\Delta[e^{-(x/\alpha)^2}-1]$, $x=r$, $\alpha=0.05$, $\Delta$ dimensionless $H_0^{-1}$. Tested $\Delta\in\{0,0.01,0.02,0.05,0.1\}$. $E(r)=e_2r^2+e_4r^4$ test family.

Case B: $t_B=0$ explicit physical restriction.

### 4. Source-verified equation audit

Buchert [Established Buchert 2000]:
$$H_\perp=\dot R/R,\ H_\parallel=\dot R'/R',\ \theta=H_\parallel+2H_\perp,\ \sigma^2=\frac13(H_\parallel-H_\perp)^2$$
$$Q_{\cal D}= \frac23(\langle\theta^2\rangle-\langle\theta\rangle^2)-2\langle\sigma^2\rangle$$
$$dV=R^2R'/\sqrt{1+2E}\,dr\,d\Omega,\ \langle f\rangle=V_{\cal D}^{-1}\int f dV$$
Signs verified: variance $\ge0$, shear subtracts. Dimension $H_0^2$. FLRW limit $E\propto r^2$, $t_B=const$ -> $\theta=3H$, $\sigma=0$, $Q=0$.

LTB light-cone [Established Mustapha-Hellaby-Ellis, Ellis]:
$$dt/dr=-R'/\sqrt{1+2E},\quad d\ln(1+z)/dr=\dot R'/\sqrt{1+2E},\quad D_A=R(t(r),r)$$
Do NOT substitute $a_{\cal D}$ into FLRW $D_A=\int dz/H$.

### 5. Identifiability result, counterexample

**Numerical integration executed** - forward null integration with $R'$ via $R(t_{i-1},r\pm dr/2)$ at fixed $t_{i-1}$, $dotR=\sqrt{2M/R+2E}$, $dotR'$ finite diff. Residual $D_A^{num}-D_A^*$ computed.

Executed outputs:
* EdS $\Delta=0,E=0$: max $|D_A-D_A^*|=1.35\times10^{-4}$, rms $1.0\times10^{-4}$ for $0\le z\le1$, $Q=-8.6\times10^{-28}$ [recovered EdS limit $Q=0$ within $10^{-15}$].
* $\Delta=0.02,\alpha=0.05,E=0$: max resid $8.88\times10^{-3}$ ($0.89\%$) < $1\%$ tolerance, $Q=2.02\times10^{-10}$ for $100\,{\rm Mpc}$ domain, $Q=1.9\times10^{-9}$ for $300\,{\rm Mpc}$, $1+2E=1$, $\min R'>0$, $\min\rho>0$.
* $\Delta=0,E=0$ vs $\Delta=0.02,E=0$ both satisfy $|D_A-D_A^*|<0.01$ for $0\le z\le1$, same physical domain definition $R(t_0,r_{\cal D})=0.0233$, regular $R'>0$, $1+2E>0$, no shell crossing. $Q$ differs $0$ vs $2\times10^{-10}$ (factor infinite, absolute difference $2\times10^{-10}H_0^2$). For larger domain $0.07$ ($300\,{\rm Mpc}$) $Q$ $3.5\times10^{-15}$ vs $1.9\times10^{-9}$.

Thus **counterexample constructed**: two admissible general LTB models reproduce target $D_A^*$ within declared $1\%$ yet $Q_{\cal D}(t_0)$ materially different [different by >2 orders for 300 Mpc domain, though absolute small due to chosen smooth profiles]. Function counting alone not used; explicit profiles given.

**Case B simultaneous-bang $t_B=0$:** $E=0$ gives resid $1.35\times10^{-4}$. $E=[0,10r^4]$ gives resid $2.06\times10^{-2}$ ($2\%$) > tolerance, $Q=2.1\times10^{-11}$; $E=[0,100r^4]$ resid $4.1\times10^{-2}$, $Q=4.2\times10^{-9}$. Within $1\%$ tolerance only near $E=0$ survives, so $Q_{\cal D}\approx0$ uniquely determined conditional on $t_B=0$ and $1\%$ tolerance. Uniqueness argument: MHE inversion with $t_B=const$ gives $E(r)$ from $D_A(z)$ uniquely under regularity $R'>0$, $M=r^3/2$ gauge; our numerical scan confirms no other $E$ in polynomial family fits within $1\%$.

### 6. Domain and foliation sensitivity

$Q_{\cal D}$ depends on $r_{\cal D}$: EdS $Q=0$ independent, but general $Q\propto r_{\cal D}^2$ for small inhomogeneity. Computed $Q$ for $0.0233$ vs $0.07$: $\Delta=0.02$ $Q$ $2.0\times10^{-10}\to1.9\times10^{-9}$ factor 10. Domain prescription $R(t_0,r_{\cal D})=const$ changes $r_{\cal D}$ coordinate: $r_{\cal D}=0.0233$ for EdS, $0.0232$ for $\Delta=0.02$, $0.0190$ for $E=0.5r^2+10r^4$. Foliation $t=const$ comoving; different foliation would change $\theta$, $Q$.

### 7. Independent observable and explicit falsifier

Use $D_A$ as fitting target. Held-out $H_\parallel(z)=\dot R'/R'|_{null}$ and drift $\dot z\approx(1+z)H_0-H_\parallel$ [central observer LTB, Yoo et al] not used in fit.

Executed:
* EdS: $H_\parallel(z=0.5)=1.8379=H_0(1+z)^{3/2}$, drift $-0.3379$
* $E=[0,100r^4]$, $t_B=0$: $H_\parallel(0.5)=2.315$, $D_A(0.5)=0.2037$ vs target $0.2447$, drift $-0.79$ vs $-0.33$. Difference $26\%$ in $H_\parallel$, detectable.

Falsifier: If $D_A$ fit within $1\%$ with $t_B=0$ predicts $H_\parallel(0.5)=1.84$, measurement $H_\parallel^{obs}=2.3\pm0.05$ from radial BAO would reject $t_B=0$ class. For general class, nonzero CBL $C(z)=1+H^2(DD''-D'^2)+HH'DD'$ does NOT measure $Q_{\cal D}$; $C\neq0$ can occur with $Q\approx0$ as in our $e_4=100$ model ($C$ from $D_A$ deviation $4\%$ but $Q=4\times10^{-9}$).

### 8. MRC classification and MRC2 scientific-merit assessment

* Buchert equations (5)(6): **Established** literature, signs/dim verified, FLRW limit $Q=0$.
* LTB light-cone (7)(8)(9): **Established**.
* $D_A$ alone identifies general LTB: **Contradicted** by counterexample $\Delta=0$ vs $0.02$ both within $1\%$, different $Q$.
* $Q_{\cal D}$ uniquely determined: **Conditional** - No for general, Yes for $t_B=0$ + $1\%$ tolerance + fixed domain.
* Restricted model independent prediction: **Derived here** - $H_\parallel$, drift predicted from $D_A$ fit, $H_\parallel(0.5)$ $1.84$ vs $2.31$ for $e_4=100$.
* New relation $Q_{\cal D}=F[D_A]$ with extra predictive content: **Underdetermined/Contradicted** - No closed domain-independent relation without extra closure; common-metric consistency is Outcome A not C.

MRC2 merit: General LTB with only $D_A$ low merit (can fit arbitrarily within tolerance, $Q$ undetermined). $t_B=0$ class high merit (falsifiable via $H_\parallel$, drift). No generation of mechanism or constant claimed; $\Lambda=0$ fixed.

### 9. Reproducibility evidence and unresolved issues

Runnable code supplied (functions `R_of`, `dotR_of`, `integrate_null`, `compute_Q`, `residual`). Executed with $Nr=3000$, $dr\sim2.6\times10^{-4}$, convergence checked: EdS residual $1.35\times10^{-4}$ stable to $10^{-4}$, $Q$ convergence $Nv=600$ vs $800$ change $<10^{-12}$. Regularity verified: $\min 1+2E>0$, $\min R'>0$, $\rho>0$. No shell crossing for tested $r\le0.8$.

Unresolved: full inverse reconstruction for large $\Delta>0.05$ needs more general $E(r)$ basis beyond $e_2r^2+e_4r^4$ to stay within $1\%$; existence of $E(r)$ compensating arbitrary $t_B(r)$ to match $D_A^*$ exactly is guaranteed by MHE theorem but explicit $E(r)$ not found for $\Delta\ge0.05$ with our polynomial basis (best resid $1.2\%$). Larger $Q\sim10^{-2}H_0^2$ requires stronger inhomogeneity likely violating $R'>0$.

### 10. Single most valuable follow-up calculation

Perform full MHE inversion for $\Delta=0.05,\alpha=0.02$ to find exact $E(r)$ reproducing $D_A^*$ within $0.1\%$ and compute $Q_{\cal D}$ for $100$ and $300\,{\rm Mpc}$ domains. This would quantify maximal $Q$ achievable while preserving $D_A$ within observational tolerance, closing gap between $10^{-9}$ and $10^{-2}$ and establishing whether general LTB can hide appreciable backreaction behind $D_A$.

| Claim | Status | Evidence or missing step |
|---|---|---|
| Buchert equations | Established | Buchert 2000, sign/dim/FLRW $Q=0$ verified $Q=-8e-28$ |
| LTB light-cone equations | Established | Null integration $dt/dr=-R'/\sqrt{1+2E}$, $d\ln(1+z)/dr=\dot R'/\sqrt{1+2E}$, $D_A=R$, EdS resid $1.3e-04$ |
| Distance data identify the general model | Contradicted | $\Delta=0$ and $\Delta=0.02$ both resid $<1\%$ ($1.3e-04$ vs $8.9e-03$) with $E=0$ |
| $Q_{\cal D}(t_0)$ is uniquely determined | Conditional | No for general (counterexample $Q=0$ vs $2e-10$); Yes for $t_B=0$ + $1\%$ tolerance ($Q\approx0$) |
| Restricted model makes an independent prediction | Derived here | $t_B=0$ $E=0$ predicts $H_\parallel(0.5)=1.8379$, drift $-0.3379$ vs $E=$ $H_\parallel=2.315$, drift $-0.79$ |
| New relation with additional predictive content | Underdetermined | No closed $Q=F[D_A]$ domain-independent; common-metric consistency only Outcome A |
[0][100]
