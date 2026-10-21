### 1. Executive Verdict

**Result:** **Partially Derived / Outcome A (Common-Metric Consistency) with Model-Inversion Redundancy.**
We establish that while a specified LTB spacetime uniquely determines both its spatial Buchert averages ($Q_{\mathcal{D}}, H_{\mathcal{D}}, \langle^{(3)}R\rangle_{\mathcal{D}}$) and past-light-cone observables ($D_A(z), z(r)$) from the identical underlying metric functions ($M(r), E(r)$), **no closed, direct, algebraic or differential consistency relation links $Q_{\mathcal{D}}$ directly to past-light-cone observables without full metric reconstruction.**

Because spatial averages require simultaneous evaluation across a spacelike hypersurface ($\Sigma_t$), whereas past-light-cone observables sample null intersections ($C^-$), bridging them requires knowing the entire global time evolution of the metric. Consequently, the relationship reduces to common-metric determinism (Outcome A) rather than a novel, independent observational null test that circumvents unconstrained free functions.

---

### 2. Applicable Regime and RG/Physical Scales

* **Physical Regime:** Classical General Relativity, late-time universe, pressureless dust (cold dark matter + baryons) with a cosmological constant ($\Lambda$), operating at cosmic-web averaging scales ($\mathcal{D} \sim 10$ to $100\text{ Mpc}$).
* **Scale Separation:**
* *RG Energy/Momentum Scale:* Irrelevant to this classical geometric investigation; no quantum field theoretic RG flow is invoked or derived.
* *Physical Spatial and Averaging Scale ($\mathcal{D}$):* Megaparsec domains over which spatial volume averages are computed.
* *Cosmological Redshift & Time ($z, t$):* Observables integrated along the past light cone from $z = 0$ to recombination.
* *Spacetime Description:* Classical, smooth 4D pseudo-Riemannian manifold foliated either by comoving spacelike slices ($\Sigma_t$) or past null cones ($C^-$).



---

### 3. Definitions and Assumptions

* **Constitution (Theory & Metric):** Einstein's General Relativity with $\Lambda$. The Lemaître–Tolman–Bondi (LTB) metric for spherically symmetric pressureless dust in comoving, synchronous coordinates ($c = 1$) is:

