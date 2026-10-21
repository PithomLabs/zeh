# ZEH-PAPER-SCOPE-1 — Submission

**Method box (standing):** claims tagged [census] / [grammar] / [constitution] / [shield]; status (1) established, (2) derived in this investigation, (3) conditional, (4) conjecture, (5) unsupported/falsified. No numerics executed; no bibliography asserted as final — every literature entry below is a *verification target* with the exact claim to be checked, per the honesty rule. The ZEH-5 submission arrived truncated (cut mid-integrability-condition); that item is carried as an open obligation, not presumed complete.

---

## 1. Executive recommendation (one line)

**GO** — on one theorem: a *constructive, exact, local non-identifiability result* — the map from past-light-cone angular-diameter distance to the slice-defined scalar 𝒬_D(t₀) is not single-valued; there is an explicit one-function family of regular LTB models reproducing any vertex-compatible D_A(z) *exactly*, with 𝒬_D varying along it — with a conditional uniqueness companion under simultaneous bang. Function counting motivates this; the construction below is what could prove it.

## 2. The sharpest candidate proposition [4 — conjectural until obligations close]

**Setting [constitution]:** Λ = 0, dust, gauge M(r) = r³/2 (relabeling freedom fully removed — [census]), central observer (declared, not derived), regular center (E = O(r²), t_B′(0) = 0), expanding branch, no shell crossings, t₀ fixed. Target G(Z) = D_A*(1+z), Z ∈ [1, 2], C², with vertex-compatibility conditions (G(1) = 0, positive low-z slope consistent with the gauge-imposed central orbit — the EdS target satisfies these exactly; a general target imposes finitely many vertex conditions).

**Conclusions sought:**
- **(C1) Family:** a map Ψ from a C¹-neighborhood 𝒰 of u₀ ≡ 1 (where u ≡ √(1+2E), u(0) = 1, u − 1 = O(r²)) into admissible LTB models, such that every Ψ(u) reproduces D_A(z) = G(1+z) **exactly** on [0, 1] — at all orders, not within a tolerance — with Ψ(u₀) = EdS.
- **(C2) Explicitness:** t_B is not an input but an off-cone *output*: t_B(r) = T(r) − τ(r), where τ is the orbit time taking shell r from bang to its light-cone radius. The degeneracy is parametrized by E, with bang time slaved.
- **(C3) Core:** u ↦ 𝒬_D^{Ψ(u)}(t₀; domain of fixed present-day areal radius R_phys) is **non-constant** on 𝒰 — explicit u₁ ≠ u₂, same physical domain, different 𝒬_D.
- **(C4) Discrimination:** the held-out channels H_∥(z)|_cone and ż(z) are non-constant on 𝒰 — distances alone cannot identify the model, but one additional channel can.
- **(C5) Restriction [conditional, highest risk]:** within the subclass t_B ≡ 0, Ψ(u₀) is locally unique — so 𝒬_D becomes well-defined precisely when one structural input is added.

**Why this is the right size:** (C1) formalizes LTB fitting folklore (Mustapha–Hellaby–Ellis-style versatility) as an exact regularity-preserving theorem; (C3) answers the driving question with a *negative result about a specific scalar*, which no fitting-versatility result states; (C5) is the positive companion that makes the negative informative rather than vacuous.

## 3. The scoping calculation that justifies GO [2 — derived this turn]

The benchmark phase left the inverse problem as the on-cone system (E1–E6, EdS-verified). The decisive scoping question: *is the one-function freedom real, or an artifact of counting?* Pen-and-paper closure analysis, with cone state (T, Z, P, Q) = (light-cone time, 1+z, R′, Ṙ′), u(r) input, Rc = G(Z) imposed:

- **Identities:** T′ = −P/u; Z′ = ZQ/u; dRc/dr = P(1 − V/u); dVc/dr = Q + P·r³/(2G²u) (using the exact dust acceleration R̈ = −r³/(2Rc²)); V² = r³/G + u² − 1.
- **Imposing the target** and differentiating it along the cone yields one linear relation (L1) in (P, Q); the ∂_r-of-the-shell-equation yields a second (L2).
- **Key closure check:** differentiating the shell equation *along the cone* and substituting (L1) reproduces (L2) identically — the would-be "extra" consistency condition is **not independent**. The system is therefore 4 equations in 4 unknowns (T, Z, P, Q) **with u(r) a genuine free input**, not a constrained one.
- Degeneracy of the linear solve at the vertex (determinant → 0 as r → 0) is handled by the standard regular-center series; away from the vertex the determinant was already checked nonzero at z = 0.1 in the benchmark phase [2].

