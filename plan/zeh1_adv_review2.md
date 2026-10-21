## claude

Still working: I've pulled the relevant sections from the reality check (about 12,000 lines across 15 maps) and am assembling the answer now.

**Short answer:** In form, yes. As an established result, no, and the reality check is specific about where it breaks. It has no entry at all on the cosmic web, inhomogeneity, averaging or backreaction, so that leg is extrapolation.

| Ingredient | What the reality check supports | Status |
|---|---|---|
| **Global constraints** | The Bianchi identity forces ∇T = 0 as a consistency theorem (calculus map). Constraints remove 8 of the metric's 10 components (degrees-of-freedom map). ADM mass links local fields to global charge via Stokes. | Strong, but these are identities, not selectors. The Stokes route needs an asymptotic boundary, and the duality and complexity maps list boundaryless closed universes as out of scope. A fully constrained system has no external clock. |
| **Cosmic web** | Not covered. The nearest entries are emergence (coarse-grained fluid dynamics), chaos (cascades) and geometry (FLRW as the homogeneous idealization). | Untested |
| **Causal boundaries** | Causal structure needs a Lorentzian metric (geometry map). Topology cannot supply it, and Lorentzian topology change is forbidden. The de Sitter horizon entropy S = A/4G is confirmed. Jacobson derives the Einstein equations from the Clausius relation on local causal horizons. | Confirmed for the static patch. Partial for an expanding universe: the horizon is observer-dependent, there is no global heat bath, and the dictionary is unresolved. |

**What a valid restriction would have to look like, by the document's own rules**

1. **It must be an inequality, not a value.** Every map answers NO on the cosmological constant, initial conditions and signature, and the geometry map calls geometry "permissive, not selective." The confirmed horizon results are all bounds: Bekenstein, area-law capacity, and the chaos bound λ ≤ 2πk_BT/ħ.
2. **It must be carried by native structure.** For global constraints that means the Bianchi identity or Hamiltonian constraint, and for causal boundaries it means the metric. Topology cannot carry it, because it is silent on shape and scale. The web's Betti numbers or genus therefore cannot restrict the expansion history. The web's topology also evolves as voids merge, so it has no protected invariant. The topology map would class "topological" here as language, because it only names network structure.
3. **The scale separation must be sharp.** The emergence map says coarse-grained laws are testable only where scales separate cleanly. The cosmic web sits in the nonlinear transition between background and structure, where the averaging scale is a choice.

**Where it breaks**

- **The horizon leg is the weak link.** The entropy, complexity, duality and emergence maps all label the cosmological horizon PARTIAL. Any bound built on it inherits that ambiguity, so it would be conditional on which horizon is used (event or apparent).
- **Constraints don't become boundary charges.** With no asymptotic boundary, the global constraint is just the Hamiltonian constraint on a slice, the Friedmann-type relation already in use. New content would have to come from the inhomogeneous correction, which is the part the reality check never examines.
- **Any bound constrains but does not select.** Even a successful restriction would not fix Λ or the initial state.

**Candidate shape (outside the reality check)**

The closest known form is a generalized-second-law-type inequality, in which horizon area growth plus the coarse-grained entropy of structure cannot decrease. That would tie the expansion history to structure-formation entropy. The better-grounded route is Jacobson's local horizons, which exist at every point and avoid the global-horizon ambiguity. The global horizon would then be an output, not an input. A theory with a preferred slicing, such as a constant-mean-curvature (York-time) foliation, would also supply the missing clock.

**Verdict:** PARTIALLY APPLICABLE, untested. The reality check shows what shape the restriction must take: an inequality, carried by the constraint and horizon structure, not by topology. It does not show that one exists.


## Meta

That framing is the right sharpening, and it survives the reality check if we keep each math map in its lane.

Your file forces this: no map fixes $\Lambda$, initial $f_v$, or the horizon size from first principles. That is the Graveyard result for algebra, calculus, geometry, topology, invariants, symmetry, entropy. What they *do* give is a consistency relation between observables at the same scale. That is where your bulk-to-boundary idea becomes testable.

### Grounding per reality_check.md

**Where they shine here:**

* **Symmetry / Invariants:** Noether second theorem -> Hamiltonian constraint ${\cal H}\approx0$. Invariants shine as grammar: $dQ/dt=0 \iff [Q,H]=0$. [invariants.md Shines 1] This gives $3H_{\cal D}^2 = 8\pi G\langle\rho\rangle_{\cal D}+\Lambda-\frac12\langle R\rangle_{\cal D}-\frac12 Q_{\cal D}$. Exact, but does NOT select $\Lambda$ or initial $\langle R\rangle$. [symmetry.md Graveyard 7]

* **Calculus:** shines as engine of motion. Raychaudhuri $\dot\theta=-\frac13\theta^2-2\sigma^2-4\pi G\rho$, and Buchert averaging non-commutation $\partial_t\langle f\rangle-\langle\dot f\rangle=\langle f\theta\rangle-\langle f\rangle\langle\theta\rangle$. Gives integrability $\dot Q+6HQ+\dot{\langle R\rangle}+2H\langle R\rangle=0$. [calculus.md Shines 1,5] Calculus does NOT select initial $Q$ or $f_v$. [calculus.md Graveyard 1]

