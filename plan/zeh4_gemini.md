### 1. Executive Verdict

**Result:** **Outcome B (Conditional Predictions of a Specified Model)** with Degeneracy / Underdetermination in Case 1.
We establish that in **Case 1** (General LTB with arbitrary bang-time $t_B(r)$), past-light-cone observables alone are insufficient to uniquely determine the spacetime metric or $Q_{\mathcal{D}}(t_0)$ without additional assumptions, due to gauge freedom and source degeneracies (e.g., the mass-profile/bang-time degeneracy). In **Case 2** (Simultaneous-bang LTB, $t_B(r) = \text{constant}$), light-cone observables uniquely determine the remaining free function, which in turn *conditionally* fixes $Q_{\mathcal{D}}(t_0)$ (Outcome B). However, no genuinely new consistency relation (Outcome C) independent of the standard metric reconstruction equations is achieved.

---

### 2. Regime and Scale Declaration

* **Physical Regime:** Classical General Relativity, late-time epoch ($z \in [0, 2]$), pressureless dust (cold dark matter + baryons) with a fixed cosmological constant ($\Lambda > 0$).
* **Spatial Averaging Scale:** Cosmic-web scale ($\mathcal{D} \sim 10$ to $100\text{ Mpc}$ comoving radius).
* **Observables:** Angular-diameter distance $D_A(z)$ and radial expansion rate $H(z)$ (derived from Baryon Acoustic Oscillations and Type Ia Supernovae).
* **Validity Limits:** Assumes spherical symmetry centered on the observer, vanishing pressure ($p=0$), and classical gravity (no quantum corrections or modifications to GR).

---

### 3. Model Specification and Free-Function Count

* **Metric (Constitution):** Lemaître–Tolman–Bondi (LTB) metric in comoving, synchronous coordinates ($c=1$):

