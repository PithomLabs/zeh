Use the exact same prompt for every agent, run them independently, and compare their derivations—not just their conclusions. The next task is deliberately narrower: test whether LTB can deliver a genuinely nontrivial relation between spatial backreaction and past-light-cone observations.

# Common Agent Task: Derive or Falsify the Spatial–Null Consistency Relation

## Mission

Conduct an independent, adversarial mathematical investigation of this question:

**For a specified inhomogeneous spacetime, can we derive a nontrivial, testable consistency relation between Buchert’s spatially averaged dynamics and past-light-cone observables, without introducing enough free functions to fit observations arbitrarily?**

Your immediate task is not to develop a Theory of Everything, explain dark energy, or prove the zero-energy universe hypothesis. It is to establish exactly what can and cannot be derived from a controlled relativistic model.

All agents must work from this identical specification. Do not assume that another agent's proposed result is correct. Derive the equations independently, check relevant primary sources, and report negative results honestly.

## 1. Mandatory methodological rules

Apply the Math Reality Check throughout.

- **Census:** identify the physical degrees of freedom, independent data, and quantities actually determined.
- **Grammar:** verify the mathematical identities, differential equations, and definitions.
- **Constitution:** state the theory, coordinate choices, foliation, boundary conditions, and closure assumptions. Do not pretend the framework choice was derived.
- **Shield:** formulate a falsifiable restriction that could rule out the specified model.
- **Generator/selector warning:** do not use constraints to claim that you have generated a physical mechanism, selected initial conditions, or predicted a fundamental constant unless an explicit derivation establishes that claim.

The Math Reality Check is a methodological audit, not a universal no-go theorem prohibiting mathematics from deriving physical results.

Every important assertion must be classified as one of:

1. Established result from the literature.
2. Derivation completed in this investigation.
3. Conditional result depending on stated assumptions.
4. Conjecture or proposed research direction.
5. Unsupported or falsified claim.

Verify equations, rather than trusting confident prose. Check signs, dimensions, definitions, limiting cases, and hidden assumptions. Cite primary sources for established results, and distinguish those sources from your own derivations.

## 2. Declare the physical regime and scale

Begin by explicitly stating the regime to which the investigation applies.

For this task, start with late-time, classical general relativity, using pressureless dust and optionally a cosmological constant. Work at cosmic-web averaging scales, typically Mpc to tens or hundreds of Mpc, with observations on the much larger past light cone.

Explain the distinction between:

- RG energy/momentum scale;
- physical spatial and averaging scale;
- cosmological redshift and time;
- the classical spacetime description and any effective or coarse-grained description.

**Do not call spatial averaging an RG flow without deriving that connection.** Do not extrapolate this classical result to the Planck scale, quantum gravity, particle-generation selection, or the Born rule.

## 3. Use LTB as the first controlled laboratory

Investigate the Lemaître–Tolman–Bondi (LTB) solution for spherically symmetric pressureless dust, with the option of including a cosmological constant.

State the metric, conventions and field equations. For example, in units where (c=1), one common convention is

