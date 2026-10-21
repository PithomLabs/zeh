# ZEH/LTB Identifiability in Phys Pseudo

**Working title of the investigation:** *Spatial Backreaction and Light-Cone
Observables in LTB Cosmology: An Identifiability Analysis.*

---

## 0. Scope, sources, and how to read this document

### 0.1 What this document is

This is an **exploratory mathematical reasoning and adversarial review
document**. It uses the Phys Pseudo language (seven constructs, `PSEUDO.md`) to
express the reasoning behind the ZEH/LTB identifiability investigation, and then
applies the Math Reality Check protocol (`MRC_REVIEW_PROTOCOL.md`) to that
reasoning.

It is **not** an implementation handoff, not a specification for a Go
derivation, and not a proof of anything. It does not settle the central
conjecture. The claim register's open status is preserved exactly as the source
records it.

Per `PSEUDO.md` §7, representing a proposition here does not endorse it, and
every statement below is open to the review in §10. The document deliberately
exposes what the argument establishes, where its premises are insufficient, and
what remains to be done.

### 0.2 Sources actually read

| Source | Role in this document |
|---|---|
| `phys-pseudo/AGENTS.md`, `../AGENTS.md`, `phys-system/AGENTS.md` | workspace and package operating rules; instruction hierarchy |
| `phys-pseudo/PSEUDO.md` | **sole authority** for language syntax and meaning |
| `phys-pseudo/MRC_REVIEW_PROTOCOL.md` | the review method applied in §10 |
| `phys-pseudo/CONVENTIONS.md` | historical pointer only; used as such |
| `phys-pseudo/README.md` | scope and intended use |
| `phys-pseudo/plan/reality_check.md` | advisory only; consulted, not applied as a gate |
| `phys-lib/gr/ltb/README.md`, `doc.go` | package scope, status discipline, claim register in prose |
| `phys-lib/gr/ltb/fixture.go` | the seven assumption seeds; the executed fragment; the cone and vertex constructions; `Verify()` |
| `phys-lib/gr/ltb/claim.go` | `ClaimStatus`, `CheckClaimPromotion` and its documented limits |
| `phys-lib/gr/ltb/manifest.json` | machine metadata: regime, conventions, executed vs represented-only, limitations |
| `phys-lib/gr/ltb/research_metadata.json` | target, domain, the four claim entries, obligations O1–O7, literature list |
| `phys-lib/gr/ltb/manifest_test.go` | what the metadata tests actually pin |
| `phys-lib/gr/ltb/protocol/derivation_test.go` | what the protocol tests actually establish |
| `phys-math/rules.go`, `ast.go`, `apply.go`, `operator.go` | semantics of `DIFFERENTIATE-001`, `EXPR-CANON-001`, `Canonicalize`, node tags |
| `zeh/README.md`, `zeh/plan/README.md` | the supplied reference (identical content in both) |
| `zeh/plan/plan2_z.md` | the research-lead plan named in `research_metadata.json`'s `provenance_note`; source of the metric, the cone system, the vertex relations, the `Q_2` response, and the two open lemmas |

**Limitations of the source set.** `phys-lib/gr/ltb` contains **no**
package-local `AGENTS.md`; its local instructions are `README.md`, `doc.go` and
`manifest.json`. The Phys artifacts contain **no** `Q_D` artifact, **no**
spatial-averaging primitive, **no** volume measure, **no** cone-system artifact,
and **no** definition of `beta`. `MHE 1997` and `Buchert 2000` were **not read**
for this document. No Go code was built, run, or replayed while producing this
document; every claim about "executed" work is a report *about* the supplied
workflow, attributed as such.

### 0.3 Attribution convention used throughout

Because `PSEUDO.md` has no provenance syntax, the following tags appear in
ordinary prose and `#` comments only:

- **(supplied)** — transcribed from `zeh/README.md` / `zeh/plan/plan2_z.md`;
  not re-derived here.
- **(fixture)** — read off the live code in `phys-lib/gr/ltb`.
- **(rule)** — read off `phys-math` rule semantics.
- **(reconstructed)** — derived in this document, independently, from stated
  premises.
- **(reported)** — an execution claim made *by* the supplied workflow; not
  certified here.

Statuses such as `literature-claim-requiring-verification`,
`candidate-construction-incomplete`, `open-conjecture` and `deferred` are
**metadata strings** in `research_metadata.json` and `claim.go`. They are
reproduced below as attributed prose. They are not language constructs and carry
no truth value.

---

## 1. Inputs: regime, conventions, assumptions, cited material

```text
# --- 1. Inputs ---------------------------------------------------------------
# Assumption descriptions are transcribed from the seven seeds in
# phys-lib/gr/ltb/fixture.go (Build), and from manifest.json "conventions".
# The fixture's own category labels appear in the trailing comments; they are
# metadata, not language constructs.

define r := the comoving radial coordinate, the single bound parameter declared by the fixture's function/1
define M := the radial gauge function M(r) = r^3/2 exactly, that is (1/2)*r^3 with integer exponent 3
define Rphys := the fixed physical areal radius of the comoving domain at t0, so that R(t0, rD) = Rphys
    ? no numerical value for Rphys appears in any accessible Phys artifact; the fixture and research_metadata.json write the symbol "Rphys" only, and the value 0.0233 that the research plan uses is not carried by the artifacts, so the domain over which Q_D is to be compared is not numerically fixed by the accessible material

assume a_gauge: the radial gauge is fixed exactly as M(r) = r^3/2, not r^(3/2); this removes the relabeling freedom r -> r~(r)
assume a_regime: late-time classical GR, irrotational pressureless dust, Lambda = 0, units c = G = H0 = 1
assume a_observer: central observer with comoving synchronous dust foliation; all beams through the vertex are radial
assume a_regularity: regular center, 1 + 2E > 0, R' > 0, rho > 0, no shell crossings over the stated domain and interval
assume a_domain: the domain is a spherical comoving domain with fixed physical boundary R(t0, rD) = Rphys, and rD is recomputed per model
assume a_central_norm: central normalization R'(t0, 0) = 1 with shared observer event t0 = 2/3; a load-bearing constitution, not a derived result
```

**Distinguishing the roles of the conventions** (the task requires this
explicitly):

| Statement | Role | Where it lives |
|---|---|---|
| `M(r) = r^3/2` | **Meaning of a symbol** — what the function `M` is | `define M` |
| "the radial coordinate *is fixed by* that `M`" | **Chosen convention (gauge)** — a premise, not a fact about Nature | `assume a_gauge` |
| `R = D_A` on the central cone | **Input convention (reading of the observable)** — how the measured quantity is read | `assume a_target_reading` below |
| `R'(t0,0) = 1`, `t0 = 2/3` | **Declared normalization / constitution** — adopted, explicitly *not derived* | `assume a_central_norm` |
| `D_A*(z) = 2[1-(1+z)^(-1/2)]/(1+z)` | **Input data** (a fixed observation) | `given observation` below |

```text
# --- 1b. The observation, the cited material, and the geometric background ---

given observation: the fixed past-light-cone distance observation is the function D_A*(z) = 2[1 - (1+z)^(-1/2)]/(1+z) on 0 <= z <= 1
assume a_target_reading: on the central cone the observed quantity is read as the area radius itself, R = D_A, and not as the rescaled G(Z)

given ltb_metric: the LTB dust background is ds^2 = -dt^2 + R'(t,r)^2/(1+2E(r)) dr^2 + R^2 dOmega^2, with R-dot^2 = r^3/R + u^2 - 1, u = sqrt(1+2E), and rho = 3r^2/(2 * 4 pi R^2 R')
    ? (supplied, plan2_z.md section 3, itself citing Lemaître 1933, Tolman 1934, Bondi 1947) the metric and orbit equations are transcribed, not re-derived here, and the cited primaries were not read; re-deriving the orbit equation and the density formula from the field equations would be the evidence that closes this
given buchert_qd: the Buchert averaging formalism and the definition Q_D = (2/3)(<theta^2> - <theta>^2) - 2<sigma^2>, with the average taken over the comoving domain with the proper-volume measure, are cited background (Buchert 2000)
    ? (fixture) the averaging operation and its volume measure are recorded in the fixture as represented only; no executable primitive exists in this slice, so every use of Q_D below is a formula-level statement and not a computed value
```