**Consequence:** each admissible u drives a well-posed initial-value problem whose solution satisfies the target *identically*; injectivity of u ↦ model is trivial (u determines E). The non-uniqueness is therefore **constructive, not counted** — precisely what the assignment demands. Residual scoping risk is concentrated in two places, flagged honestly: the center-series matching (standard LTB technology, but must be written), and (C3), which is a genuine computation, not a corollary — see §4.

## 4. Obligation ledger — known equations vs. new proof

| # | Obligation | Status of the mathematics | Risk |
|---|---|---|---|
| O1 | Well-posedness of the driven cone system (existence/uniqueness, series at vertex) | New but elementary ODE theory; equations already derived [2] | Low |
| O2 | Realizability: cone state → global model (orbit integration, t_B output); admissibility persistence (1+2E > 0, ρ > 0, R′ > 0) for small amplitude | Elementary — open conditions + continuous dependence | Low |
| O3 | **𝒬₂ functional:** expand 𝒬_D to O(ε²) along Ψ(𝒰); exhibit two profiles with different values. 𝒬_D is intrinsically O(ε²) (variance minus shear is quadratic), so the difference of two members is dominated by 𝒬₂ — no cancellation from higher orders | **New computation — the paper's labor.** Physically a curvature bump deforms H_∥ − H_⊥ on the slice at O(ε), giving nonzero ⟨σ²⟩ at O(ε²); but nonconstancy must be *shown*, and the surprise branch (𝒬₂ ≡ const along the family) would itself be a different, also publishable, result | Medium |
| O4 | Fixed physical domain: r_D(u) from R(t₀, r_D) = R_phys; nonconstancy survives the domain adjustment | Elementary | Low |
| O5 | Linear-response audit: verify against the literature whether the central-observer D_A response to linear LTB perturbations vanishes (candidate sources below). The theorem is exact/nonlinear and does **not** depend on the answer; the answer controls only the narrative (if linear-blind, 𝒬_D — itself O(ε²) — is the *leading* imprint of LTB structure on distances: a strong punchline) and the route to O6 | Literature verification + possible short derivation | Medium |
| O6 | (C5) restricted uniqueness. **Flagged self-audit:** the benchmark phase called this "linearly rigorous"; if O5 confirms linear blindness, a zero linearization *cannot* support an IFT uniqueness argument — that claim is downgraded [5-pending] and uniqueness must come from the direct ODE structure of the t_B-output condition. Fallback: restrict further (e.g., monotone E) or state as conditional | New proof; the riskiest item | High |
| O7 | (C4) held-out variation: P, Q respond to u′ at O(ε) through the O(ε) term 2uu′ in (L2), so H_∥(z) = Q/P responds at linear order even though D_A does not; the drift integral responds through the Z(r) mapping. Small computation | Low |
| O8 | Complete the truncated ZEH-5 integrability condition (bookkeeping; needed for the closure-ansatz remark) | Bookkeeping | Low |

Pre-registered falsifier for the *scope*: if O3 yields 𝒬₂ constant on 𝒰, the non-identifiability theorem dies in its advertised form — re-scope to the (unexpected) invariance theorem or stop.

## 5. Novelty audit (verification plan — no final bibliography asserted)

No live search was executed in this session; the novelty claim is [3 — conditional on the check]. Named closest-prior candidates, what each (probably) proves, and the exact delta:

| Candidate (verify) | What it actually establishes (to verify) | Leaves unresolved | Our delta |
|---|---|---|---|
| Mustapha–Hellaby–Ellis 1997 (MNRAS ~292, 817) | Numerical construction: LTB versatility — fitting prescribed distance (+counts?) data by choosing functions, different gauge/freedom split | No theorem; no exactness/regularity statement; 𝒬_D absent; no uniqueness companion | Exact, regular, constructive family in a fixed gauge; 𝒬_D-specific non-identifiability |
| Zibin 2008 (PRD ~78, 043504); February et al. 2010 (MNRAS) | Central-observer D_L deviations from FLRW arise at second order in LTB contrast | Nothing about 𝒬_D identifiability, no iso-distance family, no restricted uniqueness | Supplies O5 context; our family explains *why* second-order deviations are closure-choice-dependent |
| García-Bellido–Haugbølle 2008 (JCAP); Enqvist–Mattsson 2007 | Restricted-profile fits with t_B = 0 (practice of closing the freedom by hand) | No uniqueness statement; profile ansätze are additional assumptions [constitution] | (C5) is the rigorous version of their closure |
| Reconstruction algorithms & regularity methods (Bolejko–Krasiński–Hellaby–Célérier, CUP volume; related papers) | Algorithms for LTB reconstruction from SN-type data | No identifiability theorem; uniqueness not proved | Theorems, not algorithms — though Ψ doubles as an algorithm for ZEH-6 |
| Quartin–Amendola 2010 (PRD ~81, 103522); Uzan–Clarkson–Ellis 2008 (PRL ~100, 191303) | Drift/kinematic channels distinguish finite-amplitude LTB from FLRW/DE | Not connected to 𝒬_D or to an iso-distance family | (C4) sharpens "drift discriminates" to "drift discriminates *within* the exact iso-distance family" |
| Koksbang (2019–2023, light-cone averaging in exact/numerical models); Heinesen (2021–, effective observables from light-cone data) | Compute effective/observables-backreaction quantities *in* models; rigorous observable definitions | No identifiability theorem for the slice-defined 𝒬_D from cone data | The identifiability question itself |

