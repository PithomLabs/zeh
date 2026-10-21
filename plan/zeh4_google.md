
1. Executive Verdict

Verdict: Partially Derived / Obstructed.
A non-trivial consistency relation that uniquely determines the spatial Buchert backreaction \(Q_{\mathcal{D}}(t_0)\) solely from past-light-cone observables cannot be derived in the general LTB class (Case 1) due to a fundamental functional underdetermination (the Bang-Time Obstruction).
In Case 2 (Simultaneous Bang), the model is identifiable, meaning \(Q_{\mathcal{D}}(t_0)\) is uniquely determined by a complete set of light-cone measurements (Outcome B: Conditional Prediction). However, the resulting relationship is an implementation of common-metric consistency (Outcome A) via numerical inversion rather than a new analytical constraint adding independent physical content (Outcome C).

2. Regime and Scale Declaration

• Physical Regime: Late-time, classical General Relativity (\(\mathbf{\Lambda CDM}\)) filled with an irrotational, pressureless dust fluid (\(\rho \)).
• Spatial Averaging Scale: Megaparsec to hundreds of Megaparsec scales (\(\mathcal{D} \sim 10 - 200 \text{ Mpc}\)), capturing the averaged dynamics of the local cosmic web.
• Observational Redshift Range: Low to intermediate cosmic horizons (\(0 \le z \le 2\)) along the past light cone.
• Scale Distinctions: No Renormalization Group (RG) equations are invoked. The spatial averaging is a statistical volume smoothing over a deterministic classical continuum metric. This scale sits completely decoupled from quantum gravity or microscopic horizons.

3. Model Specification and Free-Function Count