[\
ds^2=-dt^2+\frac{R'(t,r)^2}{1+2E(r)},dr^2+R(t,r)^2d\Omega^2.\
]

Define every symbol, including the mass function, radial curvature/energy function, and any bang-time or integration functions. State the radial-coordinate freedom and count the independent physical functions only after accounting for that freedom.

Do not assume a specific density profile or remove a free function without identifying this as an additional physical assumption.

## 4. Derive the spatial quantities

Choose and justify a comoving spatial domain (\mathcal D), its foliation, and its boundary prescription. Give the proper volume element and averaging definition.

For irrotational dust, calculate or express in terms of the specified solution:

[\
H\_{\mathcal D},\qquad\
Q\_{\mathcal D},\qquad\
\langle{}^{(3)}R\rangle\_{\mathcal D}.\
]

Use the standard Buchert convention:

[\
Q\_{\mathcal D}\
\=\frac23\left(\
\langle\theta^2\rangle\_{\mathcal D}\
-\langle\theta\rangle\_{\mathcal D}^{,2}\
\right)-2\langle\sigma^2\rangle\_{\mathcal D}.\
]

Verify the averaged Hamiltonian equation and integrability condition under the assumptions you state.

Do not reverse the signs of expansion variance and shear, replace a variance with a second moment, or treat (Q\_{\mathcal D}) as an arbitrary observable.

## 5. Derive the past-light-cone quantities

For a specified observer, derive the radial null-geodesic and redshift equations and calculate the applicable observables, including:

- Angular-diameter distance (D_A(z));
- radial and transverse expansion rates, where applicable;
- redshift drift (\dot z(z)), if the derivation is tractable;
- relevant optical shear or lensing quantities, if they contribute to the proposed relation.

Be explicit about which quantities are directly observable and which require reconstruction or assumptions.

Do not substitute the Buchert-averaged scale factor into FLRW distance equations without proving that this substitution is valid in the chosen model.

## 6. The central challenge: derive or falsify the bridge

Investigate whether the spatial quantities and the light-cone quantities obey a **closed, nontrivial relation** in the chosen LTB model.

Proceed in this order:

1. Identify which metric functions enter each set of quantities.
2. Derive the exact relations that follow from the field equations and null propagation.
3. Attempt to eliminate unobserved metric functions where mathematically justified.
4. Determine whether the result genuinely constrains (Q\_{\mathcal D}) or other spatially averaged quantities through light-cone observables.
5. If the elimination is impossible without additional information, identify exactly what remains unknown and why.

Crucially, distinguish these three outcomes:

**A. Common-metric consistency:** both sets of quantities are computed from the same metric and therefore agree with that metric.

**B. Existing model test:** a fixed LTB solution predicts multiple observables that can be compared with data.

**C. New consistency relation:** a derived constraint removes or links otherwise independent quantities and has predictive content beyond merely solving the same metric twice.

Do not claim outcome C merely because A or B has been established.

## 7. Adversarially test the previous agents’ proposed shortcuts

Explicitly evaluate the following claims, without assuming they are true:

- A relation between redshift drift and the shear contribution to (Q\_{\mathcal D}) automatically determines the full (Q\_{\mathcal D}).
- The spatial-averaging commutation rule is equivalent to a boundary-flux law.
- A boundary or Stokes argument directly produces an exact slice-to-null-cone matching equation.
- A Clarkson–Bassett–Lu or other FLRW null-test statistic is automatically proportional to (Q\_{\mathcal D}).
- A nonzero FLRW null test uniquely identifies backreaction or establishes that backreaction causes acceleration.
- Merely having more observables than free parameters proves a model is identifiable and predictive.

For each claim, give the strongest supporting derivation or source, or explain exactly why the claim fails. Distinguish exact identities from approximations and model-dependent ansätze.

## 8. Conduct a proper degrees-of-freedom and identifiability audit

Do not rely solely on the rule “number of observables greater than number of parameters.”

Determine:

- The physical free functions and parameters after gauge freedoms are removed.
- Which quantities are inferred from independent observations.
- Which observables are degenerate or statistically dependent.
- Which priors, closure conditions, or profile restrictions are imposed.
- Whether a proposed relation survives when those assumptions are varied.
- Whether independent observables genuinely overdetermine the specified model.

If a parametric profile, simultaneous-bang condition, simulation-derived structure, or scaling ansatz is introduced, classify it as an explicit additional assumption. Do not describe it as a consequence of Buchert’s equations unless proved.

## 9. Mandatory control checks

Before reporting success, show the relevant checks:

**FLRW limit:** establish that the equations reduce correctly when the inhomogeneity vanishes or the chosen solution becomes FLRW.

**Dimensional and sign checks:** verify dimensions, signs and normalization conventions.

**Domain dependence:** test what happens when the averaging domain or foliation changes. State whether the proposed restriction is invariant or prescription-dependent.

**Independent prediction:** identify at least one observable not used to tune the model that the proposed relation predicts.

**Falsifier:** state a realistic result that would reject the relation or the chosen model class.

If any check fails, report the failure rather than quietly modifying the result.

## 10. Required output format

Structure your answer in the following order:

1. **Executive verdict:** derived, partially derived, not derived, or falsified.
2. **Applicable regime and RG/physical scales.**
3. **Definitions and assumptions:** metric, matter model, observer, domain, foliation and free functions.
4. **Equation audit:** sourced equations and your derivations, with steps where needed.
5. **Bridge result:** the strongest relation actually established, if any.
6. **Degrees-of-freedom audit:** what is fixed, what remains free, and what makes the test identifiable.
7. **Adversarial claim table:** previous claims, verdicts, and mathematical reasons.
8. **Controls and falsifier:** FLRW limit, dimensional/sign checks, domain sensitivity, and an independent observational prediction.
9. **Literature:** primary sources, with precise citations and a statement of what each source actually establishes.
10. **Research recommendation:** the single most valuable next calculation and why it follows from your findings.

End with a compact status table:

| Claim                                                | Status | Evidence or missing step |
| ---------------------------------------------------- | ------ | ------------------------ |
| Spatial Buchert equations                            | <br>   | <br>                     |
| Light-cone propagation equations                     | <br>   | <br>                     |
| LTB spatial-to-null relation                         | <br>   | <br>                     |
| Relation specifically constraining (Q\_{\mathcal D}) | <br>   | <br>                     |
| Independent predictive content                       | <br>   | <br>                     |
| Observational falsifier                              | <br>   | <br>                     |

## 11. Standard of success

A successful submission must produce at least one explicit, correctly derived relation with its assumptions and limitations stated. It must explain why the relation is not merely tautological, how it restricts the allowed model or reconstruction, and what independent observation could falsify it.

If no such relation can be established, that is an acceptable and useful outcome. Show the strongest partial result and isolate the obstruction precisely.

Do not invent an equation to satisfy the task. Do not use confident language to cover an unclosed system. Do not claim novelty unless the relevant literature has been checked.

**Final principle:** the common spacetime guarantees that its calculated quantities are mutually consistent. Our research task is to discover whether that consistency can be expressed as a new, closed, observable restriction without hiding the missing information in freely adjustable functions.

Comparison protocol: give this same prompt to each agent without sharing the others’ responses first. When you bring the outputs back, the decisive comparison should be equation-level: which relation was actually derived, under which assumptions, and what independent observation could falsify it.