---

## 2. The question and the identifiability criterion

The question: **given an admissible LTB model class and a fixed past-light-cone
distance observation, what does that observation determine about present-day
Buchert backreaction `Q_D(t0)` on a specified comoving domain?**

The criterion (supplied, `zeh/README.md`): backreaction is identifiable exactly
when the set of values attained over the constrained class is a singleton.

```text
# --- 2. The criterion ---------------------------------------------------------

define admissible_class := the LTB dust models M satisfying a_gauge, a_regime, a_observer, a_regularity, a_domain and a_central_norm
    ? the accessible artifacts state these seven assumptions only as prose descriptions; the metric ansatz, the shell-age relation, the solution regularity class, and the boundary data that determine rD are not written down, so membership in admissible_class cannot be checked from the supplied files; a written definition of the class would resolve this
define Qset := { Q_D^M(t0) : M in admissible_class and the past-light-cone distance function of M equals observation }
    ? treating Qset as a set of values requires that the constrained class is a set of models and that the map M -> Q_D^M(t0) has this image; neither is checkable until admissible_class is specified, and the else-branch of the case split below presupposes the same set semantics
define identifiable := the case in which Qset contains exactly one value

if Qset is a singleton:
    then
        derive branch_identified: every M in admissible_class whose distance function equals observation has one and the same value of Q_D(t0), namely the unique element of Qset, from [Qset, admissible_class, observation] | a singleton set has exactly one element, and every element of Qset is Q_D^M(t0) for some constrained M
    else
        derive branch_not_identified: there are M1 and M2 in admissible_class, both with distance function equal to observation, such that Q_D^(M1)(t0) != Q_D^(M2)(t0), from [Qset, admissible_class, observation] | a set that is not a singleton has two distinct elements, and each element of Qset is attained by some constrained M

derive criterion_is_singleton: the observation determines Q_D(t0) over admissible_class exactly when Qset is a singleton, which is the condition called identifiable, from [Qset, identifiable, admissible_class, observation] | substituting the right-hand side of the definition of identifiable into the condition gives the equivalence
```

**Three things this criterion is not.** They are stated here because the
distinction is the whole point of the exercise:

1. It is **not** the statement that a particular model produces a particular
   value. Exhibiting one admissible model with one value of `Q_D` says nothing
   about whether `Qset` is a singleton (§9.6).
2. It is **not** a statement that the model is "underdetermined".
   Underdetermination is a *vague* property; the singleton criterion is exact
   and decidable for a specified class.
3. It is **not** a property of the observation alone. It is a property of the
   *pair* (observation, class). See §10, finding `rv_class_relativity`.

```text
# --- 2b. The physical conjecture, which is stronger than the criterion ---------

claim zeh_q03: there exist two admissible LTB models M1 and M2 with identical past-light-cone distance functions equal to observation on 0 <= z <= 1, and with Q_D^(M1)(t0) != Q_D^(M2)(t0) on the same physical domain R(t0, rD) = Rphys
    ? no theorem artifact exists for this proposition and the register records it with the status string "open-conjecture"; the decisive missing ingredient is a nonzero Q_2[h] for an admissible profile under the exact observation constraint (obligation o4), and the proposition would be resolved either by constructing such an admissible pair with distinct Q_D, or by establishing that Q_D(t0) is in fact determined over the intended class
```

---

## 3. Reconstruction A — the target distance series

The supplied reference gives a binomial expansion, a numerator, and a division
by `1+z`, and reports that the third coefficient `19/8` corrects an earlier
`23/8` slip. The point of this section is to *show the dependency* rather than
to assert the corrected value.

```text
# --- 3. The target series D_A*(z) ---------------------------------------------

given binomial_half: the binomial series (1+z)^(-1/2) = 1 - z/2 + 3z^2/8 - 5z^3/16 + O(z^4) for |z| < 1
given geometric_recip: the geometric series (1+z)^(-1) = 1 - z + z^2 - z^3 + O(z^4) for |z| < 1

derive numerator_series: 2[1 - (1+z)^(-1/2)] = z - 3z^2/4 + 5z^3/8 + O(z^4) from [binomial_half] | subtracting the binomial series from 1 gives z/2 - 3z^2/8 + 5z^3/16, and multiplying by 2 gives z - 3z^2/4 + 5z^3/8
derive coeff_order1: the coefficient of z in D_A*(z) is 1 from [numerator_series, geometric_recip] | the only product of total order 1 is (z)(1) = z
derive coeff_order2: the coefficient of z^2 in D_A*(z) is -7/4 from [numerator_series, geometric_recip, coeff_order1] | the order-2 products are (z)(-z) = -z^2 and (-3z^2/4)(1) = -3z^2/4, summing to -7z^2/4
derive coeff_order3: the coefficient of z^3 in D_A*(z) is 19/8 from [numerator_series, geometric_recip, coeff_order2] | the order-3 products are (z)(z^2) = z^3, (-3z^2/4)(-z) = 3z^3/4 and (5z^3/8)(1) = 5z^3/8, summing to (8 + 6 + 5)z^3/8 = 19z^3/8
derive da_series: D_A*(z) = z - 7z^2/4 + 19z^3/8 + O(z^4) from [coeff_order1, coeff_order2, coeff_order3] | the three coefficients are exactly the coefficients of the Cauchy product of numerator_series and geometric_recip
```

**A second, independent route to the same coefficient** — the composition check
the source reports. It needs the EdS cone profile of §4, and is placed there.

---

## 4. Reconstruction B — the EdS vertex profile, the vertex normalization, and the composition check

```text
# --- 4. The EdS baseline ------------------------------------------------------
# The five cone expressions below are the ones the fixture constructs and stores
# (fixture.go: ConeRefs["u"], ["V0"], ["Q0"], ["Rc0"], ["P0"]); the EdS cone
# solution Z_0 and R_{c,0} is supplied (plan2_z.md section 4.3).

define cone_u := 1 - r/2
define cone_V0 := r / cone_u
define cone_Q0 := 1 / cone_u
define cone_Rc0 := r * cone_u^2
define cone_P0 := cone_u^2
define eds_Z0 := (1 - r/2)^(-2)
define eds_z := eds_Z0 - 1

given binomial_neg2: the binomial series (1 - x)^(-2) = sum over n >= 0 of (n+1) x^n, for |x| < 1

derive eds_Z0_expansion: eds_Z0 = 1 + r + 3r^2/4 + r^3/2 + O(r^4) from [eds_Z0, binomial_neg2] | substituting x = r/2 gives 1 + 2(r/2) + 3(r/2)^2 + 4(r/2)^3 = 1 + r + 3r^2/4 + r^3/2
derive eds_z_expansion: eds_z = r + 3r^2/4 + r^3/2 + O(r^4) from [eds_Z0_expansion] | subtracting the constant term
derive vertex_coefficients: the coefficients of eds_z are z_1 = 1, z_2 = 3/4 and z_3 = 1/2 from [eds_z_expansion] | reading off the three displayed orders
derive eds_Z0_convergence: the series for eds_Z0 about r = 0 converges for |r| < 2 from [eds_Z0, binomial_neg2] | the nearest singularity of (1 - r/2)^(-2) is the pole at r = 2
```

### 4.1 The composition check (the "caught the 23/8 slip" control)

On the central cone the observed area distance *is* the area radius
(`a_target_reading`), so in the EdS baseline the composition `D_A*(z(r))` must
reproduce `R_{c,0}(r) = r(1 - r/2)^2` exactly. This is an independent check on
the `z^3` coefficient.

```text
# --- 4.1. The composition check ------------------------------------------------

derive composition_expansion: D_A*(eds_z(r)) = r - r^2 + r^3/4 + O(r^4) from [da_series, eds_z_expansion] | substituting eds_z = r + 3r^2/4 + r^3/2 into D_A*(z) = z - 7z^2/4 + 19z^3/8, with eds_z^2 = r^2 + 3r^3/2 and eds_z^3 = r^3, gives r + (3/4 - 7/4)r^2 + (1/2 - 21/8 + 19/8)r^3 = r - r^2 + r^3/4
derive composition_matches_cone: D_A*(eds_z(r)) agrees with cone_Rc0 through the orders checked from [composition_expansion, cone_Rc0, a_target_reading] | cone_Rc0 = r(1 - r/2)^2 = r - r^2 + r^3/4, and on the cone the area distance is the area radius
derive refutes_23_8: the third coefficient of D_A* is 19/8 and the value 23/8 is inconsistent with the EdS cone composition, from [composition_expansion, da_series] | replacing 19/8 by 23/8 in the composition changes the r^3 coefficient to 1/2 - 21/8 + 23/8 = 3/4, whereas the exact composition requires 1/4
```

