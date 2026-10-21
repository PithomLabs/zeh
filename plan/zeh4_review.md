# Research Director’s adjudication: ZEH-4

The agents have clarified the inverse problem, but they have not completed the benchmark. The next stage should be a reproducible calculation, not another round of prose-only derivations.

My verdict is Outcome A established, Outcome B conditionally achievable, Outcome C not derived—and not proven impossible. The reports reveal an important source-version error, inconsistent equation conventions, and numerical counterexamples that cannot yet be reproduced.

## 1. What survives the collective review?

| Claim                                                                                                    | Research Director’s decision                            |
| -------------------------------------------------------------------------------------------------------- | ------------------------------------------------------- |
| Buchert spatial averaging and LTB light propagation are established mathematical frameworks.             | Keep                                                    |
| One specified metric determines its spatial averages and past-light-cone observables.                    | Keep — Outcome A                                        |
| General LTB reconstruction may be underdetermined by distance data alone.                                | Keep as a hypothesis to test under explicit assumptions |
| Restricting the model can produce independently testable predictions.                                    | Keep — Outcome B                                        |
| A new closed relation directly linking \\(Q\_{\mathcal D}\\) to light-cone observables has been derived. | Reject — not demonstrated                               |
| Such a relation is impossible for all central LTB domains.                                               | Reject — not demonstrated                               |

The published light-cone averaging framework gives us the appropriate mathematical tools, but it does not automatically close the system linking spatial backreaction to observations.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://arxiv.org\&sz=32)

arXiv



### The most consequential correction: the Sussman sign claim

DeepSeek claims that Sussman proved \\(Q\_{\mathcal D}\leq0\\) for all central spherical LTB domains, then uses this to declare the bridge impossible.&#x20;

zeh4_deepseek.md



The current full text of Sussman’s paper does not support that universal claim. It reports \\(Q\_{\mathcal D}\geq0\\) for specified regular hyperbolic domains without turning values, and \\(Q\_{\mathcal D}\leq0\\) for specified elliptic domains without turning values. Configurations involving turning values require additional conditions on the domain and the profiles.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://arxiv.org\&sz=32)

arXiv

+1



Decision: remove the universal sign theorem from our research record. The agent appears to rely on an earlier version or summary of the paper. We must reconcile source versions and theorem assumptions before using a result to rule out an entire model class.

This does not establish our proposed bridge. It removes an invalid reason for claiming that the bridge is impossible.

## 2. Equation and evidence corrections

Free-function counting. General LTB has three radial functions before radial-coordinate freedom is fixed: \\(M(r)\\), \\(E(r)\\) and \\(t_B(r)\\). After gauge fixing, two independent physical functions remain. If we choose \\(M(r)=M_0r^3\\), the remaining functions are \\(E(r)\\) and \\(t_B(r)\\). Imposing \\(t_B(r)=\mathrm{constant}\\) is an additional physical restriction, leaving one free function if the global parameters are fixed.

Some reports confuse gauge fixing with the simultaneous-bang restriction. DeepSeek’s summary even reverses the case labels.&#x20;

zeh4_deepseek.md



Google’s claimed algebraic bridge. The proposed inversion formula does not follow from the equations supplied in its report.&#x20;

zeh4_google.md



In units \\(c=G=1\\), define

\\[ A=(1+z)H\_{\parallel}\frac{dD_A}{dz}, \qquad B=1-\frac{2M}{D_A}-\frac{\Lambda D_A^2}{3}. \\]

The radial null equations and LTB shell equation give

\\[ A=\sqrt{1+2E}-\dot R, \qquad B=(\sqrt{1+2E}-\dot R)(\sqrt{1+2E}+\dot R). \\]

Therefore, when \\(A\ne0\\),

\\[ \boxed{\sqrt{1+2E}=\frac{A^2+B}{2A}} \\]

—not the formula Google claims. Even this corrected identity still involves the mass profile \\(M(r)\\); it is not a relation determining \\(Q\_{\mathcal D}\\).

There is also a recurring redshift-drift error. For a central observer in LTB, the standard relation is

\\[ \dot z(z)=(1+z)H_0-H\_{\perp}(z), \qquad H\_{\perp}=\frac{\dot R}{R}, \\]

