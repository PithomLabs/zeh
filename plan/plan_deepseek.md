## ZEH-PAPER-SCOPE-1: Literature, Novelty, and Contribution Lock

### Executive verdict

**Revise.** The candidate research question is well-posed and sits in a genuine gap in the literature, but the gap is narrower and more technical than the current framing suggests. The prior work establishes two crucial facts that shape the contribution: (1) \(D_A(z)\) alone does **not** determine the LTB free functions—an infinite class of LTB models fits any isotropic distance-redshift relation; and (2) for central spherical domains, Sussman proved \(Q_{\mathcal D} \le 0\) for elliptic models and \(Q_{\mathcal D} \ge 0\) for hyperbolic models, with the sign fixed by spatial curvature type, not by backreaction dynamics. These results mean the paper cannot claim "observations determine \(Q_{\mathcal D}\)" in general LTB, but they leave open a sharper question: **under what additional conditions does a past-light-cone observable (beyond \(D_A\)) break the degeneracy and fix \(Q_{\mathcal D}(t_0)\)?** The contribution is a conditional identifiability theorem, not a derivation of backreaction from distance data.

---

### 1. Recommended provisional title

**"Identifiability of Buchert Backreaction from Past-Light-Cone Observables in LTB Cosmology: A Conditional Reconstruction Theorem"**

Alternative if the result turns out negative: **"What Past-Light-Cone Data Cannot Determine: Degeneracy of Buchert Backreaction in LTB Dust Models"**

---

### 2. One-sentence primary research question

Under what additional past-light-cone observables beyond \(D_A(z)\)—specifically redshift drift \(\dot z(z)\) or radial expansion \(H_\parallel(z)\)—does the present-day Buchert backreaction \(Q_{\mathcal D}(t_0)\) in a general LTB dust model become uniquely determined, and what is the minimal observable set required?

---

### 3. Research gap, supported by primary literature

Three established results bound the contribution:

**Result 1 (Mustapha–Hellaby–Ellis 1997; MNC 2000).** An infinite class of LTB models fits any isotropic \(D_A(z)\) or \(D_L(z)\) around a central observer. The inverse problem from distance data alone is degenerate. This is confirmed by multiple independent groups.

**Result 2 (Sussman 2008).** For averaging domains containing the symmetry center, \(Q_{\mathcal D}\) has a fixed sign determined by spatial curvature: \(Q_{\mathcal D} \le 0\) for elliptic (positively curved) models and \(Q_{\mathcal D} \ge 0\) for hyperbolic (negatively curved) models. This is a sign constraint, not an identifiability result. It does not link \(Q_{\mathcal D}\) to observables.

**Result 3 (Buchert–van Elst–Heinesen 2022).** A covariant averaging formalism on the past null cone exists, including area-averaged equations for \(D_A\) and redshift drift, but the formalism "identifies additional variables and closure conditions that the equations alone do not fix". No closed relation to spatial \(Q_{\mathcal D}\) is derived.

**What the gap is.** No paper in the primary literature has addressed the joint identifiability question: given \(D_A(z)\) **plus** one additional observable (redshift drift or radial expansion), does \(Q_{\mathcal D}(t_0)\) become uniquely determined in LTB? The closest work is the inverse-problem degeneracy literature (Mustapha–Hellaby–Ellis), which addresses \(D_A\) alone, and Sussman's sign theorem, which addresses \(Q_{\mathcal D}\) alone. The bridge between them—conditional identifiability under additional observables—is unaddressed.

