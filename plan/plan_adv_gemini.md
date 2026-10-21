# Executive Scope Recommendation and Literature Lock: Identifiability of Buchert Kinematical Backreaction in LTB Cosmology

---

## 1. Recommended Provisional Title

**"Identifiability and Functional Degeneracy of Buchert Kinematical Backreaction from Past-Light-Cone Distance-Redshift Observations in Central-Observer Lemaître–Tolman–Bondi Cosmology"** (with conditional alternative: *"Identifiability of Buchert Backreaction from Past-Light-Cone Observables in LTB Cosmology: A Conditional Reconstruction Theorem"*).

---

## 2. One-Sentence Primary Research Question

Within central-observer Lemaître–Tolman–Bondi (LTB) dust cosmology with zero cosmological constant ($\Lambda = 0$) and explicit radial gauge fixture $M(r) = r^{3/2}$, does the past-light-cone angular diameter distance $D_A(z)$ uniquely determine the present-day Buchert kinematical backreaction $Q_{\mathcal{D}}(t_0)$ over a specified comoving spatial domain $\mathcal{D}$, and under what explicit mathematical subclass restrictions or additional observable sets does unique reconstruction hold?

---

## 3. Research Gap and Literature Comparison

The literature surrounding LTB inverse problems and spatial averaging splits into disjoint formalisms:

* **Optical Inverse Reconstruction:** Mustapha, Hellaby, and Ellis (1997) and Lu and Hellaby (2007) proved that observing a single isotropic light-cone distance $D_A(z)$ leaves an unconstrained functional degree of freedom between the spatial curvature profile $E(r)$ and the bang-time profile $t_B(r)$, requiring a second independent observable (such as galaxy number counts $n(z)$ or expansion rates) to achieve uniqueness. Célérier (2000) showed inhomogeneous LTB models fit $D_A(z)$ without a cosmological constant but omitted spatial backreaction calculations.


* **Spatial Averaging & Backreaction:** Buchert (2000, 2011) established non-perturbative scalar averaging on constant-time slices, defining $Q_{\mathcal{D}}(t)$, while Sussman (2008) proved that central averaging domains exhibit a sign constraint determined strictly by spatial curvature type ($Q_{\mathcal{D}} \le 0$ for elliptic, $Q_{\mathcal{D}} \ge 0$ for hyperbolic models).


* **Recent Developments:** Heinesen et al. (2019, 2022) formulated covariant past-null-cone averaging, and Green & Wald (2011, 2015) demonstrated perturbative backreaction suppression under high-frequency limits.



**The Gap:** No prior work rigorously quantifies whether the functional light-cone degeneracy between $E(r)$ and $t_B(r)$ under $D_A(z)$ alone propagates into a functional variance or uncertainty in the slice-defined spatial backreaction $Q_{\mathcal{D}}(t_0)$. The proposed paper bridges this gap by establishing exact conditions for conditional identifiability and non-identifiability.

---

## 4. Principal Candidate Contribution (Conjectural)

The project establishes a dual analytical contribution:

1. **The General LTB Functional Degeneracy Theorem (Negative Result):** A formal proof demonstrating that a single optical observable $D_A(z)$ on the past light cone is insufficient to uniquely reconstruct $Q_{\mathcal{D}}(t_0)$ in general LTB dust models. The unconstrained functional freedom maps a single distance function to a continuous family of distinct spatial backreaction values evaluated at $t = t_0$.


2. **The Simultaneous-Bang Reconstruction Theorem (Positive Companion):** A formal analytical derivation proving that under the explicit subclass restriction $t_B(r) \equiv 0$, $D_A(z)$ uniquely determines the spatial energy profile $E(r)$ and consequently fixes $Q_{\mathcal{D}}(t_0)$ across comoving domains.



---

## 5. Minimum Mathematical Obligations

To establish these claims, the mathematical roadmap requires:

* **O1 & O2:** Formulate the driven on-cone differential system and verify well-posedness, boundary regularity, and vertex series expansion.


* **O3:** Construct the exact $Q_2$ functional by expanding $Q_{\mathcal{D}}(t_0)$ to second order along the iso-distance family $\Psi(u)$ to test non-constancy.