**Independent corroboration of the refutation.** The `23/8` value also fails the
direct multiplication: `d_3 = n_3 - d_2` forces `n_3 = 23/8 + d_2 = 23/8 - 14/8
= 9/8`, i.e. a binomial coefficient of `-9/16` where the binomial series gives
`-5/16`. The two routes are independent: one uses the algebraic structure of the
binomial series, the other uses the exact geometry of the EdS cone.

**Scope limit.** The composition check is conditional on the EdS cone solution
being correct, and on the target being the EdS area distance by construction —
which it is, since `D_A*(z)` is derived from the EdS model with `H_loc(t0) = 1`
(`zeh/plan/plan2_z.md` §3). It is a consistency check on the *coefficient*, not
an independent derivation of the target's physical meaning.

### 4.2 The vertex normalization and its branch

```text
# --- 4.2. The vertex relations -------------------------------------------------
# (supplied, plan2_z.md section 5) a_0 := R'(t0, 0); the source derives the
# central relation a_0^2 = 1/a_0 + 2E_2 and a cone r^1-match relation that it
# calls "identical" to the first, and then states that the match is "not
# independent" of the central dynamics.

given vertex_relations: for a model reproducing the target near the vertex, with a_0 = R'(t0, 0) and E(r) = E_2 r^2 + E_4 r^4 + ..., the central relation is a_0^2 = 1/a_0 + 2E_2; the target composition is written as A_1 - z_2 = -7/4 with A_1 = -a_0^2; and R_c(r) = a_0 r - a_0^2 r^2 + O(r^3)
    ? (supplied) the two vertex relations are presented as two and then, in the same paragraph, as one; the displayed form of the composition uses A_1 - z_2 = -7/4, which holds only when z_1 = 1, and z_1 = a_0 by the r^1 match, so the general composition is A_1 = z_2 - (7/4) z_1^2 and the general form of z_2 is (3/4) a_0^2; and no relation is displayed that would fix a_0 without the declared normalization, so the second branch reported below cannot be re-derived; writing the r^1 and r^2 coefficient matches with their own algebra, and displaying the branch equation, would resolve this

derive vertex_E2_zero: with a_0 = 1 the central relation gives E_2 = 0, from [vertex_relations, a_central_norm] | substituting a_0 = 1 gives 1 = 1 + 2E_2
derive vertex_z2: with a_0 = 1 the target composition gives z_2 = 3/4, from [vertex_relations, a_central_norm] | z_2 = 7/4 - a_0^2 = 7/4 - 1 = 3/4
derive vertex_z2_agrees: the derived z_2 agrees with the EdS profile coefficient, from [vertex_z2, vertex_coefficients] | vertex_coefficients gives z_2 = 3/4, and vertex_z2 gives 3/4

if a_central_norm is not imposed:
    then
        claim vertex_second_branch: the vertex system admits a further branch with a_0 = (sqrt(15) - 3)/6 and E_2 approximately -3.4
            ? (supplied) the source reports this branch and states that its global admissibility was not examined, but it never displays the branch equation; the stated a_0 is the positive root of 6 a_0^2 + 6 a_0 - 1 = 0, and at least two different candidate relations give an E_2 that rounds to -3.4, so the reported number does not identify the relation; displaying the branch equation would resolve this
    else
        derive vertex_branch_primary: the vertex relations are used with a_0 = 1 and give E_2 = 0 and z_2 = 3/4, from [vertex_relations, a_central_norm] | as in vertex_E2_zero and vertex_z2
```

**Reading.** The constitution `a_0 = 1` is *declared*, and the source's own
remark is that the data fix one fewer quantity than the class assumes. That
observation survives this review. What does **not** survive is the advertised
"two independent relations": the source itself withdraws the independence in the
next sentence, and the general `z_2` formula used in the branch discussion
appears to be the `a_0 = 1` special case. See §10, finding `rv_general_composition`.

### 4.3 The candidate recursion in `beta`

```text
# --- 4.3. The candidate recursion ----------------------------------------------
# (supplied, plan2_z.md section 6) the plan writes u = 1 + beta r^4 + gamma r^6 + ...
# after E_2 = 0 is forced, and the recursion z_3 = 1/2 + (2/3) beta.

define beta := the coefficient of r^4 in the even expansion u(r) = 1 + beta r^4 + gamma r^6 + ... of u = sqrt(1 + 2E), which parametrizes the family once the r^2 coefficient of u has been fixed to zero
    ? beta has no definition in any accessible Phys artifact; fixture.go, manifest.json and research_metadata.json do not mention it, so the definition used here comes from the research plan alone and the candidate recursion cannot be checked against any stored artifact

claim candidate_recursion: for the cone family with u = 1 + beta r^4 + ..., the coefficient z_3 of the cone redshift profile satisfies z_3 = 1/2 + (2/3) beta
    ? (supplied) the source records this as a candidate recursion, not as a certified result, and the fixture stores no artifact for it; a derivation of the recursion from the cone system, or a second evaluation at beta != 0, would resolve this
derive candidate_recursion_beta0: at beta = 0 the candidate recursion gives z_3 = 1/2, in agreement with the independently computed EdS value, from [candidate_recursion, vertex_coefficients] | substituting beta = 0 gives 1/2 + 0 = 1/2, and vertex_coefficients gives z_3 = 1/2
```

**Scope limit, stated here rather than left implicit.** Agreement at `beta = 0`
does not discriminate the candidate from any other relation that agrees there.
The stored `z_3 = 1/2` is a *finite-order baseline*; it is consistent with the
candidate and with infinitely many alternatives. Nothing in the accessible
material distinguishes them, and the fixture's own documentation says the same.

---

## 5. Reconstruction C — the EdS cone identity and its domain

This is the case where the supplied assertion needs the most careful reading.
The reference states the identity and then says it "holds identically for
`u != 0`". The displayed expressions, however, have a *second* denominator that
vanishes at `r = 0`.

```text
# --- 5. The EdS cone identity -------------------------------------------------

derive cone_lhs: 2 * cone_V0 * cone_Q0 = 2r/cone_u^2, defined exactly where cone_u != 0, from [cone_V0, cone_Q0] | (r/cone_u)(1/cone_u) = r/cone_u^2, and the product is defined exactly when cone_u does not vanish
derive cone_rhs: 3r^2/cone_Rc0 - r^3*cone_P0/cone_Rc0^2 = 3r/cone_u^2 - r/cone_u^2 = 2r/cone_u^2, defined exactly where r != 0 and cone_u != 0, from [cone_Rc0, cone_P0] | 3r^2/(r u^2) = 3r/cone_u^2 and r^3 u^2/(r^2 u^4) = r/cone_u^2, and both divisions require the divisor r u^2 to be nonzero
derive cone_identity: 2 * cone_V0 * cone_Q0 = 3r^2/cone_Rc0 - r^3*cone_P0/cone_Rc0^2 for every r with r != 0 and cone_u != 0, from [cone_lhs, cone_rhs] | both sides are the single expression 2r/cone_u^2
```

**The domain, checked point by point rather than by simplification.**

```text
derive cone_undefined_at_r0: the displayed cone identity is undefined at r = 0, even though cone_u = 1 != 0 there, from [cone_Rc0, cone_V0, cone_Q0] | cone_Rc0 = r cone_u^2 vanishes at r = 0, so 3r^2/cone_Rc0 and r^3*cone_P0/cone_Rc0^2 are 0/0, while 2*cone_V0*cone_Q0 is defined and equals 0
derive cone_undefined_at_r2: the displayed cone identity is undefined at r = 2, where cone_u = 0, from [cone_u, cone_V0, cone_Rc0] | cone_V0 and cone_Q0 divide by cone_u, and cone_Rc0 vanishes, so every term of the displayed identity is undefined
derive cone_pole_at_r2: the identity admits no finite continuous extension across r = 2, from [cone_lhs] | 2r/cone_u^2 tends to +infinity as cone_u = 1 - r/2 tends to zero
derive cone_extends_at_r0: the identity does admit a continuous extension to r = 0, with both sides equal to 0 there, from [cone_identity, cone_lhs, cone_undefined_at_r0] | for r != 0 both sides are the one function 2r/cone_u^2, whose limit as r tends to 0 is 0 because cone_u tends to 1; the left side is already defined at r = 0 and equals 0 there
derive r2_outside_admissible: r = 2 is excluded by the regularity requirement, from [cone_u, a_regularity] | cone_u = 0 at r = 2 gives 1 + 2E = cone_u^2 = 0, which violates 1 + 2E > 0
```