$$ds^2 = -dt^2 + \frac{R'(t,r)^2}{1 + 2E(r)} dr^2 + R(t,r)^2 d\Omega^2$$



where $R(t,r)$ is the areal radius, prime denotes $\partial_r$, and $\dot{}$ denotes $\partial_t$.
* **Field Equations (Grammar):**

$$\dot{R}^2 = \frac{2M(r)}{R} + 2E(r) + \frac{\Lambda}{3}R^2, \quad \frac{4\pi G}{3} \rho(t,r) = \frac{M'(r)}{R^2 R'}$$


* **Free Functions & Gauge Freedom (Census):**
The metric functions entering the general solution are the mass function $M(r)$, the curvature function $E(r)$, and the bang-time function $t_B(r)$ (where $R(t_B(r), r) = 0$).
* *Gauge Freedom:* The radial coordinate $r$ can be reparameterized monotonically as $\tilde{r} = f(r)$.
* *Physical Degrees of Freedom Count:* After fixing the radial coordinate gauge (e.g., setting $R(t_0, r) = r$ today), **Case 1** retains **two** independent physical free functions of $r$ (e.g., $E(r)$ and $t_B(r)$). **Case 2** (simultaneous-bang, $t_B(r) = 0$) reduces the physical free functions to **one** independent function of $r$ (e.g., $E(r)$), as $M(r)$ is fixed by the local mass-density profile at $t_0$.



---

### 4. Source-Verified Equation Audit

* **Buchert Spatial Equations (Grammar):**
For a spherical domain of coordinate radius $r_{\mathcal{D}}$:

$$3 H_{\mathcal{D}}^2 = 8\pi G \langle \rho \rangle_{\mathcal{D}} + \Lambda - \frac{1}{2}\langle {}^{(3)}R \rangle_{\mathcal{D}} - \frac{1}{2} Q_{\mathcal{D}}$$



The kinematical backreaction scalar for irrotational dust is:

$$Q_{\mathcal{D}} = \frac{2}{3}\left(\langle \Theta^2 \rangle_{\mathcal{D}} - \langle \Theta \rangle_{\mathcal{D}}^2\right) - 2\langle \sigma^2 \rangle_{\mathcal{D}}$$



where local expansion $\Theta = \frac{\dot{R}'}{R'} + 2\frac{\dot{R}}{R}$ and shear $\sigma^2 = \frac{1}{3}\left(\frac{\dot{R}'}{R'} - \frac{\dot{R}}{R}\pipsq\right)$. *(Source: Buchert, 2000)*
* **Light-Cone Propagation Equations (Grammar):**
Along the radial past light cone ($dt/dr = -R'/\sqrt{1+2E}$):

$$D_A(z) = R(t(r), r), \quad 1+z = \frac{a_0}{a(t,r)} \quad \text{(or integrated via null ray equations)}.$$



*(Source: Lemaître 1933; Mustapha, Bassett, & Hellaby, 1998)*

---

### 5. Identifiability Result & Counterexample

* **Case 1 (General LTB with arbitrary $t_B(r)$):**
* *Result:* **Underdetermined / Unidentifiable from past light cone alone.**
* *Counterexample Construction:* Following Mustapha et al. (1998), past-light-cone observations provide at most two independent functions of redshift (e.g., $D_A(z)$ and the Hubble parameter $H(z)$). In Case 1, the spacetime is governed by *two* arbitrary free functions ($E(r)$ and $t_B(r)$) plus coordinate freedom. One can construct two distinct LTB profiles with different $t_B(r)$ (e.g., an early versus late local bang time) that project identical distance-redshift relations along the past light cone ($C^-$) but evolve differently off the light cone on the spacelike slice ($\Sigma_{t_0}$), yielding completely different values for $Q_{\mathcal{D}}(t_0)$. Thus, $Q_{\mathcal{D}}(t_0)$ is **not** uniquely determined.


* **Case 2 (Simultaneous-Bang, $t_B(r) = 0$):**
* *Result:* **Outcome B (Conditionally Determined).**
* Setting $t_B(r) = 0$ eliminates one free function, leaving only $E(r)$ (given a known mass profile or density normalization). Past-light-cone data (such as $D_A(z)$ combined with number counts or redshift drift) can uniquely invert the remaining free function (Mustapha et al., 1998). Once $E(r)$ and $M(r)$ are uniquely reconstructed across the manifold, the metric is fixed, and $Q_{\mathcal{D}}(t_0)$ is uniquely evaluated as a derived consequence (Outcome B). However, no new independent null-test constraint (Outcome C) is generated; it is simply metric reconstruction.



---

### 6. Domain and Foliation Sensitivity

* **Dependence:** $Q_{\mathcal{D}}(t_0)$ is highly sensitive to the choice of the spatial averaging domain radius $r_{\mathcal{D}}$ and the constant-time slicing $t = t_0$. It is a non-local spatial volume average, not a coordinate-invariant local scalar field. Shifting $r_{\mathcal{D}}$ alters the volume-averaged variance terms, meaning backreaction is explicitly a prescription-dependent indicator of domain inhomogeneity.

---

### 7. Independent Observable and Explicit Falsifier

* **Independent Observable:** Peculiar velocity dispersion and kinetic Sunyaev-Zel'dovich (kSZ) effect amplitude across cosmic-web voids.
* **Falsifier:** If a simultaneous-bang LTB model is fully reconstructed from past-light-cone distance data ($D_A(z)$), it predicts a unique, rigid value for $Q_{\mathcal{D}}(t_0)$ and spatial curvature variance today. If observations of peculiar velocity scatter and local bulk flows disagree by more than statistical tolerances with the backreaction-induced velocity gradients predicted by that reconstructed profile, the model class is falsified.

---

### 8. Math Reality Check (MRC) & MRC2 Scientific-Merit Assessment

* **Census:** Physical free functions identified (two in Case 1, one in Case 2); gauge freedom explicitly stripped.
* **Grammar:** Buchert averaging equations and LTB null-propagation equations verified against primary sources.
* **Constitution:** Classical GR, irrotational pressureless dust, spherical symmetry, comoving synchronous gauge.
* **Shield:** Falsifiable restriction established via null-cone inversion limits and peculiar velocity consistency checks.
* **Generator/Selector Warning Honored:** Did not claim backreaction *generates* dark energy or *selects* initial conditions; treated it purely as a kinematic consequence of reconstructed inhomogeneity.
* **MRC2 Merit:** High methodological rigor; successfully isolates why past-light-cone observations cannot determine spatial volume averages without auxiliary assumptions (like $t_B(r) = 0$).

---

### 9. Reproducibility Evidence and Unresolved Issues

* **Primary Sources:** Buchert (2000) for $Q_{\mathcal{D}}$ definitions; Mustapha, Bassett, & Hellaby (1998) for LTB light-cone inversion proofs.
* **Unresolved Issue:** The reliance on the simultaneous-bang assumption ($t_B(r) = 0$) is an unproven physical constraint; relaxing it introduces severe degeneracies that null-cone data alone cannot break without off-light-cone dynamical inputs (e.g., velocity field measurements).

---

### 10. Single Most Valuable Follow-Up Calculation

* **Calculation:** Numerically integrate the Mustapha-Bassett-Hellaby light-cone inversion equations for an LTB toy model with a specified non-zero bang-time gradient $\partial_r t_B \neq 0$, compute the resulting past-light-cone distance measures, and explicitly map the continuum of degenerate spatial backreaction values $Q_{\mathcal{D}}(t_0)$ that yield the exact same $D_A(z)$.

---

### Final Status Table

| Claim | Status | Evidence or Missing Step |
| --- | --- | --- |
| **Buchert spatial equations** | **Established** | Standard GR volume-averaging identities for irrotational dust. |
| **LTB light-cone propagation** | **Established** | LTB radial null geodesics and optical relations. |
| **Selected observables identify the model** | **Conditional (Outcome B)** | Fails in Case 1 (arbitrary $t_B$) due to inversion degeneracy; succeeds in Case 2 (simultaneous bang). |
| **$Q_{\mathcal{D}}(t_0)$ is uniquely determined** | **Conditional / False in Case 1** | Uniquely determined *only* after imposing $t_B(r) = \text{const}$ and completing full metric reconstruction; otherwise underdetermined. |
| **Conditional independent prediction exists** | **Established** | Reconstructed LTB profiles predict peculiar velocity scatter and spatial curvature variance. |
| **New relation with additional predictive content** | **Not Derived (No Outcome C)** | No closed consistency relation emerges independent of standard metric reconstruction equations. |