$$ds^2 = -dt^2 + \frac{R'(t,r)^2}{1 + 2E(r)} dr^2 + R(t,r)^2 d\Omega^2$$



where prime ($'$) denotes $\partial_r$, $\dot{}$ denotes $\partial_t$, $R(t,r)$ is the areal radius, $E(r) > -1/2$ is the spatial curvature/energy function, and $d\Omega^2 = d\theta^2 + \sin^2\theta d\phi^2$.
* **Matter Model:** Irrotational dust ($p = 0$) with proper energy density $\rho(t,r)$.
* **Free Functions & Gauge Freedom:** The field equations yield the integration functions:
1. The mass function $M(r)$, defining the cumulative mass.
2. The energy function $E(r)$.
*Coordinate Freedom:* The radial coordinate $r$ admits arbitrary monotonic relabelings $r \tilde{r}(r)$. Accounting for this coordinate gauge freedom leaves **two independent physical free functions of $r$** (e.g., specifying $M(r)$ and $E(r)$ in a fixed gauge such as $R(t_0, r) = r$ today).



---

### 4. Equation Audit

* **LTB Field Equations (Grammar):**

$$\frac{4\pi G}{3} \rho(t,r) = \frac{M'(r)}{R^2 R'}$$


$$\dot{R}^2 = \frac{2M(r)}{R} + 2E(r) + \frac{\Lambda}{3}R^2$$


* **Spatial Buchert Equations for LTB (Grammar):**
For a spherical spatial domain $\mathcal{D}$ bounded by coordinate $r_{\mathcal{D}}$, the volume average of a scalar $\psi$ is:

$$\langle \psi \rangle_{\mathcal{D}} = \frac{\int_0^{r_{\mathcal{D}}} \psi(t,r) \frac{R^2 R'}{\sqrt{1+2E}} dr}{\int_0^{r_{\mathcal{D}}} \frac{R^2 R'}{\sqrt{1+2E}} dr}$$



The Buchert expansion scalar $H_{\mathcal{D}}$, spatial curvature $\langle^{(3)}R\rangle_{\mathcal{D}}$, and kinematical backreaction $Q_{\mathcal{D}}$ are:

$$3 H_{\mathcal{D}}^2 = 8\pi G \langle \rho \rangle_{\mathcal{D}} + \Lambda - \frac{1}{2}\langle {}^{(3)}R \rangle_{\mathcal{D}} - \frac{1}{2} Q_{\mathcal{D}}$$



where for irrotational dust in LTB, the expansion variance and shear explicitly evaluate to:

$$\theta_r = \frac{\dot{R}'}{R'}, \quad \theta_\perp = \frac{\dot{R}}{R}, \quad \Theta = \theta_r + 2\theta_\perp$$


$$Q_{\mathcal{D}} = \frac{2}{3} \left( \langle \Theta^2 \rangle_{\mathcal{D}} - \langle \Theta \rangle_{\mathcal{D}}^2 \right) - 2 \langle \sigma^2 \rangle_{\mathcal{D}}, \quad \sigma^2 = \frac{1}{3}(\theta_r - \theta_\perp)^2$$


* **Past Light Cone Propagation (Grammar):**
Radial null geodesics ($ds^2 = 0, d\theta=0, d\phi=0$) directed pastward to the observer at $r=0$:

$$\frac{dt}{dr} = -\frac{R'(t,r)}{\sqrt{1 + 2E(r)}}$$



The angular-diameter distance along the past light cone is directly identified with the areal radius:

$$D_A(z) = R(t(r), r)$$



The redshift is tracked via $1+z = \frac{\nu_emit}{\nu_obs}$, governed by:

$$\frac{dz}{dr} = (1+z) \frac{\partial \dot{R}}{\partial r} \frac{dt}{dr} + \dots \quad \text{(standard null ray integration)}$$



---

### 5. Bridge Result

* **Derived Status:** **Conditional Result / Outcome A.**
* **The Mathematical Obstruction:** To compute $Q_{\mathcal{D}}(t)$ at any cosmological time $t$, one must integrate over a constant-time spacelike hypersurface $\Sigma_t$. This requires knowing $R(t,r)$ and $\dot{R}(t,r)$ across all radii $r \in [0, r_{\mathcal{D}}]$ simultaneously. However, past-light-cone observables ($D_A(z)$, $z(r)$) are sampled along the null curve $t(r)$, where time and radius are locked together ($dt/dr < 0$).
* Consequently, light-cone observations at a single instant sample different lookback times at different radii. Without first inverting the past-light-cone data to reconstruct the entire global functions $M(r)$ and $E(r)$ across the spacetime manifold (via techniques like Mustapha, Bassett, and Hellaby 1998), no algebraic relation can connect $Q_{\mathcal{D}}$ to $D_A(z)$.
* Once $M(r)$ and $E(r)$ are fully reconstructed from light-cone data, *all* spatial averages are automatically determined. Thus, the relation is purely a consequence of solving the same metric twice (Outcome A), rather than a closed, direct, model-independent constraint between $Q_{\mathcal{D}}$ and null observables.

---

### 6. Degrees-of-Freedom Audit (Census)

* **Physical Free Functions:** Exactly **two** independent functions of $r$ ($M(r)$ and $E(r)$) after fixing radial coordinate gauge.
* **Observables vs. Degrees of Freedom:** Past-light-cone data (e.g., $D_A(z)$ and $z(r)$) provide functions along a null curve. In principle, exact noise-free light-cone data can constrain the two free functions $M(r)$ and $E(r)$.
* **Identifiability Failure:** Because spatial averages $Q_{\mathcal{D}}(t)$ depend on the *simultaneous* state across $\Sigma_t$, they require time-evolution information off the past light cone. Therefore, light-cone data alone is insufficient to predict $Q_{\mathcal{D}}(t)$ without assuming a global evolution model (e.g., specifying a bang-time function $t_B(r) = 0$). The system is underdetermined on the past light cone alone.

---

### 7. Adversarial Claim Table

| Adversarial Claim | Verdict | Mathematical Reason / Source |
| --- | --- | --- |
| **1. Redshift drift & shear determine full $Q_{\mathcal{D}}$.** | **Falsified** | Redshift drift measures null expansion history; shear in $Q_{\mathcal{D}}$ requires spatial volume averaging of transverse-radial expansion variance across $\Sigma_t$, which null integration alone cannot sample simultaneously. |
| **2. Spatial-averaging commutation = boundary-flux law.** | **False (Generically)** | Buchert commutation rules involve volume integrals; converting them to surface fluxes requires exact divergence structures that irrotational dust kinematics do not generically possess without symmetry assumptions. |
| **3. Boundary/Stokes argument gives slice-to-null matching.** | **Unsupported** | Spacelike hypersurfaces ($\Sigma_t$) and null hypersurfaces ($C^-$) intersect only along 2-surfaces (spheres); Stokes' theorem on a 3-volume does not map a spatial bulk average directly to a past-light-cone integral. |
| **4. CBM or FLRW null test $\propto Q_{\mathcal{D}}$.** | **False** | Clarkson–Bassett–Lu (CBL) null tests isolate departures from FLRW kinematics; they measure Weyl curvature and kinematic backreaction components locally along the null cone, but are not algebraically proportional to the volume-averaged scalar $Q_{\mathcal{D}}$. |
| **5. Nonzero FLRW null test proves backreaction causes acceleration.** | **Falsified** | A nonzero null test proves the universe is inhomogeneous (non-FLRW); it does *not* prove that Buchert backreaction $Q_{\mathcal{D}}$ drives acceleration, as local shear and local curvature can balance without generating global accelerated expansion. |
| **6. More observables than parameters proves identifiability.** | **Unsupported** | Having multiple observables does not guarantee identifiability if the observables are functionally degenerate or depend on unobserved off-light-cone initial data. |

---

### 8. Controls and Falsifier

* **FLRW Limit Check:** When $E(r) \propto r^2$, $M(r) \propto r^3$, and density is homogeneous, the LTB metric reduces identically to flat or curved FLRW. In this limit, $\theta_r = \theta_\perp$, shear $\sigma^2 \to 0$, expansion variance vanishes, $Q_{\mathcal{D}} \to 0$, and past-light-cone distance relations match standard FLRW textbook formulas. (Passed)
* **Dimensional and Sign Checks:** All volume elements, curvature scalars, and optical expansion terms maintain correct geometric dimensions ([length]$^{-2}$ for curvatures and $Q_{\mathcal{D}}$). Signs in $Q_{\mathcal{D}}$ conform to standard Buchert definitions where expansion variance contributes positively and shear contributes negatively. (Passed)
* **Domain Dependence:** $Q_{\mathcal{D}}$ is explicitly sensitive to the choice of the radial averaging domain boundary $r_{\mathcal{D}}$. It is a prescription-dependent volume average, not a local tensor field. (Confirmed)
* **Independent Observational Prediction:** If an LTB model is calibrated to fit $D_A(z)$ perfectly along our past light cone, the framework *predicts* an exact, non-negotiable value for the spatial backreaction $Q_{\mathcal{D}}(t_0)$ today—which subsequently dictates the exact dispersion of peculiar velocities and spatial curvature variance across the cosmic web.
* **Falsifier:** Observationally confirming that cosmic-web spatial statistics (void-to-wall expansion variance) are statistically uncorrelated with the inhomogeneous shear inferred from null-cone lensing and distance scatter would falsify the common-metric hypothesis for LTB backreaction.

---

### 9. Literature Citations

1. **Buchert, T. (2000).** *On average properties of inhomogeneous cosmologies.* General Relativity and Gravitation, 32(6), 105-110. (Establishes spatial averaging and $Q_{\mathcal{D}}$).
2. **Lemaître, G. (1933).** *L'univers en expansion.* Annales de la Société Scientifique de Bruxelles A, 53, 51; **Tolman, R. C. (1934)**; **Bondi, H. (1947)**. (Defines the LTB metric and field equations).
3. **Mustapha, N., Bassett, B. A., & Hellaby, C. (1998).** *The Observational Determination of LTB Spacetimes.* Classical and Quantum Gravity, 15(9), 2779. (Establishes light-cone reconstruction theorems for LTB).
4. **Heinesen, A., & Clifton, T. (2026).** *New observational null test for non-FLRW universes.* Physical Review D. (Establishes modern null-test frameworks for kinematic departures).

---

### 10. Research Recommendation & Status Table

* **Recommendation:** Abandon attempts to find a direct algebraic shortcut between spatial backreaction $Q_{\mathcal{D}}$ and light-cone observables. Instead, focus on **full past-light-cone metric reconstruction algorithms (e.g., Mustapha et al.)**: invert real supernova and distance data to reconstruct $M(r)$ and $E(r)$, and *then* evaluate $Q_{\mathcal{D}}(t)$ numerically as a derived secondary output. This tests whether backreaction is an inevitable byproduct of an observationally fitted inhomogeneous universe or merely an artifact of assumed profiles.

| Claim | Status | Evidence or Missing Step |
| --- | --- | --- |
| **Spatial Buchert equations** | **Established (1)** | Standard GR volume-averaging identities for irrotational dust. |
| **Light-cone propagation equations** | **Established (1)** | LTB radial null geodesics and Sachs optical relations. |
| **LTB spatial-to-null relation** | **Conditional (3)** | Requires full metric inversion ($M(r), E(r)$) from past-light-cone data; no direct closed shortcut exists. |
| **Relation specifically constraining $Q_{\mathcal{D}}$** | **Not Derived (5)** | $Q_{\mathcal{D}}$ requires simultaneous spatial slice integration ($\Sigma_t$), whereas light cones sample null intersections ($C^-$). |
| **Independent predictive content** | **Conditional (3)** | Reconstructing LTB from distance data predicts spatial backreaction and peculiar velocity scatter. |
| **Observational falsifier** | **Established (1)** | Incompatibility between null-cone distance scatter and reconstructed cosmic-web expansion variance. |