**Assessment of the supplied assertion.** The reference's sentence "holds
identically for `u != 0`" is **true as a statement about the simplified rational
function** `2r/u^2`, and **false as a statement about the displayed formula**,
which is undefined at `r = 0`. The failure is in the display, not in the
algebra. The distinction is not cosmetic: the simplification `r^2/(r u^2) = r/u^2`
cancels a factor of `r`, and cancellation is exactly the operation that
manufactures the appearance of definability at `r = 0`.

```text
claim source_cone_domain_claim: the EdS cone identity holds identically for u != 0
derive refutes_source_cone_domain_claim: as a statement about the displayed rational expressions the claim is false at r = 0, from [cone_undefined_at_r0, source_cone_domain_claim] | the condition u != 0 admits r = 0, and there the right-hand side of the displayed identity is undefined while the left-hand side is 0
```

**Physical impact: essentially none, and that is worth stating.** `r = 0` is the
cone vertex, where the series recursion of §4 applies instead of the closed-form
cone quantities; and `r = 2` is the bang shell, excluded by `a_regularity`
(`r2_outside_admissible`). The full LTB cone relation carries an extra term
`2 u u'`, which vanishes at the vertex because `u(0) = 1` and `u' = O(r^3)` at a
regular center; it is dropped in the EdS case only because `u` is constant. The
finding is a statement about the *written* identity, not about the physics.

**What the fixture's test can and cannot see.** The protocol test evaluates the
stored cone expressions at the rational sample points `1/100, 7/500, 3/50, 1/2`.
None of these is `0` or `2`, so the test is consistent with the restriction
above but cannot detect it. This is not a defect: the test is explicitly
labelled finite-sample corroboration rather than a symbolic proof. It is
recorded in §10 as a coverage observation, not as a defect.

---

## 6. Reconstruction D — the gauge derivative

```text
# --- 6. The gauge derivative ---------------------------------------------------

given power_rule: for a constant n and an indeterminate x, (x^n)' = n x^(n-1)

derive gauge_derivative: dM/dr = 3r^2/2, from [M, power_rule] | M = (1/2) r^3, so d/dr[(1/2) r^3] = (1/2) * 3 r^2
derive gauge_typo_derivative: if the gauge string were read as M = r^(3/2), the derivative would be (3/2) r^(1/2), from [power_rule] | the same rule applied to r^(3/2)
derive gauge_typo_is_distinct: (3/2) r^(1/2) and 3r^2/2 are different functions, from [gauge_derivative, gauge_typo_derivative] | at r = 2 the two values are 3*sqrt(2)/2 and 6
```

**What the recorded execution in the fixture establishes** *(reported, not
certified here)*:

- `fixture.go` builds `M` as the body of a `function/1` with a single bound
  parameter `r` and runs `DIFFERENTIATE-001` at order 1 against it, recording a
  `derivation/1` in the evidence inventory.
- The hand golden is `3r^2/2`, stored as a separate `expression/1`. A stored
  `relation/1` with operator `EQ` binds the derivative output on its left to
  the golden on its right, and a `theorem/1` takes that relation as its
  conclusion with the differentiation derivation attached.
- `Verify()` replays each derivation in the inventory, checks the *binding*
  (left side byte-identical to the stored output, right side identical to the
  stored golden), and runs the theorem conclusion gate. `checkMPrimeGolden` is
  explicitly a *binding* check: the engine promises no distributivity and no
  term collection, so equality between the engine's uncollected output form and
  `3r^2/2` is **not** established by that check.
- The mathematical agreement is supplied by two independent routes in the
  protocol package: a hand-written exact-rational evaluator at finite rational
  sample points (supplementary corroboration), and a structural all-`r` argument
  over the decoded output that requires every nonzero monomial to have total
  degree two and the degree-two coefficients to sum to exactly `3/2`, with
  arbitrary-precision degree accumulation. The engine's output retains a
  `0 * r^3` product-rule residue, which the structural argument admits because
  its coefficient is zero and its exponent is a non-negative integer.

**Boundary.** Replay of a recorded derivation establishes that the recorded
steps reproduce their recorded outputs. It does not establish that the
derivation proves the intended proposition, and it says nothing about whether
the LTB assumptions apply. This document did not run any of it.

---

## 7. Reconstruction E — the EdS expansion construction and variable identity

```text
# --- 7. The EdS expansion construction ----------------------------------------
# (fixture) fixture.go builds theta = H + 2H with H one ephemeral symbol, and
# sigma^2 = (1/3)(H - H)^2 with the same H; theta is passed through EXPR-CANON-001
# and the canonical output is recorded; sigma is deliberately kept out of the
# evidence inventory.

given theta_construction: the stored EdS construction is theta = H + 2H, where H is one ephemeral symbol with display name "H"
given sigma_construction: the stored, represented-only shear expression is sigma^2 = (1/3)(H - H)^2 with the same H
given canon_semantics: EXPR-CANON-001 canonicalizes an expression by recursively canonicalizing children, flattening nested Add and Mul nodes, sorting commutative children by canonical bytes, and arity-normalizing; it performs no term collection, no distributivity and no theorem proving
given node_tags: the expression node tags are TagSymbol = 0x01, TagRational = 0x02, TagAdd = 0x03, TagMul = 0x04

derive theta_canon_shape: the canonical form of theta = H + 2H is a two-child Add whose children are the symbol occurrence H and the product 2*H, from [theta_construction, canon_semantics, node_tags] | neither child of the Add is itself an Add, so flattening leaves two children, and sorting by canonical bytes places the symbol occurrence (tag 0x01) ahead of the product node (tag 0x04)
derive canon_does_not_collect: the recorded canonicalization does not establish theta = 3H, from [canon_semantics, theta_canon_shape] | the two H occurrences remain two separate children of the Add; collecting like terms is not among the canonicalization operations
derive sigma_structural_value: the represented expression (1/3)(H - H)^2 evaluates to 0, from [sigma_construction] | H - H = 0, and 0 squared is 0
```

### 7.1 Variable identity

```text
derive H_occurrences_identical: the two H occurrences inside theta encode byte-identically, from [theta_construction] | the fixture builds both operands from one ephemeral symbol value, and an ephemeral symbol carries no ParameterID, so the encoded identity of an ephemeral symbol is its display string
claim H_is_one_variable: the two occurrences of H denote one and the same mathematical quantity, so that theta = H + 2H = 3H
    ? (fixture) the production H is an ephemeral symbol whose encoded identity is its display string; byte-identical encodings establish syntactic sameness in that representation, and they establish neither bound-parameter identity nor physical meaning; the fixture's synthetic control exercises the different mechanism of two bound symbols with distinct ParameterID values, and that control does not transfer to the production ephemeral H
```

**Boundary.** The canonicalization of `theta = H + 2H` is a *syntactic
normalization* of the stored tree. It is not a proof of `theta = 3H`, and it is
not a physical equation: `theta` is a construction artifact, and the EdS
expansion rate is a *model* quantity, established (if at all) by the model, not
by the normalizer.

**Boundary on the shear.** `sigma_structural_value` is a statement about a
*represented* expression. It is not a computation of the Buchert shear average
`<sigma^2>` over a domain, because the averaging operation and its volume
measure have no executable form in this slice. The fixture keeps the sigma
construction out of the evidence inventory on purpose. `Q_D = 0` for the EdS
background is therefore a formula-level consequence (§9), not an executed
result.

---

## 8. The claim register and the seven open obligations

The four register entries and the seven obligations are transcribed from
`phys-lib/gr/ltb/research_metadata.json`. The **status strings are metadata**,
reproduced here as attributed prose; they are not language constructs and they
assert nothing about the truth of the propositions they label.

