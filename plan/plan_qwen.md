Here is the bounded manuscript plan, strictly aligned with the Reality-First methodology and the Math Reality Check constraints. It leverages **Degrees of Freedom** (as a strict census) and **Invariants** (as a shield) to establish a rigorous, analytically defensible negative result, avoiding any numerical fishing expeditions or overreach.

---

### 1. Recommended Provisional Title
**Underdetermination of Kinematical Backreaction from Angular Diameter Distance in Lemaître–Tolman–Bondi Cosmology**

### 2. One-Sentence Primary Research Question
Does the past-light-cone angular diameter distance $D_A(z)$ alone uniquely determine the present-day Buchert kinematical backreaction $\mathcal{Q}_\mathcal{D}(t_0)$ in a central-observer LTB dust cosmology, or does a fundamental functional degeneracy persist?

### 3. The Research Gap
Prior LTB inverse-problem literature (e.g., Mustapha, Hellaby & Ellis 1997; Célérier 2000) establishes that *two* observables (e.g., $D_A(z)$ and $H(z)$, or redshift drift) are required to uniquely reconstruct the two metric free functions ($E(r)$ and $t_B(r)$). Concurrently, Buchert averaging studies in LTB (e.g., Bolejko 2008; Valkenburg 2012) compute $\mathcal{Q}_\mathcal{D}$ for *specific, fully specified* metric profiles. 
**The Gap:** There is no explicit, analytical proof quantifying the exact degree of underdetermination of $\mathcal{Q}_\mathcal{D}(t_0)$ when restricted to $D_A(z)$ alone. The literature often implicitly assumes priors (like a simultaneous bang) to close the system, without formally proving that dropping this prior leaves $\mathcal{Q}_\mathcal{D}(t_0)$ as a continuously degenerate, prior-dependent quantity rather than an observable-derived invariant.

### 4. Principal Candidate Contribution
A rigorous analytical proof (a "Degrees of Freedom Census" theorem) demonstrating that for a fixed $D_A(z)$, the space of compatible LTB metrics is parameterized by exactly one arbitrary function (e.g., the bang time profile $t_B(r)$). Consequently, $\mathcal{Q}_\mathcal{D}(t_0)$ varies continuously across this degenerate space, proving it cannot be reconstructed from $D_A(z)$ without additional, non-observable physical priors.

### 5. Minimum Mathematical Obligations
To establish this, the paper must analytically deliver:
1. **The Metric Setup:** The exact LTB line element in the $M(r) = r^3/2$ gauge, defining the two free functions $E(r)$ and $t_B(r)$.
2. **The Observable Functional:** The null geodesic equations yielding $D_A(z)$ strictly as a functional of $E(r)$ and $t_B(r)$ along the past light cone.
3. **The Backreaction Functional:** The exact expression for $\mathcal{Q}_\mathcal{D}(t_0)$ as a spatial volume average of $\langle \sigma^2 \rangle_\mathcal{D}$ and $\langle \theta^2 \rangle_\mathcal{D}$ over a specified comoving domain $r \leq r_\mathcal{D}$.
4. **The Degeneracy Proof:** An analytical demonstration (e.g., via functional variation or a constructed one-parameter family of perturbations around an Einstein-de Sitter background) showing that $\delta D_A(z) = 0$ does *not* imply $\delta \mathcal{Q}_\mathcal{D}(t_0) = 0$.

### 6. Fixed Assumptions and Scope Boundaries
- **Physical Regime:** Classical GR, irrotational pressureless dust, $\Lambda = 0$, $c = G = 1$.
- **Gauge:** $M(r) = r^3/2$ (central observer at $r=0$).
- **Foliation:** Comoving dust slices ($t = \text{constant}$). $\mathcal{Q}_\mathcal{D}$ is evaluated strictly on a spatial slice, distinct from light-cone averaging.
- **Domain:** A specified comoving spatial domain $\mathcal{D}$ defined by $r \leq r_\mathcal{D}$, with physical boundary $R(t_0, r_\mathcal{D})$.
- **Observable Set:** Solely the past-light-cone angular diameter distance $D_A(z)$ for $0 \leq z \leq z_{\text{max}}$. ($H(z)$ and redshift drift are explicitly excluded from the reconstruction to prove the underdetermination).

### 7. Explicit Claims the Paper Will NOT Make
- We will **not** claim that $\mathcal{Q}_\mathcal{D}$ is fundamentally unobservable (adding $H(z)$ resolves the degeneracy).
- We will **not** claim that $\mathcal{Q}_\mathcal{D}$ is zero, negligible, or the source of dark energy.
- We will **not** claim to solve the inverse problem numerically or provide best-fit parameters.
- We will **not** conflate spatial Buchert backreaction $\mathcal{Q}_\mathcal{D}$ with optical/light-cone backreaction (we will explicitly distinguish them).

### 8. Out-of-Scope Topics and Stopping Condition
- **Out of Scope:** $\Lambda > 0$, non-dust matter, off-center observers, numerical inversion algorithms, MCMC parameter estimation, and light-cone averaging formalisms.
- **Stopping Condition:** The analytical demonstration of the functional degeneracy of $\mathcal{Q}_\mathcal{D}(t_0)$ under fixed $D_A(z)$ is complete. The paper ends once the mathematical census proves the underdetermination. No numerical reconstructions (ZEH-6) will be executed or included.

### 9. Proposed Paper Outline
- **Abstract:** State the underdetermination result clearly and its implication for observational priors.
- **1. Introduction:** Context of backreaction, the LTB inverse problem, and the specific gap (single-observable degeneracy).
- **2. Mathematical Framework:** 
  - 2.1 LTB metric and gauge fixing.
  - 2.2 Buchert kinematical backreaction $\mathcal{Q}_\mathcal{D}$ definition on comoving slices.
  - 2.3 Past-light-cone observables: Null geodesics and the $D_A(z)$ functional.
- **3. The Degrees of Freedom Census (Core Result):** 
  - 3.1 Counting: 2 free functions ($E(r)$, $t_B(r)$) vs. 1 observable constraint ($D_A(z)$).
  - 3.2 Analytical proof of degeneracy: Constructing a continuous family of LTB models that yield identical $D_A(z)$ but distinct $\mathcal{Q}_\mathcal{D}(t_0)$.
- **4. Implications for Observational Cosmology:** 
  - 4.1 Why priors (e.g., simultaneous bang $t_B(r)=0$) are strictly necessary inputs, not derivable facts.
  - 4.2 The strict boundary between spatial $\mathcal{Q}_\mathcal{D}$ and optical backreaction.
- **5. Conclusion:** Summary of the no-go result and the exact conditions under which $\mathcal{Q}_\mathcal{D}$ *could* be uniquely determined.
- **Appendix A:** Explicit functional derivatives or a worked analytical example (e.g., a perturbative deviation from EdS preserving $D_A$ but altering $\mathcal{Q}_\mathcal{D}$).

### 10. Recommendation: GO
**GO.** The scope is tightly bounded, relies entirely on analytical GR and a strict Degrees of Freedom census (perfectly aligned with the Math Reality Check), and targets a clear, defensible negative result. Underdetermination theorems are high-value contributions in inverse cosmology because they prevent the field from chasing illusory, prior-dependent "measurements." It explicitly avoids numerical fishing expeditions and cannot quietly expand into a software or survey project.