not the same expression with \\(H\_{\parallel}=\dot R'/R'\\) substituted for \\(H\_\perp\\).&#x20;

[image](https://www.google.com/s2/favicons?domain=https://www.if.ufrj.br\&sz=32)

if.ufrj.br



Numerical evidence. Google, Meta and Qwen report model profiles or different values of \\(Q\_{\mathcal D}\\) for models claimed to reproduce the same distance data.&#x20;

zeh4_google.md

zeh4_meta.md

zeh4_qwen.md



But none of these submissions provides a complete executable calculation with all profiles, solver details, residuals and numerical convergence checks. Their numerical claims therefore remain unverified proposed counterexamples, not completed derivations.

## 3. The next move: a reproducible inverse-problem benchmark

As Research Director, I am freezing the immediate target. We will not broaden the inquiry to off-centre domains or pressure perturbations until the baseline identifiability question has been tested.

The research question is:

> Can two admissible LTB models reproduce the same specified distance–redshift data but yield different present-day values of \\(Q\_{\mathcal D}\\) for the same physical domain and foliation? Does additional independent observational information remove the ambiguity?

This remains a controlled investigation in late-time classical general relativity, with dust and \\(\Lambda=0\\) for a synthetic benchmark. The domain is defined at a cosmic-web scale, illustratively 100 Mpc, while the distance data lie on the much larger past light cone. Spatial averaging is classical coarse-graining, not a Wilsonian RG flow.

## 4. Common next-task prompt for all agents

# ZEH-5: Executable LTB Identifiability Benchmark

## Role and objective

You are a **research worker** executing a bounded investigation. Do not expand the research agenda or declare an unverified result established. The Research Director will adjudicate your output against this common specification.

**Question:** Can past-light-cone data determine the present-day Buchert backreaction (Q\_{\mathcal D}(t_0)) in a general LTB model, and how does the answer change when a simultaneous-bang restriction is imposed?

Distinguish:

- **Outcome A:** quantities consistently derived from the same metric.
- **Outcome B:** conditional predictions of a restricted model.
- **Outcome C:** a new relation with additional predictive content beyond ordinary metric reconstruction.

Do not assume Outcome C exists or is impossible.

## 1. Fixed benchmark specification

Use late-time classical GR with irrotational pressureless dust, (c=G=1), and (\Lambda=0). This is a synthetic mathematical control, not a claim that an Einstein–de Sitter universe describes current observations.

Use dimensionless Hubble units (H_0=c=1). The LTB metric and shell equation are

[\
ds^2=-dt^2+\frac{R'(t,r)^2}{1+2E(r)}dr^2+R(t,r)^2d\Omega^2,\
]

[\
\dot R^2=\frac{2M(r)}{R}+2E(r).\
]

Fix the radial gauge (M(r)=r^3/2). The reference Einstein–de Sitter solution has (E(r)=0), (t_B(r)=0) and (t_0=2/3).

Use the target angular-diameter distance

[\
D_A^\*(z)=\frac{2[1-(1+z)^{-1/2}]}{1+z},\
\qquad 0\le z\le1,\
]

where (D_A^\*=H_0D_A/c). Verify analytically that this is the reference solution before beginning the inverse reconstruction.

Define the spatial domain by its present-day **areal-radius boundary**, (R(t_0,r\_{\mathcal D})=100,\mathrm{Mpc}), or (H_0R/c\simeq0.0233) for (H_0=70,\mathrm{km,s^{-1},Mpc^{-1}}). In each model, solve for the coordinate boundary (r\_{\mathcal D}) that gives this physical radius. Do not simply reuse the same coordinate radius across different metrics.

The physical spatial averaging scale is not an RG momentum scale. No connection to quantum gravity or the origin of the cosmological constant is under investigation.

## 2. Case A: general LTB

With (M(r)=r^3/2), retain the two independent functions (E(r)) and (t_B(r)).

Introduce a smooth, nonconstant bang-time profile, for example

[\
t_B(x)=\Delta\left[e^{-(x/\alpha)^2}-1\right],\
\qquad x=r,\quad \alpha=0.05,\
]

with dimensionless (\Delta) expressed in units (H_0^{-1}). Test and declare a small set of (\Delta) values.

Solve the inverse problem for (E(r)) to reproduce the fixed target (D_A^\*(z)) over the stated redshift interval. This profile is a test choice, not a theorem. If it fails regularity or cannot reproduce the target, document the failure and test a clearly specified alternative. Do not interpret the failure of one parameterization as proof that all alternatives are impossible.

## 3. Case B: simultaneous-bang restriction

Set (t_B(r)=0) as an explicit physical restriction, not a coordinate convention. With the stated gauge and fixed global parameters, determine whether the remaining profile can be reconstructed from the target distance data.

Establish uniqueness only if the inverse equations, boundary conditions and regularity requirements justify it. Counting unknown functions and observables is not sufficient.

## 4. Compute spatial and light-cone quantities

Calculate

[\
Q\_{\mathcal D}\
\=\frac23\left(\
\langle\theta^2\rangle\_{\mathcal D}\
-\langle\theta\rangle\_{\mathcal D}^{,2}\
\right)-2\langle\sigma^2\rangle\_{\mathcal D},\
]

using the proper-volume measure for the selected domain and the same foliation and evaluation time in both models.

Calculate (D_A(z)) and (H\_{\parallel}(z)=\dot R'/R') along the past light cone. If you calculate redshift drift, verify the central-observer LTB formula against a primary source; do not interchange (H\_\parallel) and (H\_\perp).

## 5. Test identifiability

For the general LTB case, attempt to establish one of the following:

1. Construct two admissible models that reproduce the target (D_A^\*(z)) within a declared tolerance yet give materially different (Q\_{\mathcal D}(t_0)) for the same physical domain; or
2. establish a valid uniqueness argument showing that the target data and stated assumptions determine (Q\_{\mathcal D}(t_0)).

For a pair of models, provide complete profiles and verify:

- (1+2E(r)>0);
- positive matter density in the tested domain;
- (R'(t,r)>0) wherever the models are used;
- regularity at the centre;
- absence of shell crossing or other relevant singularities over the tested interval.

If no pair can be constructed, report the attempts, failures and remaining uncertainty. Function counting alone is not a counterexample.

## 6. Independent prediction

Use distance data as the fitting target. Calculate at least one additional observable not used in fitting, preferably radial expansion or redshift drift.

Report whether the restricted model makes a successful held-out prediction and whether the general model retains degeneracies. Synthetic-data success is not empirical confirmation.

## 7. Mandatory verification and deliverables

- Recover the exact Einstein–de Sitter limit with (Q\_{\mathcal D}=0).
- Check signs, dimensions, regularity and numerical convergence.
- Report the distance residual as a function of redshift.
- Show convergence of (Q\_{\mathcal D}) with numerical resolution.
- Hold the physical domain fixed across models.
- Verify source versions and theorem assumptions.
- Supply runnable code, profile definitions, actual outputs and residual checks. If the implementation was not executed, label it unexecuted and make no numerical-validation claim.

Apply the Math Reality Check and MRC2. Classify claims as established, derived here, conditional, conjectural, contradicted or underdetermined.

End with a table:

| Claim                                            | Status | Evidence or missing step |
| ------------------------------------------------ | ------ | ------------------------ |
| Buchert equations                                | <br>   | <br>                     |
| LTB light-cone equations                         | <br>   | <br>                     |
| Distance data identify the general model         | <br>   | <br>                     |
| (Q\_{\mathcal D}(t_0)) is uniquely determined    | <br>   | <br>                     |
| Restricted model makes an independent prediction | <br>   | <br>                     |
| New relation with additional predictive content  | <br>   | <br>                     |

**No invented numerical output. No unsupported no-go theorem. No promotion of common-metric consistency into a new relation without demonstrating additional predictive content.**

## 5. Acceptance gate

The next round will be considered complete only when at least one submission supplies a reproducible calculation or a valid mathematical proof that the others can independently audit.

A successful outcome does not have to be a new physical law. A demonstrated degeneracy, a conditional uniqueness result, or a well-scoped mathematical obstruction is valuable if its evidence is traceable.

The immediate objective is to establish whether the reconstruction is identifiable under explicit assumptions—not to prove that the universe has a hidden energy ledger. This keeps the research on the appropriate physical scale and gives us a reliable result on which to base the next decision.&#x20;