```text
# --- 8. The claim register -----------------------------------------------------
# (fixture) research_metadata.json, "claims". The titles below are verbatim.
# The status strings in the trailing comments are metadata values.

claim zeh_q01: LTB distance-inversion freedom
    ? the register records the status string "literature-claim-requiring-verification" and attributes the background to Mustapha-Hellaby-Ellis 1997 for "background LTB distance-inversion freedom (applicability requires verification)"; that source was not read for this document and the inference it is meant to license is not written down, so a statement of which step of this investigation MHE 1997 is supposed to support would resolve this
claim zeh_q02: an exact iso-distance construction exists that reproduces D_A* exactly on 0 <= z <= 1
    ? the register records the status string "candidate-construction-incomplete"; the construction is blocked by o1, o2 and o3, and no admissible cone solution reproducing D_A* exactly is written down in the accessible artifacts
claim zeh_q04: the simultaneous-bang restriction t_B(r) = 0 closes the remaining freedom
    ? the register records the status string "deferred" and places the branch outside this slice; the accessible artifacts contain no argument that would settle it, so bringing it into scope is a separate task
```

The central conjecture `zeh_q03` is stated in §2b, with its own `?`.

```text
# --- 8b. The seven obligations -------------------------------------------------
# (fixture) research_metadata.json, "obligations": statement, blocked claims,
# and required evidence, transcribed. Each obligation is expressed here as the
# proposition that has to be discharged.

claim o1: the candidate cone solutions reproduce D_A* exactly on 0 <= z <= 1
    ? the register names the required evidence as a "regular cone solution reproducing D_A* exactly"; a construction together with an exactness argument on the whole interval would discharge this, and the formal-series recursion supplied in the research plan is a step toward it but not an exactness proof
claim o2: the cone solutions exist and are regular at the singular cone vertex
    ? the register names the required evidence as "majorant/CKS well-posedness for the vertex-singular ODE"; a majorant or Cauchy-Kowalevski argument for the vertex-singular system would discharge this
claim o3: each cone solution is admissible and admits a valid off-cone extension
    ? the register names the required evidence as "1+2E>0, R'>0, rho>0, no shell crossing, t_B from shell-age relation"; a per-model verification of these four conditions together with the shell-age reconstruction of t_B would discharge this
claim o4: the backreaction response distinguishes the models, that is Q_2[h] != 0 for some admissible profile under the exact constraint
    ? the register names the required evidence as "Q_2[h]!=0 for an admissible profile under the exact constraint"; one symbolic evaluation of the rational-function quadrature for a monomial driver h = r^4, together with the admissibility of that profile, would discharge this
claim o5: the perturbative remainder is controlled
    ? the register names the required evidence as an "O(epsilon^3) bound guaranteeing sign for small epsilon"; a uniform remainder estimate for the Q_D expansion along the family would discharge this
claim o6: the fixed-physical-boundary shift is accounted for in Q_D
    ? the register names the required evidence as "r_D(u) variation included at the relevant order"; including the variation of r_D(u) in the Q_D evaluation at the order at which it matters would discharge this
claim o7: the Q_D-specific claim is new
    ? the register names the required evidence as a "targeted literature comparison of the Q_D-specific claim"; a literature comparison over the candidate bodies identified in the research plan would discharge this
```

**Obligation map, as recorded** (prose, since the language has no dependency
construct): `o1` blocks `zeh_q02`, `zeh_q03`; `o2` blocks `zeh_q02`; `o3` blocks
`zeh_q02`, `zeh_q03`; `o4`, `o5`, `o6` block `zeh_q03`; `o7` blocks `zeh_q01`,
`zeh_q03`. This reproduces the register's `blocks` fields and is consistent with
the README's summary.

---

## 9. The identifiability argument: what is shown, what is not, what would settle it

### 9.1 The baseline value

```text
# --- 9.1. The EdS baseline value of Q_D ----------------------------------------

given eds_homogeneity: the EdS reference model is homogeneous, with a spatially constant expansion rate and vanishing shear
given evidence_inventory: the fixture's executed evidence inventory contains exactly two derivations, DIFFERENTIATE-001 on M(r) and EXPR-CANON-001 on theta; the sigma construction, the averaging integral and the volume measure are not in it

derive eds_qd_zero: Q_D^EdS(t0) = 0 for the EdS baseline, from [eds_homogeneity, buchert_qd] | the expansion-variance term <theta^2> - <theta>^2 vanishes for a spatially constant theta, and the shear term -2<sigma^2> vanishes with the shear
claim eds_baseline_executed: the fixture's executed evidence establishes Q_D = 0 for the EdS baseline
derive refutes_eds_baseline_executed: the executed fragment does not establish Q_D = 0 for the EdS baseline, from [evidence_inventory, eds_qd_zero] | the inventory contains no averaging or volume-measure step, so the value 0 is a consequence of the Buchert formula applied to the EdS profile and not a result computed by the recorded evidence
```

### 9.2 The metric freedom

```text
# --- 9.2. The cone system and the free input ----------------------------------

given cone_system: the closed cone system is Z' = (Z/u) Q, Q = (3r^2/G + 2 u u')/(2V + r^3 G' Z/((u - V) G^2)), V = +sqrt(r^3/G + u^2 - 1), T' = -P/u, P = G' Z Q/(u - V), with G(Z) = D_A*(Z - 1)
    ? (supplied, plan2_z.md section 4.2) the system is transcribed and is not re-derived here; the accessible Phys artifacts contain no cone-system artifact at all, so nothing in this document checks the algebra of the closure
given shell_age: the bang time is recovered from the cone solution by t_B(r) = T(r) - integral from 0 to G(Z(r)) of dR~/sqrt(r^3/R~ + u(r)^2 - 1)
derive u_is_free_input: the cone system is a first-order system in Z(r) with u(r) as a free input, and t_B is an output recovered from the shell-age relation, from [cone_system, shell_age] | no t_B occurs in the closed system, and the shell-age relation reconstructs t_B once the cone quantities are solved
```

**What this establishes, and what it does not.** It establishes *metric*
freedom: given `u`, the cone is determined; `t_B` is a shadow, not an input.
It does **not** establish that `Q_D` varies along that freedom. That gap is the
whole content of the central conjecture.

### 9.3 Why counting free functions does not close the gap

```text
# --- 9.3. The response structure and the invalid inference ---------------------

given q2_response_structure: the source records the expansion Q_D[u] = epsilon^2 Q_2[h] + O(epsilon^3) for a perturbation h of the background, with Q_2[h] = (2/3)[Var(delta theta) - <Delta^2>], delta theta = h'/r + h/r^2 - (9/2) s - (3/2) r s', Delta = h'/r - 2h/r^2 - (3/2) r s', and s(r) = -t_B^(1)(r) + (2/5) h(r)/r^2
    ? (supplied, plan2_z.md section 7) Q_2 is recorded as represented only, with no executable form in the accessible artifacts, so the functional cannot be evaluated, differentiated or checked here; writing out the two terms and their dependence on the Green tail would be the evidence that closes this
claim q2_leading_cancellation: in the quadratic functional Q_2[h], the (h'/r)^2 contributions of the expansion-variance term and of the shear term cancel
    ? (supplied) the source states this cancellation and uses it to warn that nontriviality is not automatic; because Q_2 is represented only, the cancellation cannot be exhibited or checked here, and doing so would resolve this

claim count_inference: the residual freedom of u(r) in the constrained class is by itself sufficient to conclude that Q_D(t0) is not determined by the observation
derive refutes_count_inference: the residual freedom of u(r) does not by itself imply that Q_D(t0) varies over the constrained class, from [u_is_free_input, q2_response_structure, q2_leading_cancellation] | the value of Q_D(t0) over the class depends on whether Q_2[h] is nonzero for an admissible profile under the exact constraint, and a count of free functions establishes neither; the leading-derivative content of Q_2 cancels between the variance and the shear terms, so an identically vanishing Q_2 is not excluded
```

**What this refutation does and does not say.** It says the counting inference
is **not licensed** by the premises available. It does not say that `Q_2`
vanishes, and it does not say that `Q_2` is nonzero. It says the question is
open, and that the question is `o4`.

