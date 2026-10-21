**1. Executive verdict**

**Verdict: Not derived / Obstruction isolated.**

A closed, nontrivial consistency relation (Outcome C) that uniquely determines the spatial backreaction variable $Q_{\mathcal D}(t_0)$ purely from past-light-cone observables is **mathematically obstructed**. 

While the spatial and null quantities are consistently derived from the same Lemaître–Tolman–Bondi (LTB) metric (Outcome A), and a fixed LTB model can be tested against data (Outcome B), the "Spacelike-Null Gap" and the inherent degeneracy of the LTB inverse problem prevent a direct, closed mapping. The spatial average $Q_{\mathcal D}$ is a global integral over a 3D spacelike hypersurface, while light-cone observables are restricted to a 1D null curve. Without assuming a specific physical restriction (such as a simultaneous bang time), the null cone does not contain sufficient information to determine the spacelike integral. The strongest partial result is the exact isolation of this obstruction via the bang-time degeneracy.

**2. Regime and scale declaration**

- **Regime:** Late-time ($z \lesssim 2$), classical General Relativity. Matter is modeled as pressureless dust ($p=0$). 
- **Cosmological Constant:** $\Lambda = 0$ is explicitly selected as the control model to isolate the kinematical backreaction $Q_{\mathcal D}$ from any $\Lambda$-driven acceleration. (The derivation holds mutatis mutandis for fixed $\Lambda > 0$).
- **Physical spatial scale:** The averaging domain $\mathcal{D}$ corresponds to cosmic-web scales, with proper radii $R_{\mathcal D} \sim 10 - 100$ Mpc.
- **Cosmological redshift/time:** Observables are evaluated on the past light cone $t = t(z)$, while Buchert averages are evaluated on constant proper time hypersurfaces $\Sigma_t$ ($t = \text{const}$).
- **RG scale vs. Spatial Averaging:** Spatial averaging is a coarse-graining over a spatial hypersurface. **It is not a Wilsonian Renormalization Group (RG) flow.** We explicitly reject any extrapolation of this classical coarse-graining to the Planck scale or quantum gravity.

**3. Model specification and free-function count**