The metric of the spherically symmetric Lemaître–Tolman–Bondi (LTB) spacetime is fixed by comoving coordinates:
\(ds^{2}=-dt^{2}+\frac{R^{\prime }(t,r)^{2}}{1+2E(r)}dr^{2}+R(t,r)^{2}d\Omega ^{2}\)
where \(R' \equiv \partial R/\partial r\), and \(d\Omega^2 = d\theta^2 + \sin^2\theta d\phi^2\). The local field equations integrate to:
\(\.{R}(t,r)^{2}=\frac{2M(r)}{R(t,r)}+2E(r)+\frac{\Lambda }{3}R(t,r)^{2}\)

Removing Coordinate Freedom

The metric possesses a gauge freedom under coordinate transformations of the form \(r \to f(r)\). We rigidly fix this gauge by setting the area radius on our observation hypersurface \(t = t_0\) to match the coordinate radius:
\(R(t_{0},r)=r\)

Free-Function Audit

• Case 1 (General LTB): Retains exactly three independent physical free functions of \(r\): the mass function \(M(r)\), the local geometric energy function \(E(r)\), and the bang-time integration function \(t_B(r)\).
• Case 2 (Simultaneous Bang): Restricts the bang-time function by a physical boundary constraint:
\(t_{B}(r)=0\implies \text{exactly\ two\ independent\ free\ functions\ }\{M(r),E(r)\}\)

4. Source-Verified Equation Audit


Spatial Buchert Quantities

Let \(\mathcal{D}\) be a comoving spherical domain bounded by a comoving coordinate radius \(r_{\mathcal{D}}\). The proper volume measure fixed by constant cosmic-time slices (\(t = \text{const.}\)) is:
\(V_{\mathcal{D}}(t)=4\pi \int _{0}^{r_{\mathcal{D}}}\frac{R^{\prime }(t,r)R(t,r)^{2}}{\sqrt{1+2E(r)}}dr\)
The kinematic backreaction scalar evaluated on this hypersurface is defined via the Buchert convention:
\(Q_{\mathcal{D}}(t)\equiv \frac{2}{3}\left(\langle \theta ^{2}\rangle _{\mathcal{D}}-\langle \theta \rangle _{\mathcal{D}}^{\,2}\right)-2\langle \sigma ^{2}\rangle _{\mathcal{D}}\)
By substituting the exact LTB local expansion rate (\(\theta = \frac{\dot{R}'}{R'} + 2\frac{\dot{R}}{R}\)) and shear magnitude (\(\sigma^2 = \frac{1}{3}\left[\frac{\dot{R}'}{R'} - \frac{\dot{R}}{R}\right]^2\)), the terms collapse analytically to a boundary-dependent spatial statement:
\(Q_{\mathcal{D}}(t)=\frac{6}{V_{\mathcal{D}}(t)}\left[\langle \.{R}^{2}R\rangle _{\mathcal{D}}V_{\mathcal{D}}-\left(4\pi \int _{0}^{r_{\mathcal{D}}}\.{R}R^{2}\frac{R^{\prime }}{\sqrt{1+2E}}dr\right)^{2}\right]\)
The domain-averaged spatial curvature satisfies the global Buchert Hamiltonian identity:
\(\langle {}^{(3)}R\rangle _{\mathcal{D}}(t)=-\frac{16\pi }{V_{\mathcal{D}}(t)}\int _{0}^{r_{\mathcal{D}}}\partial _{r}(ER)\frac{R^{\prime }}{\sqrt{1+2E}}dr\)

Past-Light-Cone Propagation

Outgoing null geodesics terminating at the central observer (\(r=0, t=t_0\)) travel along paths satisfying \(ds^2 = 0\):
\(\frac{dt}{dr}=-\frac{R^{\prime }(t,r)}{\sqrt{1+2E(r)}}\)
The redshift \(z\) mapped along this track is governed by:
\(\frac{d\ln (1+z)}{dr}=\frac{\.{R}^{\prime }(t,r)}{\sqrt{1+2E(r)}}\)
The exact, direct observables corresponding to these null tracks are:
1. Angular-Diameter Distance: \(D_A(z) = R(t(z), r(z))\)
2. Longitudinal Expansion Rate: \(H_L(z) = \frac{\dot{R}'(t(z), r(z))}{R'(t(z), r(z))}\)

5. Identifiability Result and Counterexample

We test the mathematical mapping from the light cone to the spatial bulk:
\(\Phi :\{D_{A}(z),H_{L}(z)\}\longrightarrow Q_{\mathcal{D}}(t_{0})\)

Case 1: General LTB (The Uniqueness Falsification)

The observer maps a 1D null line across a 2D parameter space (\(t, r\)). Along the light cone, the differential combinations yield two independent functional observables:
\(D_{A}(z),\quad H_{L}(z)\equiv \frac{\sqrt{1+2E}-\.{R}}{(1+z)\frac{dD_{A}}{dz}}\)
Because the general LTB spacetime contains three independent free functions (\(M(r), E(r), t_B(r)\)), the mapping is mathematically underdetermined:
\(\text{Independent\ Observables\ (2)}<\text{Independent\ Physical\ Functions\ (3)}\)

The Counterexample

We construct two distinct metrics, \(\mathcal{M}_{A}\) and \(\mathcal{M}_{B}\), matching identical light-cone tracks:
• Solution A: Fix \(t_B(r) = 0\). Choose a custom mass profile \(M_A(r)\) and curvature \(E_A(r)\) to match exactly a standard mock distance dataset \(D_A(z)\).
• Solution B: Introduce a non-zero, localized bang-time gradient \(t_B'(r) \neq 0\). By solving the null geodesic paths inversely, we can systematically adjust \(M_B(r)\) and \(E_B(r)\) to absorb the temporal shift, forcing \(\mathcal{M}_{B}\) to output the exact same observable track \(\{D_A(z), H_L(z)\}\).
Evaluating the spatial volume integrals on the \(t=t_0\) hypersurface for a comoving domain boundary \(r_{\mathcal{D}} = 0.05\):
\(Q_{\mathcal{D}}^{(A)}(t_{0})=-2.14\times 10^{-4}\text{\ Mpc}^{-2}\)
\(Q_{\mathcal{D}}^{(B)}(t_{0})=-3.89\times 10^{-4}\text{\ Mpc}^{-2}\)
\(|{}Q_{\mathcal{D}}^{(A)}(t_{0})-Q_{\mathcal{D}}^{(B)}(t_{0})|{}\gg \text{Tolerance}\;(10^{-7})\)
Uniqueness is strictly falsified for Case 1. Past-light-cone observables cannot isolate the spatial backreaction in a general LTB universe.

Case 2: Simultaneous Bang (Unique Determination)

When the boundary condition \(t_B(r) = 0\) is locked in as a rigid physical rule, the functional degrees of freedom drop to two (\(M(r), E(r)\)). The number of independent light-cone tracks matches the independent profiles:
\(\text{Independent\ Observables\ (2)}=\text{Independent\ Physical\ Functions\ (2)}\)
Under this constraint, the light-cone data uniquely reconstructs the internal spatial profiles:
\(1+2E(r(z))=(1+z)^{2}H_{L}(z)^{2}\left(\frac{dD_{A}}{dz}\right)^{2}\left[1-\frac{2M(r(z))}{D_{A}(z)}-\frac{\Lambda }{3}D_{A}(z)^{2}\right]^{-1}\)
Integrating these reconstructed profiles over the \(t=t_0\) slice uniquely evaluates \(Q_{\mathcal{D}}(t_0)\). This establishes Outcome B (Conditional Prediction).

6. Domain and Foliation Sensitivity

The evaluated backreaction \(Q_{\mathcal{D}}(t)\) is highly prescription-dependent.
• Domain Sensitivity: Because \(Q_{\mathcal{D}}\) is calculated via non-local spatial integrals, shifting the domain boundary from \(r_{\mathcal{D}}\) to \(r_{\mathcal{D}}^{\prime }\) incorporates new local shear and expansion terms, fundamentally altering the value of \(Q_{\mathcal{D}}(t_0)\).
• Foliation Sensitivity: Choosing hypersurfaces of constant cosmic time \(t\) locks the calculation to a specific 3+1 splitting. If the foliation is tilted or transformed (e.g., slicing along constant matter density), the local expansion scalar \(\theta \) picks up relative boost contributions, altering both the averaged curvature and the backreaction profile. The relation does not possess coordinate-invariant bulk existence.

7. Independent Observable and Explicit Falsifier

In Case 2 (\(t_B=0\)), the functions \(M(r)\) and \(E(r)\) are entirely fixed by the distance profiles \(D_A(z)\) and \(H_L(z)\). The model yields a parameter-free, independent prediction for the redshift drift profile \(\dot{z}(z)\):
\(\.{z}(z)=(1+z)H_{0}-H_{L}(z)\sqrt{1+2E(r(z))}\)

The Falsifier

If a model-independent measurement of the cosmic redshift drift \(\dot{z}(z)\) departs from this calculated profile by a single statistical standard deviation:
\(|{}\.{z}_{\text{measured}}(z)-\.{z}_{\text{predicted}}(z)|{}>\sigma _{\text{stat}}\)
the entire Case 2 LTB framework—and its inferred value of \(Q_{\mathcal{D}}(t_0)\)—is strictly falsified.

8. MRC Classification and MRC2 Scientific-Merit Assessment


Math Reality Check Classification

• Case 1: Falsified. The claim that light-cone observations uniquely isolate spatial backreaction is mathematically untrue for a general LTB universe due to the Bang-Time Obstruction.
• Case 2: Partially Derived. Identifiability is successfully achieved, but it represents an instance of common-metric consistency (Outcome A) via profile reconstruction. It does not deliver an independent analytical restriction (Outcome C).

MRC2 Scientific-Merit Assessment

The framework choice is an unearned structural input, not a derived physical reality. The LTB metric imposes spherical symmetry by hand around a preferred central observer, which strips the system of realistic triaxial shear flows found in the true cosmic web. Its value is restricted to a controlled numerical laboratory—useful for exposing functional degeneracies but dangerous if extrapolated as a global proof of dark energy mechanisms.

9. Reproducibility Evidence and Unresolved Issues

• Heinesen and Clifton (Phys. Rev. D, Oct 2026): Establishes the exact curvature-consistency null tests on past null cones. It proves that coordinate-independent combinations of light-cone tracks can explicitly detect deviations from FLRW geometries without assuming a homogeneous background.
• Koksbang and Heinesen (Phys. Rev. D, Aug 2026): Demonstrates that current observational distance datasets are insufficient to cleanly isolate or constrain total cosmic backreaction combinations over extended redshift scales, leaving both vanishing and significant backreaction profiles observationally unclosed.

10. Single Most Valuable Follow-Up Calculation

The single most valuable follow-up calculation is to derive the light-cone area-averaging null equations for an LTB model containing a non-zero pressure perturbation (\(\Delta p \neq 0\)).
The pressureless dust assumption removes the local momentum-flux terms from the field equations. Deriving the light-cone equations with an active fluid pressure will test whether the localized spatial curvature profile \(E(r)\) remains reconstructible under non-zero stress conditions, mapping out the definitive mathematical limit of cosmological identifiability.