### 9.4 The three substantive obligations for a proposed perturbation

A proposed perturbation must clear three separate hurdles. Each is a
substantive mathematical obligation; none follows from the others.

```text
# --- 9.4. Three obligations for any perturbation argument ----------------------

claim perturbation_is_admissible: a small perturbation h of the EdS background yields a model in admissible_class
    ? admissibility requires 1 + 2E > 0, R' > 0, rho > 0 and no shell crossing for the perturbed profile, and none of these is implied by smallness of h; a per-model verification is the evidence named by o3
claim perturbation_preserves_observation: a small perturbation h of the EdS background reproduces D_A* exactly on 0 <= z <= 1
    ? exactness on the whole interval is strictly stronger than agreement at leading order, and the supplied recursion is a formal-series statement whose analytic upgrade is o2; a construction with an exactness argument is the evidence named by o1
claim perturbation_changes_qd: a small perturbation h of the EdS background changes Q_D(t0) on the fixed physical domain
    ? this requires Q_2[h] != 0 for the perturbed profile under the exact constraint (o4), a controlled remainder (o5), and the variation of r_D(u) included at the order at which it matters (o6); the leading-derivative cancellation inside Q_2 means neither the sign nor the nonvanishing is automatic
```

### 9.5 What would settle the question

```text
# --- 9.5. The route conditional -------------------------------------------------

if there is an admissible profile h in admissible_class with Q_2[h] != 0 under the exact constraint, the perturbed model's distance function equals observation exactly on 0 <= z <= 1, the Q_D expansion remainder is controlled, and the fixed-boundary shift is accounted for:
    then
        derive route_yields_nonidentifiability: the observation does not determine Q_D(t0) over admissible_class, from [Qset, admissible_class, observation, q2_response_structure] | the perturbed model and the EdS model both match the observation, and their Q_D values differ at order epsilon^2 with epsilon^2 Q_2[h] != 0
    else
        derive route_yields_no_conclusion: this route yields no conclusion about identifiability, from [q2_response_structure] | the absence of a nonzero Q_2 for an admissible profile under the exact constraint leaves the question open, and it does not by itself establish identifiability either
```

**The `else` branch matters and should not be read as a negative result.** A
vanishing `Q_2` on the *perturbative* family would leave the exact-construction
route open, and it would leave open the possibility that the *physical* class
is wider than the perturbative family. The else branch says "no conclusion",
not "identifiable".

### 9.6 The value of one model is not identifiability

```text
# --- 9.6. The singleton criterion is not a value -------------------------------

claim edS_value_is_identifiability: because the EdS baseline has Q_D(t0) = 0, the observation determines Q_D(t0) = 0
derive refutes_edS_value_is_identifiability: the EdS baseline value does not establish that Qset is a singleton, from [eds_qd_zero, Qset] | the EdS model contributes one element, 0, to Qset; whether other elements exist is a separate question that the value 0 does not answer
```

### 9.7 Executed versus represented, in the supplied workflow

*(Reported, not certified here; the split is taken from
`manifest.json → verification` and `README.md`.)*

| Reported as executed | Reported as represented only |
|---|---|
| `DIFFERENTIATE-001` on `M(r) = r^3/2`, replayed, bound to the hand golden through a stored `EQ` relation and a theorem-conclusion gate | the spatial averaging integral and the volume measure (no integration primitive was added) |
| `EXPR-CANON-001` on the EdS `theta = H + 2H` construction, replayed | the vanishing of `sigma` beyond its factored structure |
| pointwise Go-rational corroboration of the EdS cone identity and of the stored series coefficients | the off-cone extension; the `Q_2` functional; all claim statuses |

**Three boundaries that the review keeps separate.** Pointwise rational
corroboration is not symbolic proof. Stored representation is not execution.
Replay is not proof that the physical assumptions apply. And mathematical
validity is not empirical support: the target `D_A*` is the EdS area distance
*by construction*; it is a model-based target, not a measured dataset, and no
observational consequence is represented or claimed anywhere in the material.

---

## 10. MRC adversarial review of this document

The review below follows `MRC_REVIEW_PROTOCOL.md`. Findings are `claim`s,
refutations are `derive`s, and genuinely open points are `?`s, as the
protocol's output shape prescribes. Prose attributes each finding: some are
defects of the *source* material, some are confirmations that this document
preserved a boundary, and some are defects of *this document*. Names are
prefixed `rv_` so that no name is declared twice in the document.

### 10.1 Reconstruction of the target

**Question.** Given an admissible LTB model class and a fixed past-light-cone
distance observation, what does the observation determine about present-day
Buchert backreaction `Q_D(t0)` on a specified comoving domain?

**Stated result.** None. The central entry `zeh_q03` is an open conjecture with
no theorem artifact.

**Regime.** Late-time classical GR, irrotational pressureless dust,
`Lambda = 0`, units `c = G = H0 = 1`; central observer; comoving synchronous
dust foliation; regular center; no shell crossings; a fixed physical domain
boundary.

**Scope of any possible conclusion.** A conclusion would be relative to a
specified class, foliation, domain and normalization — none of which is written
out in the accessible artifacts beyond seven prose descriptions.

### 10.2 Material findings

#### `rv_class_relativity` — the criterion is class-relative, the conjecture is not

```text
claim rv_class_relativity: the singleton criterion is a property of the pair (observation, admissible_class), and not of the observation alone
derive rv_class_relativity_step: two different classes can yield different identifiability verdicts for the same observation, from [rv_class_relativity, Qset, admissible_class] | Qset is defined through the membership clause "M in admissible_class", so changing the class changes the set and can change whether it is a singleton
claim rv_physical_conjecture: the physical conjecture that the observed data fail to determine Q_D(t0) concerns the true class of physically admissible LTB models, which is not fixed by the seven assumption descriptions
    ? the true admissible class is not specified in any accessible artifact; the seven descriptions are framework commitments, and whether they pin down the class a physical reading would use is not established; a written specification of the class, and an argument that it contains the intended models, would resolve this
```

**Why it is material.** The exact mathematical criterion and the physical
conjecture are different propositions. The criterion is a decision procedure
about a *declared* class and is exactly expressible. The physical conjecture
quantifies over a class that nobody has written down, and the two can have
different verdicts: a class narrow enough to contain only the EdS model is a
singleton, while the true class is expected to contain more. The document
expresses the first precisely and the second as a `claim` with a `?`; it cannot
do better, and it must not pretend to.

#### `rv_sample_coverage` — the source's domain assertion is over-strong (confirmed, and extended)

The document refuted the supplied assertion `source_cone_domain_claim` at
`r = 0`. The review confirms the refutation and adds a coverage observation
about the fixture.

```text
claim rv_sample_coverage: the protocol test's cone sample points do not probe the singular values of the displayed identity
derive rv_sample_coverage_step: the cone corroboration in the protocol test cannot detect the r = 0 domain restriction, from [cone_undefined_at_r0, evidence_inventory] | the sample points 1/100, 7/500, 3/50 and 1/2 are all different from 0 and from 2, so every evaluated point satisfies the restriction
```

**Why it is not a defect.** The test is explicitly labelled finite-sample
corroboration, not a symbolic proof, and the fixture's own limitations list
says as much. Recorded as a non-blocking coverage observation. **Minimum useful
improvement (optional, and not requested here):** name the domain restriction
in the test's documentation so that a future reader does not mistake a passing
sample sweep for a domain statement.

#### `rv_general_composition` — the source's vertex argument does not support the branch it reports

```text
claim rv_general_composition: the r^2 composition is A_1 = z_2 - (7/4) z_1^2, and the plan's displayed form A_1 - z_2 = -7/4 is the special case z_1 = 1
derive rv_general_composition_step: substituting z_1 = a_0 and A_1 = -a_0^2 into A_1 = z_2 - (7/4) z_1^2 gives z_2 = (3/4) a_0^2, from [rv_general_composition, vertex_relations] | z_2 = -a_0^2 + (7/4) a_0^2
claim rv_source_z2_form: the source's general form z_2 = 7/4 - a_0^2 coincides with the correct composition only at a_0 = 1
derive rv_source_z2_form_step: the two forms agree only when a_0 = 1, from [rv_general_composition_step, vertex_z2, vertex_relations] | (3/4) a_0^2 = 7/4 - a_0^2 forces a_0^2 = 1, and a_0 > 0 forces a_0 = 1
claim rv_branch_unverifiable: the second vertex branch reported by the source cannot be re-derived from the accessible material
    ? the branch equation is never displayed; the reported a_0 is the positive root of 6 a_0^2 + 6 a_0 - 1 = 0, and at least two candidate relations give an E_2 rounding to -3.4 (namely (a_0^2 - 1)/(2 a_0) and (a_0^2 - 1/a_0)/2), so the reported number does not identify the relation; the branch also uses the special-cased z_2 form
```