**What the gap is not.** The paper cannot claim that \(D_A\) alone determines \(Q_{\mathcal D}\) (false), that backreaction generates acceleration (Sussman's theorem restricts this), or that observations uniquely determine the LTB model (false without additional data).

---

### 4. One principal candidate contribution

**A conditional identifiability theorem for \(Q_{\mathcal D}(t_0)\).**

Specifically: *In simultaneous-bang LTB with fixed gauge \(M(r) = r^3/2\), the pair \((D_A(z), H_\parallel(z))\) over a finite redshift interval determines \(Q_{\mathcal D}(t_0)\) uniquely if and only if a certain functional equation—derived from the linearized Einstein–Boltzmann system around EdS—has only the trivial solution.*

The theorem is **conditional** on the form of the functional equation and its solution space. It is not a claim that the observables determine the model; it is a claim about the map from observables to a specific functional of the model (the backreaction).

**Why this matters.** If the theorem holds, it converts backreaction from a model-dependent quantity into an observable-determined quantity. If it fails, it establishes a new degeneracy—a negative result that is equally publishable.

---

### 5. Minimum mathematical obligations

**O1. Linearize LTB around EdS.** Derive the linearized shell equation, null geodesic equation, and redshift equation. The shell equation is \(\dot R_1 = -(3t_0^2/2t)R_1 + (3t_0^{2/3}t^{1/3}/2r)e\), with solution \(R_1 = (3t_0^{2/3}/4r)e(r)t^{4/3}\) for regularity at the bang.

**O2. Derive the linearized observables.** Express \(\delta D_A(z)\) and \(\delta H_\parallel(z)\) as functionals of \(e(r)\) and \(\tau(r)\).

**O3. Derive the linearized \(Q_{\mathcal D}\).** Express \(\delta Q_{\mathcal D}(t_0)\) as a functional of \(e(r)\) and \(\tau(r)\) on the domain \(R(t_0, r_{\mathcal D}) = L\).

**O4. Solve the functional equation.** Set \(\delta D_A(z) = 0\) for all \(z \in [0,1]\). This gives a functional equation for \(e(r)\) and \(\tau(r)\). Determine the solution space.

**O5. Impose the second observable.** Set \(\delta H_\parallel(z) = 0\) or use a known nonzero profile. Determine whether the combined system has a unique solution for \(\delta Q_{\mathcal D}(t_0)\).

**O6. Check regularity and domain dependence.** Verify \(1+2E > 0\), \(R' > 0\), positive density, no shell crossing. Check whether the result depends on the domain radius \(L\).

**O7. FLRW limit.** Verify \(Q_{\mathcal D} = 0\) when \(e = \tau = 0\).

**What follows from known equations.** O1–O3 use standard LTB linearization. O4 is the hard step. O5–O7 are checks.

**What requires a new proof.** The solution space of the functional equation in O4. If the equation has nontrivial solutions, the degeneracy is established. If not, uniqueness follows.

---

### 6. Assumptions, regime, scale, domain, foliation, observable set

| Item | Specification |
|---|---|
| **Theory** | Classical GR, \(\Lambda = 0\), \(c = G = 1\) |
| **Matter** | Irrotational pressureless dust |
| **Gauge** | \(M(r) = r^3/2\) |
| **Foliation** | Dust rest frame (Buchert convention) |
| **Domain** | Spherical comoving, central, \(R(t_0, r_{\mathcal D}) = 100\) Mpc |
| **Case A** | General LTB: free functions \(E(r)\), \(t_B(r)\) |
| **Case B** | Simultaneous bang: \(t_B(r) = 0\), free function \(E(r)\) |
| **Primary input** | \(D_A(z)\), \(0 \le z \le 1\) |
| **Secondary input** | \(H_\parallel(z)\) or \(\dot z(z)\) |
| **Target** | \(Q_{\mathcal D}(t_0)\) |

The EdS target \(D_A^*(z) = 2[1-(1+z)^{-1/2}]/(1+z)\) is the reference solution. It is not mandatory for the theorem; it is the control case.

---

### 7. Explicit claims the paper will **not** make

- **No claim** that \(D_A(z)\) alone determines \(Q_{\mathcal D}(t_0)\). Mustapha–Hellaby–Ellis forbids this.
- **No claim** that backreaction generates cosmic acceleration. Sussman's theorem restricts \(Q_{\mathcal D}\)'s sign for central domains.
- **No claim** that LTB is a realistic description of the universe. This is a controlled mathematical laboratory.
- **No claim** that the result extends to non-central domains, Szekeres models, or non-dust matter without proof.
- **No claim** of empirical confirmation. Synthetic-data success is not observational evidence.
- **No claim** that the identifiability theorem is a "new consistency relation" in the sense of Outcome C unless it demonstrably adds predictive content beyond ordinary reconstruction.

---

### 8. Out-of-scope topics and stopping condition

**Out of scope:** Quantum gravity, the cosmological constant problem, the Born rule, particle generation, RG flow, numerical \(N\)-body simulations, CMB analysis, BAO fitting, survey systematics, modified gravity, Szekeres models (unless needed for a counterexample), off-center observers.

**Stopping condition:** If the functional equation in O4 has nontrivial solutions for \(e(r)\) and \(\tau(r)\) that preserve \(D_A(z)\) while yielding materially different \(Q_{\mathcal D}(t_0)\), the paper becomes a negative result: *"Distance Data Cannot Determine Backreaction: A Degeneracy Theorem for LTB."* This is a valid paper.

If the functional equation has only the trivial solution, the paper becomes a positive result: *"Distance Data Plus One Observable Determines Backreaction in Simultaneous-Bang LTB."* This is also a valid paper.

If the functional equation cannot be solved analytically, the paper becomes a partial result with a clearly stated obstruction.

---

### 9. Proposed paper outline

1. **Introduction.** The backreaction identifiability problem. Prior work: Mustapha–Hellaby–Ellis degeneracy, Sussman sign theorem, Buchert past-null-cone formalism. Statement of the gap.
2. **LTB formalism.** Metric, gauge, free functions, Buchert averaging, \(Q_{\mathcal D}\) definition.
3. **Linearization around EdS.** Shell equation, geodesic equation, redshift equation. Derivation of \(\delta D_A\), \(\delta H_\parallel\), \(\delta Q_{\mathcal D}\).
4. **The functional equation.** Derivation from \(\delta D_A = 0\). Analysis of solution space.
5. **Identifiability theorem.** Statement, proof (or counterexample), assumptions, limitations.
6. **Controls.** FLRW limit, domain dependence, regularity.
7. **Discussion.** What the result means for the backreaction program. What additional observables (redshift drift, lensing) would add.
8. **Conclusion.** Conditional identifiability or conditional degeneracy.

---

### 10. Go / revise / stop recommendation

**Revise, then go to ZEH-6.**

The revision: reframe the question from "does \(D_A\) determine \(Q_{\mathcal D}\)?" (already answered negatively by MHE) to "does \(D_A\) **plus one additional observable** determine \(Q_{\mathcal D}\), and what is the minimal observable set?" This is the genuine gap.

**Rationale.** The prior work constrains the question tightly. MHE closes \(D_A\)-alone. Sussman closes the sign of \(Q_{\mathcal D}\) for central domains. What remains open is the joint identifiability question. That question is analytically tractable via linearization, does not require numerical simulation, and can fail cleanly (degeneracy) or succeed cleanly (uniqueness). It is the smallest meaningful mathematical result available.

**What ZEH-6 should do.** Execute O1–O5. Derive the functional equation. Attempt to solve it. If it cannot be solved, characterize the obstruction. Do not run a numerical solver until the functional equation is stated.

**What ZEH-6 should not do.** Claim novelty without comparing to MHE and Sussman. Invent a numerical example. Promote common-metric consistency to a new relation.

---

### Status table

| Claim | Status | Evidence or missing step |
|---|---|---|
| Buchert equations | **Established** | Buchert 2000, 2001 |
| LTB light-cone equations | **Established** | Krasiński 1997; standard null geodesics |
| Sussman sign theorem (\(Q_{\mathcal D} \le 0\), central domains) | **Established** | Sussman 2008, arXiv:0807.1145 |
| MHE degeneracy (\(D_A\) alone) | **Established** | Mustapha–Hellaby–Ellis 1997; MNC 2000 |
| Buchert past-null-cone formalism | **Established** | Buchert–van Elst–Heinesen 2022, arXiv:2202.10798 |
| \(D_A\) alone determines \(Q_{\mathcal D}\) | **Falsified** | MHE degeneracy |
| \(D_A\) + one observable determines \(Q_{\mathcal D}\) | **Open** | Functional equation O4 unsolved |
| New relation with additional predictive content | **Not derived** | Conditional on O4–O5 |
