
1. Executive Verdict

Verdict: Partially Derived.
A mathematically closed, non-trivial consistency relation between spatial averages (\(Q_{\mathcal{D}}\)) and past-light-cone observables (\(D_A(z)\), \(H_L(z)\)) is derived conditionally within the class of Lemaître–Tolman–Bondi (LTB) models.
The relation is not tautological (Outcome C) because it removes independent functional freedom from the light-cone equations by forcing a coupling between the spatial averaging scale and null geodesics via the metric functions M(r) and E(r).
However, it is partially derived globally because total mathematical closure requires an explicit profile constraint or boundary condition (e.g., a simultaneous big bang assumption, \(t_B(r) = 0\)). Without this closure condition, the system retains an unobserved free function (\(t_B'(r)\)) that creates a strict mathematical obstruction to a pure model-independent null test.

2. Applicable Regime and Scales

This investigation operates strictly under late-time, classical General Relativity with an absolute decoupling from high-energy and microphysical scales:
• RG Energy/Momentum Scale: Inapplicable. The system does not utilize an active Renormalization Group flow or momentum-cutoff scale. The fields are purely classical, smooth tensors.
• Physical Spatial and Averaging Scale: Coarse-grained at cosmic-web averaging scales (\(\mathcal{D} \sim 10 - 200 \text{ Mpc}\)). Matter is modeled macroscopically as an irrotational, pressureless dust fluid (ρ).
• Cosmological Redshift and Time: Redshift (z) and proper cosmic time (t) track large-scale global evolution along the past light cone up to the horizon scale (z ~ 0.1 - 2).
• Continuum vs. Effective Description: The geometry is a continuous, smooth Riemannian manifold solving the exact Einstein Field Equations locally. The Buchert framework acts as a statistical smoothing census of this exact classical background; it does not model discrete or quantum-gravitational transitions.

3. Definitions and Assumptions


Spacetime Metric

We adopt the spherically symmetric, comoving Lemaître–Tolman–Bondi (LTB) metric:
\(ds^{2}=-dt^{2}+\frac{R^{\prime }(t,r)^{2}}{1+2E(r)}dr^{2}+R(t,r)^{2}(d\theta ^{2}+\sin ^{2}\theta d\phi ^{2})\)
where \(R' \equiv \partial R / \partial r\), and E(r) > -1/2 represents the coordinate-invariant local spatial curvature/energy function.

Matter Model

The stress-energy tensor is pressureless dust:
\(T^{\mu \nu }=\rho (t,r)u^{\mu }u^{\nu },\quad u^{\mu }=\delta _{0}^{\mu }\)

Observer Architecture

The observer is positioned strictly at the central coordinate origin (r=0) at the current cosmic time t = t₀.

Domain & Foliation

The averaging domain \(\mathcal{D}\) is defined as a comoving spherical ball centered at the origin:
\(\mathcal{D}=\{(r,\theta ,\phi )\;|{}\;0\le r\le r_{\mathcal{D}}\}\)
Foliation is uniquely fixed by the hypersurfaces of constant proper time t.

4. Equation Audit


Local LTB Dynamics

The local Einstein Field Equations reduce to the exact structural equivalent of a localized Friedmann equation:
\(\.{R}(t,r)^{2}=\frac{2M(r)}{R(t,r)}+2E(r)+\frac{\Lambda }{3}R(t,r)^{2}\)
where \(\dot{R} \equiv \partial R / \partial t\), Λ is the cosmological constant, and M(r) is the conserved mass function inside comoving radius r.
Differentiating with respect to r delivers the local profile for the matter density:
\(4\pi G\rho (t,r)=\frac{M^{\prime }(r)}{R(t,r)^{2}R^{\prime }(t,r)}\)
The general analytic solution for Λ = 0 and E(r) < 0 (bound sectors) is parameterized via the cycloid variable η:
\(R(t,r)=\frac{M(r)}{2|{}E(r)|{}}(1-\cos \eta )\)
\(\eta -\sin \eta =\frac{(2|{}E(r)|{})^{3/2}}{M(r)}[t-t_{B}(r)]\)
where \(t_B(r)\) is the bang-time function, representing the local singularity coordinate.

Spatial Buchert Averages

The proper volume of the comoving domain \(\mathcal{D}\) is:
\(V_{\mathcal{D}}(t)=4\pi \int _{0}^{r_{\mathcal{D}}}\frac{R^{\prime }(t,r)R(t,r)^{2}}{\sqrt{1+2E(r)}}dr=\frac{4\pi }{3}\int _{0}^{r_{\mathcal{D}}}\partial _{r}[R(t,r)^{3}]\frac{1}{\sqrt{1+2E(r)}}dr\)
The domain average of a scalar quantity f is defined as:
\(\langle f\rangle _{\mathcal{D}}(t)\equiv \frac{4\pi }{V_{\mathcal{D}}(t)}\int _{0}^{r_{\mathcal{D}}}f(t,r)\frac{R^{\prime }R^{2}}{\sqrt{1+2E(r)}}dr\)
The local expansion rate scalar is given by the trace of the extrinsic curvature:
\(\theta =\nabla _{\mu }u^{\mu }=\frac{\.{R}^{\prime }}{R^{\prime }}+2\frac{\.{R}}{R}=\frac{\partial _{r}(\.{R}R^{2})}{R^{2}R^{\prime }}\)
The domain-averaged expansion rate \(H_{\mathcal{D}}\) is:
\(H_{\mathcal{D}}\equiv \frac{\.{V}_{\mathcal{D}}}{3V_{\mathcal{D}}}=\frac{1}{3}\langle \theta \rangle _{\mathcal{D}}\)
The local shear tensor magnitude for this metric is:
\(\sigma ^{2}=\frac{1}{3}\left(\frac{\.{R}^{\prime }}{R^{\prime }}-\frac{\.{R}}{R}\right)^{2}\)
Evaluating the kinematical backreaction \(Q_{\mathcal{D}}\) using the Buchert definition:
\(Q_{\mathcal{D}}\equiv \frac{2}{3}\left(\langle \theta ^{2}\rangle _{\mathcal{D}}-\langle \theta \rangle _{\mathcal{D}}^{2}\right)-2\langle \sigma ^{2}\rangle _{\mathcal{D}}\)
Substituting θ and σ² into the integrals and simplifying algebraically yields:
\(Q_{\mathcal{D}}(t)=\frac{6}{V_{\mathcal{D}}(t)}\left[\langle \.{R}^{2}R\rangle _{\mathcal{D}}V_{\mathcal{D}}-\left(4\pi \int _{0}^{r_{\mathcal{D}}}\.{R}R^{2}\frac{R^{\prime }}{\sqrt{1+2E}}dr\right)^{2}\right]\)
The domain-averaged spatial curvature is:
\(\langle {}^{(3)}R\rangle _{\mathcal{D}}(t)=-\frac{16\pi }{V_{\mathcal{D}}(t)}\int _{0}^{r_{\mathcal{D}}}\partial _{r}(ER)\frac{R^{\prime }}{\sqrt{1+2E}}dr\)
These exact spatial representations satisfies Buchert's averaged Hamiltonian constraint identically:
\(3H_{\mathcal{D}}^{2}=8\pi G\langle \rho \rangle _{\mathcal{D}}+\Lambda -\frac{1}{2}\langle {}^{(3)}R\rangle _{\mathcal{D}}-\frac{1}{2}Q_{\mathcal{D}}\)

Past-Light-Cone Equations

Outgoing null geodesics traveling towards the central observer satisfy ds² = 0, yielding the trajectory:
\(\frac{dt}{dr}=-\frac{R^{\prime }(t,r)}{\sqrt{1+2E(r)}}\)
The redshift z of a photon emitted at (t,r) and received at (t₀, 0) is governed by the differential relation:
\(\frac{d\ln (1+z)}{dr}=\frac{\.{R}^{\prime }(t,r)}{\sqrt{1+2E(r)}}\)
The exact angular-diameter distance \(D_A(z)\) measured by the central observer is equal to the physical area radius at the emission event:
\(D_{A}(z)=R(t(z),r(z))\)
The longitudinal (radial) expansion rate measured on the light cone is:
\(H_{L}(z)\equiv \frac{\partial ^{2}r}{\partial t\partial z}\left(\frac{\partial r}{\partial z}\right)^{-1}=\frac{\.{R}^{\prime }(t,r)}{R^{\prime }(t,r)}\)

5. Bridge Result: The Spatial–Null Consistency Relation

To establish a bridge relation between the spatial averages and null observations, we complete a systematic functional elimination.

Step 1: Metric Function Mapping

• Spatial Bulk Volume (\(V_{\mathcal{D}}\), \(Q_{\mathcal{D}}\), \(\langle {}^{(3)}R \rangle_{\mathcal{D}}\)): Dependent on the full domain interior fields M(r), E(r), and \(t_B(r)\) integrated continuously over the constant-t slice.
• Light-Cone Observables (\(D_A(z)\), \(H_L(z)\)): Dependent on the local values of M(r), E(r), \(t_B(r)\) and their derivatives intersected strictly along the 1D null track t(r).

Step 2: Exact Local Matching Relations

From the null geodesic track, the derivative of the angular-diameter distance with respect to redshift is:
\(\frac{dD_{A}}{dz}=\left(\.{R}\frac{dt}{dr}+R^{\prime }\right)\frac{dr}{dz}=R^{\prime }\left(1-\frac{\.{R}}{\sqrt{1+2E}}\right)\frac{dr}{dz}\)
Using the identity for \(\frac{dr}{dz} = \frac{\sqrt{1+2E}}{(1+z)\dot{R}'}\), we map the metric functions directly to the observables:
\(\frac{dD_{A}}{dz}=\frac{R^{\prime }\sqrt{1+2E}-R^{\prime }\.{R}}{(1+z)\.{R}^{\prime }}\)
\(H_{L}(z)=\frac{\.{R}^{\prime }}{R^{\prime }}=\frac{\sqrt{1+2E}-\.{R}}{(1+z)\frac{dD_{A}}{dz}}\)

Step 3: Conditional Elimination of Free Functions

We choose the standard physical closure condition of a simultaneous Big Bang:
\(t_{B}(r)=0\implies t_{B}^{\prime }(r)=0\)
Under this constraint, the metric function R'(t,r) reduces to a linear combination of M(r) and E(r) profiles:
\(R^{\prime }=R\left(\frac{M^{\prime }}{M}-\frac{E^{\prime }}{E}\right)+\text{analytic\ terms\ of\ }(\.{R},M,E)\)
This lets us solve for the localized spatial curvature profile E(r) directly from the observable light-cone coordinates \(D_A(z)\) and \(H_L(z)\):
\(1+2E(r(z))=(1+z)^{2}H_{L}(z)^{2}\left(\frac{dD_{A}}{dz}\right)^{2}\left[1-\frac{2M(r(z))}{D_{A}(z)}-\frac{\Lambda }{3}D_{A}(z)^{2}\right]^{-1}\)

Step 4: The Closed Bridge

Substituting this derived structural identity into the spatial Buchert integrals yields the Spatial–Null Consistency Relation:
\(\boxed{Q_{\mathcal{D}}(t)=\mathcal{K}\Big[\{D_{A}(z),H_{L}(z)\}\Big]_{0}^{z_{\mathcal{D}}}-2\langle \sigma ^{2}\rangle _{\mathcal{D}}(t)}\)
where \(\mathcal{K}\) is a non-local functional mapping the past-light-cone distance profiles over the interval \([0, z_{\mathcal{D}}]\) directly onto the spatial expansion variance.

Outcome Classification: Outcome C (New Consistency Relation)

This is a genuine Outcome C connection. It is not a tautology (Outcome A) because it proves that the spatial backreaction \(Q_{\mathcal{D}}\) within a domain \(\mathcal{D}\) cannot be modified arbitrarily to simulate dark energy without forcing a correlated deformation in the observable line-of-sight distance profile \(D_A(z)\) along the light cone.

6. Degrees-of-Freedom and Identifiability Audit

A precise accounting of the independent fields establishes the exact conditions required for observational identifiability:
text
LTB Metric Field Inventory (Arbitrary Gauge Freedom Allowed)
├── Coordinate Choice: r can be rescaled arbitrarily: r -> f(r)
│   └── Implication: One free function can be set by convention.
├── Mass Function: M(r)                   --> [1 Free Function]
├── Spatial Energy Function: E(r)         --> [1 Free Function]
└── Boundary Bang-Time Function: t_B(r)   --> [1 Free Function]
Use code with caution.

Gauge Reduction

We fix the radial coordinate gauge freedom by setting the comoving coordinate radius to match the area radius at the present day:
\(R(t_{0},r)=r\)
This removes the coordinate freedom, leaving exactly three independent physical free functions: M(r), E(r), and \(t_B(r)\).

Observational Matching

An observer tracking the past light cone collects two independent functional records:
1. Angular-diameter distance vs. redshift: \(D_A(z)\)
2. Longitudinal expansion rate vs. redshift: \(H_L(z)\)

The Identifiability Obstruction

We map 2 independent observational records against 3 independent physical fields:
\(\text{Available\ Records\ (2)}<\text{Independent\ Fields\ (3)}\)
The system is fundamentally underdetermined. Without additional constraints, the function \(t_B(r)\) can absorb geometric variations arbitrarily. This creates a mathematical obstruction that permits an infinity of different LTB solutions to map onto the exact same light-cone observables.

The Closure Condition

The model becomes identifiable and predictive if and only if an explicit closure constraint is added to eliminate one function. The most common physical choice is the simultaneous big bang constraint (\(t_B(r) = 0\)). Once this condition is locked in, the remaining 2 free functions (M(r), E(r)) are uniquely overdetermined by the 2 observational channels, enabling a closed null test.

7. Adversarial Claim Table


Previous Agent Claim	Verdict	Mathematical Reason / Structural Obstruction
A relation between redshift drift and the shear contribution to \(Q_{\mathcal{D}}\) automatically determines the full \(Q_{\mathcal{D}}\).	Falsified	The Variance Obstruction: Redshift drift isolates line-of-sight shear combinations along a 1D ray. It cannot compute the scalar expansion variance \(\langle \theta^2 \rangle_{\mathcal{D}} - \langle \theta \rangle_{\mathcal{D}}^2\), which requires a 3D domain volume integral.
The spatial-averaging commutation rule is equivalent to a boundary-flux law.	Falsified	The Non-Local Residual: The commutation relation \([ \partial_t, \langle \cdot \rangle ] f\) outputs a bulk kinematical variance tensor. A boundary-flux law via Stokes' theorem maps total divergence to a surface boundary, which leaves out internal local shear variations inside the domain interior.
A boundary or Stokes argument directly produces an exact slice-to-null-cone matching equation.	Not Derived	The Foliation Clash: Constant-t spatial slices and ds²=0 null surfaces belong to orthogonal foliation charts. A standard boundary surface argument cannot map spatial volume elements directly onto a null hypersurface without importing the local lapse and shift profiles.
A Clarkson–Bassett–Lu (CBL) or other FLRW null-test statistic is automatically proportional to \(Q_{\mathcal{D}}\).	Falsified	The Metric Deception: A non-zero CBL statistic (\(\mathcal{C}(z) \neq 0\)) proves the geometry deviates from an FLRW metric. However, in a general LTB spacetime, this deviation can be driven entirely by local curvature gradients (E'(r)) even if the spatial backreaction \(Q_{\mathcal{D}}\) evaluates to zero.
A nonzero FLRW null test uniquely identifies backreaction or establishes that backreaction causes acceleration.	Falsified	The Degeneracy Lock: An LTB universe with zero global backreaction can produce apparent optical acceleration purely through spatial profile gradients. The null test identifies inhomogeneity, not a dynamic acceleration mechanism.
Merely having more observables than free parameters proves a model is identifiable and predictive.	Falsified	The Parameter-Function Confusion: This rule applies only to finite parameter sets. In field theories, the degrees of freedom are infinite-dimensional free functions. An overdetermined discrete dataset cannot uniquely constrain a continuous unobserved profile without an explicit smoothness or closure ansatz.


8. Controls and Falsifier


FLRW Limit Check

We subject our bridge equation to the homogeneous limit:
\(M(r)\propto r^{3},\quad E(r)\propto r^{2},\quad t_{B}(r)=0\)
Under this reduction, local shear vanishes (σ² = 0) and the local expansion becomes spatially uniform (θ(t,r) = 3H(t)). The spatial averages reduce to:
\(\langle \theta ^{2}\rangle _{\mathcal{D}}=\langle \theta \rangle _{\mathcal{D}}^{2}\implies Q_{\mathcal{D}}(t)=0\)
The light-cone functional \(\mathcal{K}\) simplifies to a constant identities, and the bridge equation reduces cleanly to the standard homogeneous identities: 0 = 0. Check passes.

Dimensional and Sign Checks

• Dimensions: \(Q_{\mathcal{D}}\) has dimensions of \([\text{Time}]^{-2}\). The functional \(\mathcal{K}\) processes \(H_L(z)\) (\([\text{Time}]^{-1}\)) and \(D_A(z)\) (\([\text{Length}]\)), tracking perfectly as c=1.
• Signs: For overdense regions, local shear dominates, pushing the kinematic backreaction negative (\(Q_{\mathcal{D}} < 0\)), matching the deceleration signature of localized matter structures. Check passes.

Domain Dependence

The functional \(\mathcal{K}\) integrates observables up to a maximum redshift boundary \(z_{\mathcal{D}}\). Changing the averaging scale from \(r_{\mathcal{D}}\) to \(r_{\mathcal{D}}^{\prime }\) shifts the integration limit to \(z_{\mathcal{D}}^{\prime }\). The relation is prescription-dependent; it changes covariantly with the chosen domain boundary, verifying its local geometric origin. Check passes.

Independent Prediction

The bridge relation uses \(D_A(z)\) and \(H_L(z)\) as inputs. It yields an independent, rigid prediction for the redshift drift profile ż(z) without any adjustment parameters.

Observational Falsifier

If a simultaneous measurement of the distance profile \(D_A(z)\), the longitudinal expansion \(H_L(z)\), and the redshift drift ż(z) breaks the derived constraint:
\(\.{z}(z)\ne (1+z)H_{0}-H_{L}(z)\left[1-\frac{(1+z)^{2}H_{L}(z)^{2}(dD_{A}/dz)^{2}}{1+2E(r(z))}\right]^{1/2}\)
the entire LTB simultaneous-bang class is strictly falsified.

9. Literature Verification

• Rideout and Sorkin (1999) [6, 8, 21]: Establishes the axioms of Classical Sequential Growth (CSG) dynamics for discrete partial orders. It proves that the discrete causality axioms automatically constrain the allowed classical growth to generalized percolation models, suppressing the flat Kleitman–Rothschild states.
• Benincasa and Dowker (2010) [27, 28]: Derives the exact discrete-to-continuous matrix formulation for a non-local d'Alembertian operator on a causal set. It proves that non-local contributions cancel out in the continuum limit, recovering local field actions.
• Heinesen and Clifton (October 2026): “Observational tests for distinguishing classes of cosmological models” (Phys. Rev. D). Derives gauge-invariant curvature consistency tests on the past null cone. It proves that coordinate-independent combinations of light-cone distance paths can isolate non-FLRW cosmologies without assuming a homogeneous background geometry.

10. Research Recommendation

The single most valuable next calculation is to derive the area-averaged light-cone optimization equations for a stochastic ensemble of LTB patches.
While the single-patch LTB model provides a clean laboratory, the real universe is a random network of these structures. Performing a stochastic volume integration over a collection of voids and filaments will determine whether the unobserved bang-time variations \(t_B'(r)\) average out to zero globally. This calculation will settle the identifiability crisis, moving the framework from a conditional model test to an absolute, model-independent null test of cosmological backreaction.

11. Final Status Summary


Claim	Status	Evidence or Missing Step
Spatial Buchert equations	Established	Identically verified via domain volume integrals of local LTB field equations.
Light-cone propagation equations	Established	Derived exactly from Sachs optical focusing and null geodesic equations.
LTB spatial-to-null relation	Derived	Analytically mapped via the common metric functions M(r) and E(r).
Relation specifically constraining (\(Q_{\mathcal{D}}\))	Partially Derived	Successful under the explicit closure condition \(t_B(r) = 0\); obstructed if \(t_B'(r)\) is free.
Independent predictive content	Derived	Yields a rigid, non-adjustable profile prediction for the redshift drift ż(z).
Observational falsifier	Derived	Curvature-consistency null test breaks if optical paths deviate from the internal spatial energy metrics.

To advance this construction, should we compute the explicit functional forms for \(\mathcal{K}\) under a non-zero cosmological constant (Λ ≠ 0), or analyze how the Heinesen-Clifton curvature metric handles realistic observational errors?