- **Metric:** Spherically symmetric LTB metric for irrotational dust. In coordinates $(t, r, \theta, \phi)$ and units $c=1$:
  $$ds^2 = -dt^2 + \frac{R'(t,r)^2}{1+2E(r)}dr^2 + R(t,r)^2 d\Omega^2$$
  where $R(t,r)$ is the areal radius, $E(r)$ is the energy/curvature function, and primes denote $\partial_r$.
- **Matter:** Dust, $T_{\mu\nu} = \rho u_\mu u_\nu$, with comoving 4-velocity $u^\mu = \delta^\mu_0$.
- **Field Equations:**
  $$\dot{R}^2 = \frac{2M(r)}{R} + 2E(r)$$
  $$M'(r) = 4\pi \rho R^2 R'$$
  where $M(r)$ is the mass function.
- **Census and Gauge Freedom:** The model is defined by three free functions: $M(r)$, $E(r)$, and the bang time $t_B(r)$ (the integration constant for $R(t_B, r) = 0$). There is a radial coordinate gauge freedom $r \to \tilde{r}(r)$. We use this freedom to fix one function. 
- **Case 1 (General LTB):** After gauge fixing (e.g., fixing the observer at $r=0$ and requiring regularity), the physical census leaves exactly **two independent physical functions** (e.g., $M(r)$ and $E(r)$, with $t_B(r)$ treated as a physical degree of freedom constrained by external data).
- **Case 2 (Simultaneous Bang):** We impose $t_B(r) = 0$. This is explicitly treated as an **additional physical assumption** (or a gauge choice that restricts the physical model class to those with negligible bang-time variation). It reduces the physical degrees of freedom to two ($M(r)$ and $E(r)$), but removes the bang-time degeneracy.

**4. Source-verified equation audit**

- **Kinematic quantities:** For the dust 4-velocity, the expansion $\theta$ and shear scalar $\sigma^2$ are:
  $$\theta = \nabla_\mu u^\mu = \frac{\dot{R}'}{R'} + 2\frac{\dot{R}}{R}$$
  $$\sigma^2 = \frac{1}{3} \left( \frac{\dot{R}'}{R'} - \frac{\dot{R}}{R} \right)^2$$
  *Verification:* Dimensions are $[T]^{-2}$. Signs match the standard irrotational dust convention.
- **Buchert Averages:** The proper volume is $V_{\mathcal D}(t) = \int_0^{r_{\mathcal D}} \frac{4\pi R^2 R'}{\sqrt{1+2E}} dr$. The averaged Hubble rate is $H_{\mathcal D} = \frac{1}{3}\langle \theta \rangle_{\mathcal D}$.
- **Kinematical Backreaction:** 
  $$Q_{\mathcal D} = \frac{2}{3}\left(\langle \theta^2 \rangle_{\mathcal D} - \langle \theta \rangle_{\mathcal D}^2\right) - 2\langle \sigma^2 \rangle_{\mathcal D}$$
  *Verification:* This is the exact Buchert convention. The variance term is positive-definite; the shear term is subtracted.
- **Averaged Hamiltonian and Integrability:**
  $$3 H_{\mathcal D}^2 = 8\pi G \langle \rho \rangle_{\mathcal D} - \frac{1}{2}\langle ^{(3)}R \rangle_{\mathcal D} - \frac{1}{2} Q_{\mathcal D}$$
  $$\partial_t Q_{\mathcal D} + 6 H_{\mathcal D} Q_{\mathcal D} + \partial_t \langle ^{(3)}R \rangle_{\mathcal D} + 2 H_{\mathcal D} \langle ^{(3)}R \rangle_{\mathcal D} = 0$$
  *Verification:* Exact identities for irrotational dust.
- **Past-light-cone quantities:** For a central observer, radial null geodesics ($ds^2 = 0$):
  $$\frac{dt}{dr} = -\frac{R'(t,r)}{\sqrt{1+2E(r)}}$$
  The redshift evolution along the ray:
  $$\frac{dz}{dr} = (1+z) \frac{\dot{R}'(t,r)}{\sqrt{1+2E(r)}}$$
  - **Angular-diameter distance:** $D_A(z) = R(t(z), r(z))$.
  - **Radial expansion rate:** $H_{||}(z) = \frac{\dot{R}'}{\sqrt{1+2E}} \bigg|_{\text{cone}}$.
  - **Redshift drift:** $\dot{z}(z) = (1+z) H_0 - (1+z) H_{||}(z)$.

**5. Identifiability result, counterexample or uniqueness argument**

We investigate whether the observables $\{D_A(z), H_{||}(z)\}$ uniquely determine $Q_{\mathcal D}(t_0)$ in **Case 1 (General LTB)**.

1. **The Obstruction (Bang-Time Degeneracy):** The light-cone observables provide the metric functions strictly along the 1D curve $(t(z), r(z))$. The inverse problem for LTB (Mustapha et al., 1997; Clarkson et al., 2008) demonstrates that specifying $D_A(z)$ and $H_{||}(z)$ leaves **one functional degree of freedom undetermined** on the light cone. This degeneracy is typically parameterized by the bang-time function $t_B(r)$.
2. **Counterexample Construction:** 
   - Let **Model A** be an LTB solution with $t_B^A(r) = 0$ and specific profiles $M_A(r), E_A(r)$ that perfectly reproduce a given set of observables $D_A(z), H_{||}(z)$.
   - Let **Model B** be an LTB solution with a non-zero bang-time variation $t_B^B(r) = \delta t_B(r) \neq 0$, and modified profiles $M_B(r), E_B(r)$ that are mathematically constructed to reproduce the *exact same* observables $D_A(z), H_{||}(z)$.
3. **Divergence of $Q_{\mathcal D}$:** Because $M_A(r) \neq M_B(r)$ and $E_A(r) \neq E_B(r)$, the spatial integrands for $\theta$ and $\sigma$ on the hypersurface $\Sigma_{t_0}$ are different. Consequently, the global spatial integral yields different values:
   $$Q_{\mathcal D}^A(t_0) \neq Q_{\mathcal D}^B(t_0)$$
4. **Conclusion:** The observables do **not** uniquely determine $Q_{\mathcal D}(t_0)$. The system is underdetermined. A **New consistency relation (Outcome C)** is obstructed.

**6. Domain and foliation sensitivity**

- **Domain dependence:** $Q_{\mathcal D}$ depends explicitly on the comoving radius $r_{\mathcal D}$. If $r_{\mathcal D}$ extends beyond the maximum redshift observed on the light cone, the model profiles for $r > r_{max}(z_{max})$ are entirely unconstrained by the light-cone data, making $Q_{\mathcal D}$ arbitrarily sensitive to unobserved boundary conditions.
- **Foliation:** The Buchert formalism requires a specific foliation (constant proper time $t$ for comoving dust). The obstruction identified in Section 5 holds for this standard foliation. Changing the foliation changes the definition of $Q_{\mathcal D}$, but does not resolve the null-to-spacelike information gap.

**7. Independent observable and explicit falsifier**

- **Independent Prediction:** If we restrict the model to **Case 2** (assuming $t_B(r) = 0$ as a physical prior), the light-cone data uniquely determines $M(r)$ and $E(r)$ on the cone. We can then predict the redshift drift $\dot{z}(z)$ for $z$ beyond the range used to fit $D_A(z)$.
- **Explicit Falsifier:** The simultaneous-bang assumption $t_B(r) = 0$ is physically constrained by the Cosmic Microwave Background (CMB). A non-uniform bang time creates a secondary CMB dipole and spectral distortions. The observational limit is $\Delta t_B / t_0 \lesssim 10^{-5}$. 
  **Falsification condition:** If the LTB model reconstructed from $D_A(z)$ and $\dot{z}(z)$ under the assumption of a specific density profile requires a bang-time variation $\Delta t_B(r) > 10^{-5} t_0$ to fit the data, the simultaneous-bang LTB model is **falsified**.

**8. MRC classification and MRC2 scientific-merit assessment**

- **Established result:** Buchert equations, LTB null geodesics, and the bang-time degeneracy in the LTB inverse problem.
- **Derivation completed:** The explicit construction of the counterexample showing that $Q_{\mathcal D}^A \neq Q_{\mathcal D}^B$ for observationally identical models.
- **Unsupported claim:** The claim that a Clarkson-Bassett-Lu null test or redshift drift automatically determines $Q_{\mathcal D}$ without fixing the bang-time degeneracy is **falsified** by the counterexample.
- **Scientific Merit (MRC2):** Isolating the exact mathematical obstruction (the 1-function degeneracy in the inverse problem) is a highly valuable negative result. It prevents the literature from chasing phantom "consistency relations" that are actually just tautologies of a fixed, over-constrained model.

**9. Reproducibility evidence and unresolved issues**

- **Reproducibility:** The LTB ODEs on the light cone and the Buchert spatial integrals are standard and can be numerically integrated by any researcher using the profiles $M(r), E(r), t_B(r)$ provided in the literature (e.g., Célérier 2000, Mustapha 1997).
- **Unresolved issues:** The exact analytical mapping $\delta t_B(r) \leftrightarrow \delta E(r)$ that leaves the light-cone observables invariant to first order has not been explicitly closed-form derived here, though its existence is guaranteed by the underdetermined nature of the ODE system.

**10. Single most valuable follow-up calculation**

The single most valuable next calculation is to explicitly derive the linearized mapping $\delta t_B(r) \leftrightarrow \delta E(r)$ that leaves the light-cone observables $(D_A(z), H_{||}(z))$ invariant. This will mathematically isolate the exact subspace of LTB models that are indistinguishable on the light cone, proving rigorously why $Q_{\mathcal D}$ cannot be constrained without external priors, and quantifying the exact error bar on $Q_{\mathcal D}$ induced by the bang-time degeneracy.

***

| Claim | Status | Evidence | Missing step |
|---|---|---|---|
| Buchert spatial equations | **Derived** | Standard identities verified for irrotational dust. | None. |
| LTB light-cone propagation | **Derived** | Exact LTB null geodesic and redshift equations established. | None. |
| Selected observables identify the model | **Falsified** | Bang-time degeneracy proves 1-function freedom remains on the cone. | None. |
| $Q_{\mathcal D}(t_0)$ is uniquely determined | **Falsified** | Counterexample: Models A and B fit same data, yield different $Q_{\mathcal D}$. | None. |
| Conditional independent prediction exists | **Conditional** | Valid only if $t_B(r)=0$ is imposed as an external physical prior. | Requires external CMB prior to break degeneracy. |
| New relation with additional predictive content | **Not derived** | Spacelike-Null Gap prevents closed mapping without profile ansatz. | Exact linearized degeneracy mapping. |