**Why it is material.** The source's remark — "the data alone fix one fewer
quantity than the class assumes — this strengthens, not weakens,
non-identifiability" — is the argument that the declared normalization is
load-bearing and that relaxing it opens a second branch. The review finds that
(a) the source itself withdraws the independence of the two vertex relations in
the same paragraph, so the advertised "two independent closed relations" are
one; (b) the general `z_2` formula used in the branch discussion is the
`a_0 = 1` special case, so the branch analysis is computed at the wrong order;
and (c) the branch equation itself is never written, and the reported numeric
`E_2` does not determine it. The *conclusion* the source draws — that `a_0` is
declared, not derived — survives, because it rests on the absence of a
derivation of `a_0`, not on the branch. But the branch as advertised is not a
checkable result. **Minimum fix:** display the r^1 and r^2 coefficient matches
with their own algebra, state the general composition, and write the branch
equation explicitly.

#### `rv_counting_refutation_scope` — the refutation of the counting inference is correctly bounded

```text
claim rv_counting_refutation_scope: the refutation of the counting inference is a statement about licensing, and not about the value of Q_2
derive rv_counting_refutation_scope_step: the refutation establishes that the counting inference is not entailed by the available premises, and it establishes neither that Q_2 vanishes nor that it is nonzero, from [refutes_count_inference, q2_leading_cancellation] | the cancellation, if established, removes an automatic route to nontriviality, and the remaining question is the explicit evaluation named by o4
```

**Assessment.** Correct as written. One dependency deserves recording: the
refutation leans on `q2_leading_cancellation`, which is itself a source-stated
claim with an open `?`. That is acceptable, because the inference is
*under*-determined either way — the counting argument fails whether or not the
cancellation is confirmed. The review notes the dependency and does not inflate
it into a defect.

#### `rv_obligations_independent` — the three hurdles are correctly separated

```text
claim rv_obligations_independent: admissibility of a perturbation, exact preservation of the observation, and a change in Q_D(t0) are three separate obligations, and none of them implies either of the others
derive rv_obligations_independent_step: a perturbation can preserve the observation exactly and still be inadmissible, and a perturbation can be admissible and change Q_D only through a vanishing Q_2, from [perturbation_preserves_observation, perturbation_is_admissible, perturbation_changes_qd, q2_response_structure] | the three claims have different content and different discharging evidence, named by o1, o3, o4, o5 and o6 respectively
```

**Assessment.** The document states the three obligations separately and does
not let any of them stand in for another. Confirmed.

#### `rv_finite_order_limit` — the finite-order example is correctly limited

```text
claim rv_finite_order_limit: the stored vertex coefficient z_3 = 1/2 constrains only the beta = 0 specialization, and does not discriminate the candidate recursion from any other relation agreeing there
derive rv_finite_order_limit_step: the beta = 0 check is consistent with infinitely many candidate relations, from [candidate_recursion_beta0, vertex_coefficients] | agreement at a single point of the parameter family is satisfied by any relation that agrees at that point
```

**Assessment.** The document states the limit in prose and attaches the `?` to
the `claim` rather than to the derivation, which is the correct attachment.
Confirmed; no finding.

#### `rv_canon_scope` — the canonicalization scope is correctly limited

```text
claim rv_canon_scope: the recorded canonicalization of theta = H + 2H establishes syntactic normalization of the stored tree, and establishes neither the algebraic identity theta = 3H nor any physical statement about the expansion rate
derive rv_canon_scope_step: the canonical output is a two-child Add retaining two separate symbol occurrences, from [theta_canon_shape, canon_does_not_collect, H_occurrences_identical] | canonicalization collects no like terms, so the recorded output is a normalized tree and not a collected one
```

**Assessment.** The document refutes the over-reading rather than assuming it.
Confirmed.

#### `rv_qd_execution` — the baseline value is correctly not promoted

```text
claim rv_qd_execution: the value Q_D^EdS(t0) = 0 is a formula-level consequence of the Buchert definition applied to the EdS profile, and is not an executed result of the fixture
derive rv_qd_execution_step: the evidence inventory contains no averaging step, from [refutes_eds_baseline_executed, evidence_inventory, eds_qd_zero] | the two recorded derivations are a differentiation and a canonicalization, and the represented-only material is excluded by construction
```

**Assessment.** Confirmed, and worth naming: this is exactly the "represented
is not executed" boundary, and it is the boundary most likely to be eroded by a
reader who sees a green test suite. The document refuses the promotion.

#### `rv_domain_value` — the domain of the question is not numerically fixed

```text
claim rv_domain_value: the physical domain over which Q_D is to be compared is not numerically fixed by the accessible Phys artifacts
derive rv_domain_value_step: the fixture and research_metadata.json name the boundary only symbolically as Rphys, from [Rphys, a_domain, evidence_inventory] | no accessible artifact carries a numerical value for Rphys, so the domain enters the identifiability criterion only as an unspecified constant
```

**Why it is material.** `Q_D` is an average over a domain; the domain is part
of the quantity. An unspecified `Rphys` means the target value of `Q_D` is not
even a well-defined real number, independent of the conjecture. **Minimum fix:**
carry the numerical value of `Rphys` (and the associated `r_D`) in the
artifacts, or state explicitly that the domain is symbolic.

### 10.3 Checks applied, and their proportional relevance

| Check | Applied to | Outcome |
|---|---|---|
| premise sufficiency | every consequential `derive` in §3–§9 | recomputed by hand; one premise list found too strong and repaired during review |
| circularity | the composition check (§4.1), the vertex relations (§4.2), the baseline value (§9.1) | none found; the composition check uses only the series and the definitions |
| counterexample-first | `refutes_23_8` (composition at `z^3`), `gauge_typo_is_distinct` (at `r = 2`), `refutes_source_cone_domain_claim` (at `r = 0`), `refutes_edS_value_is_identifiability` (set-theoretic), `refutes_count_inference` (logical) | all five have concrete counterexamples or explicit counter-derivations |
| domain / degenerate cases | the cone identity (`r = 0`, `r = 2`), the series (`|r| < 2`, `|z| < 1`), the gauge derivative (all `r`) | two material findings (`r = 0` undefined; `r = 2` a true pole) |
| finite-order vs general | the vertex coefficients, the candidate recursion | correctly limited; confirmed |
| conditional scope | the two case splits in §2 and §9.5 | branch-local names are never cited outside their branch; the `vertex_*` and `branch_*` derivations that restate a branch condition do so by listing the condition's premise, which `PSEUDO.md` §5.5 permits |
| role confusion | `define` vs `assume` vs `given` vs `claim` | the definitions in §1, §2, §4 and §5 pass the substitution test of `PSEUDO.md` §3; no definition smuggles a law, an existence claim or a physical assumption |
| theoretical vs physical vs empirical | §9.7 and the evidential boundary | separated; no empirical claim anywhere |

### 10.4 Cosmetic observations (explicitly not inflated)

- The `if`/`then`/`else` in §2 has no name slot, so its two branch conclusions
  cannot be cited later (`PSEUDO.md` §5.5). The document therefore states the
  criterion twice — once in the branch, once as `criterion_is_singleton`. This
  is a documented expressiveness boundary of the language, not a scientific
  defect.
- The `?` on `define admissible_class` and on `define Qset` is attached to the
  nearest statement that owns the gap, but the underlying questions are
  document-level. A reader looking for document-level questions must look at
  the two attached `?`s.

---

## 11. How well does Phys Pseudo handle this investigation?