* **Geometry:** shines as stage and force: null geodesics, area distance $D_A$, redshift drift. $G_{\mu\nu}=8\pi G T_{\mu\nu}$ is geometry as gravity. [geometry.md Shines 1] Geometry does NOT fix initial topology or $\Lambda$. [geometry.md Graveyard 3]

* **Topology:** shines as classification: voids as stable underdense defects $\pi_n\neq0$, light cone as topological sector, apparent horizon as marginally trapped surface. Topology does NOT generate metric size or dynamics. [topology.md Shines 2, Graveyard 1,5]

* **Entropy:** shines as counting and area law $S=A/4G$. [entropy.md Shines 4] Does NOT generate dynamics or select low-entropy start. [entropy.md Graveyard 1,2]

* **Emergence / Degrees of freedom:** shine as autonomy of scales. EFT at scale $L$: $S_{eff}[\phi_{low}]=\int D\phi_{high}e^{iS}$. $f_v$, $H_v-H_m$ are DOF counts at $L\sim100$ Mpc. Emergence does NOT fix couplings. [emergence.md Shines 3]

### Why your 3-ingredient construction is the correct one

**1. Spatial constraint must respond to web - allowed**

Buchert formalism is calculus + invariants where they shine. $Q_{\cal D}$ is variance of expansion, $\langle R\rangle_{\cal D}$ is curvature. Both enter averaged expansion. You do not need hidden contraction elsewhere. You need $Q_{\cal D}(L)$ at scale $L$. Value of $Q_{\cal D}$ is boundary data, not derived.

**2. Same spacetime must determine causal boundary - allowed, but past light cone only**

Buchert-van Elst-Heinesen light-cone averaging gives area-averaged constraint on past null cone including optical backreaction. Geometry shines as light propagation, calculus shines as Sachs equations for $D_A$. This is concrete.

Future event horizon is different. As you note, it depends on entire future $a(t)$ and cannot be inferred model-independently. Per invariants check, Hamiltonian constraint is not proof of global zero-energy without specific definition and boundary conditions. Treating future horizon as energy reservoir would violate Graveyard: invariants do NOT generate energy. Use apparent / quasi-local horizon measured from $D_A(z)$ and $H(z)$, not future horizon.

**3. Connection must restrict observations - this is the new measurable**

The hard part you identified is exact: spatial averages $\langle\cdot\rangle_{\cal D}$ and null averages $\langle\cdot\rangle_{lightcone}$ are not interchangeable. Emergence says each has its own EFT. RG connects them but does not fix free functions.

Therefore the only restriction that survives reality check is a consistency relation, not a value prediction:

If a model claims $Q_{\cal D}$ changes $H_{\cal D}$, then with same $\langle\rho\rangle$, $\langle R\rangle$, $Q$ it must predict $D_A(z)$, $H(z)$, redshift drift $\dot z(z)$, lensing $k(z)$ from same solution, not by inserting $a_{\cal D}$ into FLRW formulas.

Heinesen-Clifton Oct 7 2026 null test in Phys Rev D is exactly this class: FLRW predicts $C(z)=1+H^2(D D''-D'^2)+H H' D D'=0$ etc. Non-FLRW gives $C(z)\neq0$. Your extension: derive $C_{web}(z)=F[Q_{\cal D},\langle R\rangle_{\cal D}, f_v]$ with fewer free functions than observables.

Per file: invariants shine as Rosetta Stone for dualities $Z_{CFT}=Z_{grav}$, here $Z_{spatial}=Z_{null}$ must match if same spacetime. That match is testable, but does NOT predict $\Lambda$ number.

### Research verdict per file

**Mathematically plausible:** GR provides constraints, Buchert gives spatial, light-cone formalism gives null. Calculus and geometry shine here.

**Not yet established:** No demonstrated theorem unifies $Q_{\cal D}$ to $D_A(z)$ evolution without extra closure assumptions. Closure is boundary data, which calculus does NOT select.

**Concrete target:** Derive closed relation between spatial backreaction measured from $f_v$, $H_v-H_m$, $\langle\sigma^2\rangle$ and null observables $D_A(z)$, $H(z)$, $\dot z$. Measure both sides with DESI/Euclid voids + SNe/BAO. Violation falsifies model even if $H(z)$ alone fits.

Unimodular version respects check: $\Lambda$ becomes integration constant conjugate to $V_4$, $\{\Lambda,V_4\}=8\pi G$, so $V_4$ fixed means void volume gain must be wall volume loss, but $\Lambda$ value remains input, not derived, satisfying all Graveyards that say no map fixes $\Lambda$.

The ledger is therefore not expansion vs hidden contraction elsewhere in space, but bulk variance vs boundary area at same scale, with total $H_{tot}=H_{bulk}+H_{boundary}\approx0$ as constraint, not as energy creation.