* **O4 & O5:** Account for the fixed physical domain radius $R(t_0, r_{\mathcal{D}}) = R_{\text{phys}}$ and audit linear-response behavior against EdS.


* **O6:** Rigorously establish restricted uniqueness under $t_B(r) \equiv 0$.


* **O7 & O8:** Analyze held-out observable channels ($H_\parallel(z)$ and redshift drift) and complete integrability condition bookkeeping.



---

## 6. Relevant Assumptions, Physical Regime, Scale, Domain, Foliation, and Observable Set

| Parameter / Feature | Specification |
| --- | --- |
| **Spacetime Theory** | Classical General Relativity ($\Lambda = 0$, $c = G = 1$)

 |
| **Matter Content** | Irrotational, pressureless dust fluid

 |
| **Radial Gauge Fixture** | $M(r) = r^{3/2}$ (eliminates coordinate redundancy)

 |
| **Observer Position** | Strictly central observer situated at $r = 0, t = t_0$<br> |
| **Foliation Choice** | Synchronous comoving dust proper-time hypersurfaces ($t = \text{constant}$)

 |
| **Averaging Domain $\mathcal{D}$** | Symmetrical comoving sphere $r \le r_{\mathcal{D}}$ with physical boundary scale $\sim 100$ Mpc

 |
| **Primary Observable Input** | Past-null-cone angular diameter distance $D_A(z)$ over $0 \le z \le 1$<br> |

---

## 7. Explicit Non-Claims

The manuscript will strictly avoid overreaching claims:

* The paper **will not claim** that spatial kinematical backreaction $Q_{\mathcal{D}}(t_0)$ replaces dark energy or drives cosmic acceleration in the real universe.


* The paper **will not claim** validity for off-center observers, non-spherically symmetric spacetimes (e.g., Szekeres models), or non-dust fluids.


* The paper **will not present** numerical survey fits, observational data inversions, or MCMC parameter estimations.


* The paper **will not claim** gauge invariance under alternative non-comoving spatial foliations or assert a closed local consistency relation (Outcome C).



---

## 8. Out-of-Scope Topics and Stopping Condition

* **Out of Scope:** Quantum gravity, $\Lambda > 0$ models, scalar-tensor theories, modified gravity, relativistic $N$-body simulations, CMB/BAO analyses, and light-cone averaging formalisms.


* **Stopping Condition:** The project reaches its formal stopping condition upon completing the pen-and-paper proofs of the non-identifiability family and the simultaneous-bang uniqueness theorem. If analytical evaluation reveals an invariant branch ($\mathcal{Q}_2 \equiv \text{constant}$), the paper transitions to an exact invariance theorem.



---

## 9. Proposed Paper Outline

1. **Introduction:** Inhomogeneous cosmology, spatial averaging, and the optical inverse reconstruction gap.


2. **Mathematical Framework:** LTB geometry, radial gauge fixing $M(r) = r^{3/2}$, Buchert scalar averaging, and past-null-cone optics.


3. **Non-Identifiability of Backreaction in General LTB:** Light-cone functional degeneracy between $E(r)$ and $t_B(r)$ and proof of Theorem 1.


4. **Reconstruction Under the Simultaneous-Bang Restriction:** Proof of Theorem 2 ($t_B(r) \equiv 0$) and analytical mapping to $E(r)$ and $Q_{\mathcal{D}}(t_0)$.


5. **Held-Out Channels and Complementary Observables:** Evaluating $H_\parallel(z)$ and redshift drift to break degeneracies.


6. **Discussion and Literature Comparison:** Relation to Mustapha et al., Célérier, Sussman, and past-null-cone frameworks.


7. **Conclusions:** Summary of the conditional identifiability and degeneracy results.



---

## 10. Recommendation for ZEH-6

**REVISE, THEN GO.**
The research scope is fully tractable via pen-and-paper analytical derivation and a rigorous degrees-of-freedom census. Numerical execution (ZEH-6) is unnecessary for establishing the primary mathematical theorems and should be restricted solely to illustrative plotting of degeneracy bounds for a controlled EdS reference target. Proceed immediately to analytical drafting.