**1. What was easy.** The definitional spine of the argument mapped cleanly:
the symbol meanings (`M`, `r`, `Rphys`, the five cone quantities, `beta`),
the four roles of the conventions kept apart (§1), the singleton criterion
(`Qset`, `identifiable`, the case split), the chain of derivations for the
target series and the EdS expansion, the claim register, and the obligation
list. The seven constructs were sufficient for essentially the whole argument.
Two counterexample-style refutations (`refutes_23_8`,
`refutes_source_cone_domain_claim`) were natural in the language, and the
refusal to promote a candidate recursion was expressible without a status
vocabulary.

**2. What had to live in prose or comments.** (a) *Source attribution* —
mandated by `PSEUDO.md` §8, and it worked, but it means a reader cannot
mechanically separate "reconstructed here" from "transcribed" without reading
the prose. (b) *The executed/represented-only boundary* — this is the largest
prose load. The language has no evidence construct, so "the fixture records
this as executed" versus "I checked this" versus "this is represented only"
had to be carried in a table and surrounding prose. (c) *Register statuses* —
the four status strings and the `blocks` relation are metadata with no
construct; they were reproduced as attributed prose and as `?` content. (d)
*The obligation-to-claim dependency map* — again prose.

**3. Friction with conditionals, premise lists and `?`.** Three real frictions.
(i) A case split cannot be cited: the two branch consequences of the
identifiability split die with their branch, so the criterion had to be
restated at top level. (ii) A `?` must attach to a statement, so a
document-level question ("what is the admissible class?") had to be hung on
the nearest `define`, which slightly mislocates it. (iii) Premise lists are
proposed, not complete, and the language offers no way to *mark* a list as the
author's best effort; a reviewer must hunt. That is the protocol's stated
design, and it worked — the `rv_` review found one over-strong premise list
precisely because the list is visible.

**4. The exact criterion vs. the physical conjecture.** The exact criterion was
expressible with precision, and precisely. The physical conjecture was
expressible only as a `claim` with a `?`, because it quantifies over a class
that nobody has written down. The deeper problem is not expressive: the
criterion is *class-relative*, and the language has no way to parameterize a
`define` by a class, so the class had to be baked into `Qset` and the
relativity had to be recovered in prose and in the review
(`rv_class_relativity`). The language could carry the *distinction* between
"the criterion" and "the conjecture"; it could not carry the criterion as a
*parameter*.

**5. Candidate vs. established, without a status system.** Yes, and cleanly:
`claim` for the candidate recursion, `derive` for the independently
recomputed coefficients, an attached `?` naming what would settle it, and
prose for the attribution. The `?` did most of the work that a status
vocabulary would otherwise do — but it is doing something slightly different:
`?` marks *unresolved*, whereas the candidate recursion is *asserted and
uncorroborated*. The nuance that the source considers it probably-right was
carried in prose. No status system was needed and none should be added.

**6. Essential facts that were unavailable.** (i) A written definition of the
admissible class (metric, equations, solution regularity, boundary data).
(ii) The numerical value of `Rphys` / `r_D`. (iii) The definition of `beta` in
the Phys artifacts. (iv) Any executable form of `Q_2` and of the averaging
measure. (v) The off-cone extension. (vi) The branch equation for the second
vertex branch. (vii) The text of MHE 1997 and Buchert 2000. (viii) The
general `z_2` relation in the source's own notation — which the review had to
reconstruct. (ix) Any artifact or test in the fixture that mentions `Q_D` at
all: the package contains none, so the identifiability question has no
representation in the executed slice whatsoever.

**7. Was anything genuinely impossible?** No. Every distinction needed was
expressible either formally or in prose, and the prose was sufficient in each
case because the distinctions were *epistemic* (who said it, whether it was
executed) rather than *mathematical*. Two places where prose did real work
rather than decoration: the executed/represented-only boundary, and the
class-relativity of the criterion. **No new construct is warranted.** The
frictions in item 3 are inherent to a deliberately minimal language, are
documented in `PSEUDO.md` itself, and were handled adequately by the
surrounding prose. Any proposed language change would be a separate task with
its own review, and nothing observed here would justify one.

**8. What the review found that merely writing the pseudocode did not expose.**
Writing the pseudocode produced a document that *looks* complete. The review
found: the `r = 0` failure of the displayed cone identity and the fact that the
supplied "holds identically for `u != 0`" is false as displayed; the
distinction between the removable singularity at `r = 0` and the true pole at
`r = 2`; the source's own withdrawal of the independence of its two vertex
relations, and the special-cased general `z_2` form that the branch analysis
depends on; the fact that the reported `E_2 ≈ -3.4` is compatible with more
than one candidate relation; the class-relativity of the identifiability
verdict, and the resulting gap between the exact criterion and the physical
conjecture; the absence of any numerical domain in the artifacts; and the fact
that the protocol test's sample points cannot see the domain restriction. None
of these is visible from the structure of the pseudocode alone; each required
an independent check.

---

## 12. Evidential boundary

**What was checked, and how.**

- *By hand, by exact arithmetic*, on this document: the binomial expansion of
  `(1+z)^(-1/2)` through `z^3`; the numerator `2[1-(1+z)^(-1/2)]`; the Cauchy
  product with `(1+z)^(-1)` giving the coefficients `1`, `-7/4`, `19/8`; the
  same product continued to `z^4` giving `-187/64`; the refutation of `23/8`
  both by the multiplication (`n_3` would have to be `9/8`) and by the EdS
  composition (`r^3` coefficient `3/4` instead of `1/4`); the expansion of
  `(1-r/2)^(-2)` through `r^3` and its radius of convergence `|r| < 2`; the
  reduction of both sides of the cone identity to `2r/u^2` and the full domain
  of the *displayed* expressions (`r != 0` and `u != 0`); the behaviour at
  `r = 0` (removable, value `0`) and at `r = 2` (a genuine pole); the gauge
  derivative; the `r^(3/2)` counterexample at `r = 2`; the vertex relations at
  `a_0 = 1` giving `E_2 = 0` and `z_2 = 3/4`; the general composition
  `A_1 = z_2 - (7/4) z_1^2` giving `z_2 = (3/4) a_0^2`; the algebraic
  fingerprint `6 a_0^2 + 6 a_0 - 1 = 0` of the reported second branch, and the
  two candidate values of `E_2` that both round to `-3.4`.
- *By reading source*, not by executing: the semantics of `DIFFERENTIATE-001`,
  `EXPR-CANON-001` and `Canonicalize` in `phys-math`; the node-tag ordering
  used in `theta_canon_shape`; the seven assumption seeds, the two-entry
  evidence inventory, the exclusion of the sigma construction, the golden
  binding check, the sample points used by the protocol tests, the manifest's
  executed/represented-only split and limitations, the claim register and
  obligations in `research_metadata.json`, and the behaviour and limits of
  `CheckClaimPromotion`.

**What was not independently checked.** No Go code was built, run, replayed or
tested; **no test result of any kind is reported here**, and every statement
about "executed" work is a report *about* the supplied workflow. The LTB
metric and orbit equations, the closed cone system, the shell-age relation,
the vertex relations, the `Q_2` functional and its leading-derivative
cancellation were transcribed, not re-derived. `MHE 1997` and `Buchert 2000`
were not read, so both citations remain unverified, as the register itself
records. The off-cone extension, the averaging operation, the volume measure
and the `Q_2` functional have no executable form in the accessible slice and
were not evaluated. No admissible model pair was constructed; no `Q_D` value
other than the formula-level EdS baseline was computed; the perturbative
family was not instantiated.

**What remains open.** The seven registered obligations `o1`–`o7`, exactly as
the register states them, with `o4` (a nonzero `Q_2[h]` for an admissible
profile under the exact constraint) the decisive one. In addition, and beyond
the register: the written definition of the admissible class; the numerical
value of `Rphys`; the general `z_2` relation and the branch equation of the
second vertex branch; the definition of `beta` in the Phys artifacts; and the
relation between the declared class and the class a physical reading would use
(`rv_class_relativity`).

**What this document does not assert.** It does not assert that `zeh_q03` is
true, and it does not assert that `zeh_q03` is false. It does not assert that
non-identifiability follows from metric freedom or from counting free
functions — §9.3 refutes that inference. It does not assert that the
existing test suite says anything about the LTB identifiability question; the
suite concerns the executed fragment, and the package contains no `Q_D`
artifact at all. It does not assert that the mathematics above is physically
applicable to the real universe, and it makes no empirical claim: the target
`D_A*` is the EdS area distance by construction, not a measurement.