**Search plan for the 2026 check:** "LTB inverse problem uniqueness"; "bang-time degeneracy"; "identifiability of backreaction from distances"; "Buchert Q_D observability"; author-targeted (Koksbang, Heinesen, Bolejko, Krasiński, Clarkson, Zibin), 2024–2026 windows. **If an identical theorem is found: STOP and re-scope to the smallest delta** (most likely the 𝒬₂ functional or (C5), if absent there).

## 6. Regime, exclusions, and claims the paper will not make

Regime [constitution]: late-time classical GR, dust, Λ = 0 as a synthetic control, z ≤ 1, domains ~10–100 Mpc, comoving dust foliation, fixed t₀. The physical averaging scale is a geometric domain choice — **no RG-flow claim is made anywhere**; nothing reaches the Planck scale, particle content, or the Born rule. **Non-claims:** no Outcome C (the reconstruction, even where unique, is a global inversion restricted to a model class — not a closed local consistency relation; the slice/cone support obstruction stands and is stated as a theorem-shaped negative); no claim that LTB describes our universe; no dark-energy mechanism; no claim that 𝒬_D *causes* acceleration (Flanagan gauge result and Green–Wald suppression cited as context); local-in-amplitude statements only — no global no-go and no global uniqueness.

## 7. Stopping conditions and fallbacks

Stop and re-scope if: (i) the novelty check finds the theorem; (ii) O3 lands on the invariance branch; (iii) O6 fails and no restricted version survives — then the paper's contribution degrades to C1 + C4 + the formalized support obstruction, a methods-rigor note, and the honest recommendation is to shrink, not to inflate. Fallback smallest result: O1 + C1 + the explicit t_B-output map alone, stated as "the exact structure of the LTB distance degeneracy."

## 8. Proposed outline

1. Introduction — the identifiability question; MRC discipline declared.
2. LTB, gauge, admissibility, vertex conditions.
3. The driven on-cone system; closure analysis (§3 above).
4. Theorem 1 (family Ψ: existence, exactness, regularity).
5. Theorem 2 (𝒬_D non-identifiability; the 𝒬₂ functional).
6. Restricted uniqueness under t_B ≡ 0 [conditional].
7. Held-out channels: H_∥ and redshift drift.
8. Relation to prior work (the §5 table, resolved).
9. Discussion: what distances cannot know; the support obstruction as the reason Outcome C fails even here.
Appendices: series expansions; determinant and integrability computations (completing O8).

## 9. Verdict

**GO, conditional:** (a) novelty check clean; (b) a one-page analytic feasibility pass on the 𝒬₂ integrand structure (permitted — it is pen-and-paper, not ZEH-6 numerics). Everything needed for the core is already in the thread's equation inventory; what remains is two genuine proofs (O3, O6) and honest bookkeeping (O1, O2, O4, O7, O8). The paper's one sentence: **the books' slice-side column is not determined by the cone-side column — except when the universe is required to have begun everywhere at once.**

| Claim | Status | Evidence or missing step |
|---|---|---|
| Driven cone system closes with u free | [2] this turn | Closure chain §3; vertex series owed (O1) |
| Exact iso-distance family exists | [4→3] | O1+O2 routine; construction exhibited |
| 𝒬_D non-identifiable from D_A | [4] | O3 computation is the missing step |
| t_B ≡ 0 restores uniqueness | [4], flagged prior overclaim | O6; route depends on O5 verdict |
| Held-out discrimination (drift, H_∥) | [3] | O7 small computation |
| Outcome C (new closed relation) | **Not claimed** [5 as target] | Support obstruction; stated as negative result |
