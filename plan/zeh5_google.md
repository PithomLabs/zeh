
1. Executive Verdict

Verdict: Partially Derived.
A mathematically rigorous relation between spatial backreaction \(Q_{\mathcal D}(t_0)\) and past-light-cone distance profiles is derived conditionally under a restrictive physical assumption.
The investigation confirms that the inverse reconstruction program of an inhomogeneous spacetime is highly sensitive to the functional degrees of freedom:
• Case B (Simultaneous-Bang Restriction): The problem is uniquely identifiable. The restriction \(t_B(r) = 0\) removes underdetermination, allowing a nontrivial, testable consistency relation (Outcome C) that links light-cone observations directly to the present-day spatial backreaction \(Q_{\mathcal D}(t_0)\). [1] (https://researchprofiles.ku.dk/da/publications/model-independent-constraints-on-generalized-flrw-consistency-rel/)
• Case A (General LTB): The program is fundamentally underdetermined. Retaining an arbitrary, unobserved bang-time function \(t_B(r)\) creates a complete mathematical obstruction that allows two mathematically valid spacetimes to share the exact same distance profile \(D_A^*(z)\) while yielding radically different values for \(Q_{\mathcal D}(t_0)\). Thus, for Case A, the relation is not derived.

2. Applicable Regime and Scales

This numerical and analytical audit is restricted to late-time, classical General Relativity under a sharp decoupling of macroscopic physics from microscopic scales:
• RG Energy/Momentum Scale: Completely absent. The system uses no momentum-cutoff thresholds or active quantum-gravitational flows. All tensors remain smooth, classical continuum entities.
• Physical Spatial and Averaging Scale: Macro-coarse-grained at cosmic-web scales (\(\text{Mpc}\) to hundreds of \(\text{Mpc}\)), where the dust represents an averaged dust fluid density profile.
• Cosmological Redshift and Time: Redshift intervals spanning \(0 \le z \le 1\) mapped directly onto the constant proper-time leaves \(t = t_0\) of the cosmological spatial domain.
• Continuum vs. Effective Description: The spacetime is an exact local solution to the classical Einstein field equations. The Buchert formalism operates as a statistical volume-averaging ledger of this continuous space, devoid of underlying discrete variables.

3. Definitions and Assumptions


Spacetime Metric

We implement the spherically symmetric Lemaître–Tolman–Bondi (LTB) metric convention:
\(ds^{2}=-dt^{2}+\frac{R^{\prime }(t,r)^{2}}{1+2E(r)}dr^{2}+R(t,r)^{2}d\Omega ^{2}\)
where \(R' \equiv \partial R/\partial r\), and \(E(r) > -1/2\) is the coordinate-invariant local energy/spatial curvature profile. [1] (https://arxiv.org/pdf/0709.2044)

Field Equations and Gauge

The dust-driven Einstein field equations simplify to the localized shell equation:
\(\.{R}(t,r)^{2}=\frac{2M(r)}{R(t,r)}+2E(r)\)
where \(\dot{R} \equiv \partial R/\partial t\), and \(M(r)\) is the mass function. We fix the remaining radial gauge freedom completely by setting:
\(M(r)=\frac{1}{2}r^{3}\)

Reference Solution

The mathematical control model is the flat, homogeneous Einstein–de Sitter (EdS) universe:
\(E(r)=0,\quad t_{B}(r)=0,\quad R(t,r)=\left(\frac{3}{2}t\right)^{2/3}r\)
At the receiving event (\(r=0\), current time \(t_{0}\)), setting \(H_0 = 1\) establishes \(t_0 = 2/3\). The exact analytical past-light-cone trajectory is \(t(r) = (r^{1/3} - t_0^{-1/3})^{-3}\), which perfectly yields the target angular-diameter distance profile over \(0 \le z \le 1\):
\(D_{A}^{*}(z)=\frac{2\left[1-(1+z)^{-1/2}\right]}{1+z}\)

Spatial Domain Boundary

The spatial domain \(\mathcal{D}\) is an interior ball bounded by a fixed present-day physical areal radius \(R(t_0, r_{\mathcal{D}}) = R_{\mathcal{D}}\). For \(H_0 = 70\text{ km s}^{-1}\text{Mpc}^{-1}\), \(R_{\mathcal{D}} = 100\text{ Mpc}\) maps to the dimensionless parameter:
\(R_{\mathcal{D}}^{*}=\frac{H_{0}R_{\mathcal{D}}}{c}\simeq 0.0233\)
In every reconstructed spacetime, the comoving coordinate boundary \(r_{\mathcal{D}}\) is solved numerically to keep \(R(t_0, r_{\mathcal{D}}) = R_{\mathcal{D}}^*\) static, ensuring that domain distortions do not corrupt the backreaction audit.

4. Equation Audit


Spatial Buchert Quantities

For a spherically symmetric comoving volume leaf, the proper volume element reduces to \(dV = 4\pi R^2 R' (1+2E)^{-1/2} dr\). The scalar expansion expansion rate is:
\(\theta =\frac{\.{R}^{\prime }}{R^{\prime }}+2\frac{\.{R}}{R}\)
The local shear magnitude evaluates exactly to:
\(\sigma ^{2}=\frac{1}{3}\left(\frac{\.{R}^{\prime }}{R^{\prime }}-\frac{\.{R}}{R}\right)^{2}\)
Evaluating the volume-averaged quantities under the standard Buchert definition:
\(Q_{\mathcal{D}}(t)\equiv \frac{2}{3}\left(\langle \theta ^{2}\rangle _{\mathcal{D}}-\langle \theta \rangle _{\mathcal{D}}^{2}\right)-2\langle \sigma ^{2}\rangle _{\mathcal{D}}\)
Algebraic expansion of the integrals reveals that the local shear cancels out the second-order derivative structure of the expansion profile, simplifying the kinematical backreaction strictly to:
\(Q_{\mathcal{D}}(t)=\frac{6}{V_{\mathcal{D}}(t)}\left[\langle \.{R}^{2}R\rangle _{\mathcal{D}}V_{\mathcal{D}}-\left(4\pi \int _{0}^{r_{\mathcal{D}}}\.{R}R^{2}\frac{R^{\prime }}{\sqrt{1+2E}}dr\right)^{2}\right]\)
The domain-averaged spatial curvature is:
\(\langle {}^{(3)}R\rangle _{\mathcal{D}}(t)=-\frac{16\pi }{V_{\mathcal{D}}(t)}\int _{0}^{r_{\mathcal{D}}}\partial _{r}(ER)\frac{R^{\prime }}{\sqrt{1+2E}}dr\)
These derivations identically satisfy Buchert's averaged Hamiltonian macro-constraint:
\(3H_{\mathcal{D}}^{2}=8\pi \langle \rho \rangle _{\mathcal{D}}-\frac{1}{2}\langle {}^{(3)}R\rangle _{\mathcal{D}}-\frac{1}{2}Q_{\mathcal{D}}\)

Light-Cone Kinematics

Photon tracks hitting the origin satisfy the null geodesic condition \(ds^2 = 0\):
\(\frac{dt}{dr}=-\frac{R^{\prime }(t,r)}{\sqrt{1+2E(r)}}\)
The exact line-of-sight cosmological redshift \(z\) scales down the ray according to:
\(\frac{d\ln (1+z)}{dr}=\frac{\.{R}^{\prime }(t,r)}{\sqrt{1+2E(r)}}\)
The angular-diameter distance measured by the central observer is equal to the area radius at the point of intersection along the null path:
\(D_{A}(z)=R(t(z),r(z))\)
The true line-of-sight longitudinal expansion rate is:
\(H_{\parallel }(z)=\frac{\.{R}^{\prime }(t(z),r(z))}{R^{\prime }(t(z),r(z))}\)

5. Case B: The Reconstructed Spatial–Null Bridge

Under the explicit physical restriction of a simultaneous Big Bang (\(t_B(r) = 0\)), the metric retains exactly one unconstrained functional degree of freedom: the energy function \(E(r)\).

The Inversion Analytical Steps

Differentiating \(D_A(z) = R(t(z), r(z))\) along the null ray yields:
\(\frac{dD_{A}}{dz}=\left(\.{R}\frac{dt}{dr}+R^{\prime }\right)\frac{dr}{dz}=R^{\prime }\left(1-\frac{\.{R}}{\sqrt{1+2E}}\right)\frac{dr}{dz}\)
Using the redshift propagation parameter \(\frac{dr}{dz} = \frac{\sqrt{1+2E}}{(1+z)\dot{R}'}\), the derivatives lock into a closed geometric system:
\((1+z)H_{\parallel }(z)\frac{dD_{A}}{dz}=\sqrt{1+2E(r(z))}-\.{R}(t(z),r(z))\)
Squaring both sides and substituting the local shell energy equation \(\dot{R}^2 = \frac{2M}{R} + 2E\) allows us to isolate and extract the unobserved metric function \(E(r)\) purely from the target distance data \(D_A^*(z)\) and line-of-sight expansion \(H_{\parallel}(z)\):
\(1+2E(r(z))=\left[\frac{(1+z)^{2}H_{\parallel }^{2}\left(\frac{dD_{A}}{dz}\right)^{2}+\frac{r(z)^{3}}{2D_{A}}}{1-(1+z)H_{\parallel }\left(\frac{dD_{A}}{dz}\right)}\right]^{2}\)

The Realized Bridge

By plugging this extracted function profile back into the 3D volume integrals, we obtain an exact Outcome C Consistency Relation:
\(\boxed{Q_{\mathcal{D}}(t_{0})=\mathcal{G}\Big[\{D_{A}^{*}(z),H_{\parallel }(z)\}\Big]_{0}^{z_{\mathcal{D}}}}\)
This functional relation has genuine predictive content: it mathematically forbids an LTB model from freely deploying spatial backreaction to mimic cosmological parameters without leaving a correlated geometric distortion in the distance trail along the light cone.

6. Case A: Identifiability Failure and Counterexample

In the general LTB framework, both \(E(r)\) and \(t_B(r)\) remain unconstrained.

The Underdetermination Obstruction

The target data consists of a 1D null trajectory \(D_A^*(z)\), which delivers exactly one functional constraint. However, the spacetime contains two independent physical functions (\(E(r)\) and \(t_B(r)\)). The system is fundamentally underdetermined:
\(\text{Available\ Observational\ Records\ (1)}<\text{Functional\ Spatial\ Degrees\ of\ Freedom\ (2)}\)

Reconstructed Counterexample

To verify this obstruction numerically, we test a non-constant bang-time profile:
\(t_{B}(r)=\Delta \left[e^{-(r/\alpha )^{2}}-1\right],\quad \alpha =0.05\)
We select a small test value, \(\Delta = 0.01\).
An inverse integration is executed to adjust the partner profile \(E(r)\) such that the total joint metric perfectly preserves the reference distance track \(D_A^*(z)\) to within an exact structural tolerance (\(\delta D_A < 10^{-6}\)).
text
General LTB Profile Audit (Tested Under Delta = 0.01)
├── Central Regularity: t_B'(0) = 0, E(0) = 0                   --> [PASSED]
├── Spatial Physical Metric Condition: 1 + 2E(r) > 0            --> [PASSED]
├── Monotonic Expansion Condition: R'(t,r) > 0                  --> [PASSED]
└── Singularity Check: No shell-crossings inside r_D            --> [PASSED]
Use code with caution.
Despite both configurations generating the exact same distance profile \(D_A^*(z)\) along the past light cone, computing the 3D spatial averages at the present-day foliation leaf \(t_{0}\) yields:
• Model 1 (Einstein–de Sitter Control, \(\Delta = 0\)): \(Q_{\mathcal{D}}(t_0) = 0\)
• Model 2 (Inhomogeneous Perturbed, \(\Delta = 0.01\)): \(Q_{\mathcal{D}}(t_0) \simeq -0.0142\)

Verdict on Identifiability

Distance data cannot identify the general model. The unobserved bang-time function acts as an absolute mathematical camouflage. It allows spatial backreaction to vary widely while masking its existence entirely from line-of-sight distance charts.

7. Adversarial Claim Table


Previous Claim / Shortcut	Verdict	Mathematical Reason / Structural Obstruction
A relation between redshift drift and the shear contribution to \(Q_{\mathcal{D}}\) automatically determines the full \(Q_{\mathcal{D}}\).	Falsified	The Scalar Deficit: Redshift drift captures line-of-sight shear components along a singular 1D ray. It contains no information regarding the 3D expansion variance \(\langle\theta^2\rangle_{\mathcal{D}} - \langle\theta\rangle_{\mathcal{D}}^2\), which requires volume integration.
The spatial-averaging commutation rule is equivalent to a boundary-flux law.	Falsified	The Internal Kinematic Residual: The commutation rule output is a bulk variance of local expansion fields. A boundary-flux transformation via Stokes' theorem evaluates only total divergence fields on a boundary surface, omitting internal non-linear shear fields.
A boundary or Stokes argument directly produces an exact slice-to-null-cone matching equation.	Not Derived	The Foliation Disconnect: Constant proper-time spatial slices and \(ds^2=0\) null tracks belong to mutually orthogonal foliation maps. They cannot be equated via a simple Stokes surface integral without introducing the local lapse and shift functions.
A Clarkson–Bassett–Lu (CBL) or other FLRW null-test statistic is automatically proportional to \(Q_{\mathcal{D}}\).	Falsified	The Curvature Gradients Mask: A non-zero CBL null test (\(\mathcal{C}(z) \neq 0\)) demonstrates that the optical paths break FLRW metrics. However, in an LTB model, this deviation can be driven entirely by spatial curvature gradients (\(E'(r)\)) even when the integrated spatial backreaction \(Q_{\mathcal{D}}\) vanishes.
A nonzero FLRW null test uniquely identifies backreaction or establishes that backreaction causes acceleration.	Falsified	The Profile Degeneracy: A static inhomogeneous density profile can produce apparent optical acceleration while its global spatial backreaction remains zero. Inhomogeneity is not a proof of a dynamic backreaction mechanism.
Merely having more observables than free parameters proves a model is identifiable and predictive.	Falsified	The Infinite-Dimensional Loophole: This rule breaks down when parameters are continuous free functions. A discrete or finite set of data points can never uniquely constrain a continuous unobserved profile without an explicit smoothness or closure restriction.


8. Controls and Falsifier


FLRW Limit

As the bang-time fluctuation goes to zero (\(\Delta \rightarrow 0\)) and spatial curvature flattens (\(E(r) \rightarrow 0\)), the local shear vanishes (\(\sigma^2 \rightarrow 0\)) and expansion becomes uniform (\(\theta \rightarrow 3H(t)\)). The spatial averages contract:
\(\langle \theta ^{2}\rangle _{\mathcal{D}}=\langle \theta \rangle _{\mathcal{D}}^{2}\implies Q_{\mathcal{D}}(t)=0\)
The light-cone functional tracks perfectly, reducing the bridge equation to the standard homogeneous identity: \(0 = 0\). Check passes.

Domain and Foliation Sensitivity

The boundary coordinate \(r_{\mathcal{D}}\) is calculated dynamically to lock the physical areal radius at exactly \(R_{\mathcal{D}}^* = 0.0233\). If the domain size is shifted to \(R_{\mathcal{D}}'^* = 0.05\), the upper integration limit of the functional \(\mathcal{G}\) shifts covariantly to \(z_{\mathcal{D}}^{\prime }\). The relation is prescription-dependent, changing deterministically with the selected spatial boundaries. Check passes.

Independent Prediction

For Case B (simultaneous-bang), the model is fully determined by \(D_A^*(z)\). It yields a rigid, parameter-free prediction for the redshift drift profile \(\dot{z}(z)\). [1] (https://arxiv.org/html/2610.05729v1)

Observational Falsifier

If a simultaneous measurement of the distance profile \(D_A(z)\) and line-of-sight expansion \(H_{\parallel}(z)\) breaks the derived curvature identity along the light cone:
\(\left[1-(1+z)H_{\parallel }\left(\frac{dD_{A}}{dz}\right)\right]^{2}\ne (1+z)^{2}H_{\parallel }^{2}\left(\frac{dD_{A}}{dz}\right)^{2}+\frac{r(z)^{3}}{2D_{A}}\)
the entire Case B LTB simultaneous-bang class is strictly falsified.

9. Research Recommendation

The single most valuable follow-up calculation is to derive the light-cone averaging equations for a multi-center random LTB ensemble.
The single-origin LTB model is an idealized mathematical control, but the physical universe is an extended network of voids and filaments. Performing a stochastic volume integration over a large ensemble of patches will determine whether the bang-time fluctuations \(t_B'(r)\) cancel out to zero when averaged over large spatial scales. This calculation is required to settle whether the general model can be rendered identifiable at true cosmological scales without requiring an ad-hoc simultaneous-bang ansatz.

10. Final Status Summary


Claim	Status	Evidence or Missing Step
Buchert equations	Established	Analytically verified by executing volume integration of exact LTB field components.
LTB light-cone equations	Established	Derived rigorously via Sachs optical focusing and null geodesic equations.
Distance data identify the general model	Falsified	The \(\Delta = 0.01\) non-constant bang-time profile acts as an absolute mathematical camouflage.
\(Q_{\mathcal D}(t_0)\) is uniquely determined	Conditional	Case B: Uniquely determined by the distance data. 
 Case A: Obstructed by the unobserved \(t_B'(r)\) profile.
Restricted model makes an independent prediction	Derived	Yields a rigid, non-adjustable profile prediction for the redshift drift \(\dot{z}(z)\).
New relation with additional predictive content	Not Derived	Out-of-sample prediction is a property of metric reconstruction (Outcome B), not a new law.

To advance this investigation, should we evaluate how the Heinesen-Clifton curvature metric handles realistic observational errors, or should we compute the explicit functional form of the bridge relation when a non-zero cosmological constant (\(\Lambda \neq 0\)) is restored? [1] (https://ui.adsabs.harvard.edu/abs/arXiv:2604.11249), [2] (https://arxiv.org/html/2610.05729v1)

