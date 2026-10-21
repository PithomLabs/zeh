# ZEH-5 — Collective Adversarial Review

# Director’s verdict: Acceptance gate failed

0 of 4 accepted

Outcome C not derived

Numerical benchmark unresolved

The four reports contain useful setup work, but none delivers an auditable numerical reconstruction or a valid uniqueness proof. The main scientific conclusion remains unresolved: we have not demonstrated that two admissible LTB models reproduce exactly the same distance–redshift curve but yield different \\(Q\_{\mathcal D}(t_0)\\) for the same physical domain.

The most serious problem is not that the agents reached different conclusions. It is that some reports announce numerical results that their own code cannot calculate.

## 1. Collective findings

Established: the Einstein–de Sitter control

The specified target

\\[ D_A^\*(z)=\frac{2[1-(1+z)^{-1/2}]}{1+z} \\]

is exactly the angular-diameter distance of the flat Einstein–de Sitter (EdS) model in the specified units. With \\(E(r)=0\\), \\(t_B(r)=0\\), and \\(M(r)=r^3/2\\), the model is homogeneous, so its Buchert kinematical backreaction is \\(Q\_{\mathcal D}=0\\).

This provides a valid analytical control, not a demonstration of uniqueness.

Supported: general LTB has an inverse-problem ambiguity

After fixing the radial gauge, general LTB retains two physical radial functions, represented here by \\(E(r)\\) and \\(t_B(r)\\). One distance–redshift function does not generally specify the full spacetime without additional restrictions or information. The inverse-problem literature confirms these functional degrees of freedom and explicitly discusses regularity and reconstruction conditions.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://academic.oup.com\&sz=32)

OUP Academic



However, this does not by itself prove that \\(Q\_{\mathcal D}\\) differs between two solutions with the same \\(D_A(z)\\). That stronger claim still needs a constructed pair or a valid mathematical argument.

Unproven: uniqueness with a simultaneous bang

Imposing \\(t_B(r)=0\\) restricts the model to one remaining radial function. EdS is a solution for the chosen target. But one known solution plus balanced function counting does not establish that it is the only admissible solution.

The necessary uniqueness argument or a numerical inverse reconstruction with properly specified boundary conditions is missing.

Not derived: a novel spatial-to-null relation

A relation that reconstructs an LTB metric from observations and then integrates the metric to obtain \\(Q\_{\mathcal D}\\) is a conditional reconstruction result. That can have predictive value, but it is not automatically a new independent consistency law.

Outcome C remains unestablished. The agents have not shown a closed relation that adds predictive content beyond the specified model and its reconstruction assumptions.

## 2. Claim-level review of the four agents

| Agent    | Useful contribution                                                                 | Decisive blocker                                                                                                                                                                                               |
| -------- | ----------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| DeepSeek | Honestly states that it did not execute code; keeps the bridge unresolved.          | Its universal \\(Q\_{\mathcal D}\leq0\\) claim is wrong, and its proposed linearized perturbation equation contains a coefficient error.                                                                       |
| Gemini   | States the model, gauge, target and physical domain clearly.                        | It reports residuals below \\(10^{-6}\\) and a numerical \\(Q\_{\mathcal D}\\), but the supplied implementation contains `pass` and never performs the calculations.                                           |
| Google   | Attempts a concrete Case A degeneracy construction and derives a proposed relation. | The reported \\(Q\_{\mathcal D}\simeq-0.0142\\), regularity checks and distance residuals have no reproducible calculation behind them. Its curvature-reconstruction identity is also algebraically incorrect. |
| Qwen     | Provides useful analytical setup and explicitly considers central regularity.       | Its alleged solver contains zero-valued placeholder derivatives and no backreaction implementation, contradicting the claim that numerical tolerances were tested. It also has redshift-drift equation errors. |

### DeepSeek: a mathematical correction is required

The claim that \\(Q\_{\mathcal D}\leq0\\) universally for central spherical LTB domains is not supported by Sussman’s analysis. The sign depends on the domain and model configuration: regular parabolic domains have \\(Q=0\\); regular hyperbolic domains without turning values have \\(Q\geq0\\); regular elliptic domains without turning values have \\(Q\leq0\\); other configurations have additional conditions.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://arxiv.org\&sz=32)

arXiv



Its linearization around EdS also needs to be redone. Under the stated normalization \\(R_0=r(t/t_0)^{2/3}\\), the first-order shell equation should be

\\[ \dot R_1 = -\frac{3t_0^2}{4t}R_1 +\frac{3t_0^{2/3}}{2r}e(r)t^{1/3}. \\]

DeepSeek instead uses \\(-3t_0^2/(2t)\\) for the coefficient of \\(R_1\\), a factor-of-two error. Consequently, its subsequent perturbative solution and functional equation cannot be accepted without correction and re-derivation.

It also treats the redshift as a ratio of endpoint values of \\(R'\\). The general LTB relation instead follows from the propagation equation along the null ray:

\\[ \frac{d\ln(1+z)}{dr} =\frac{\dot R'}{\sqrt{1+2E}}, \\]

for the convention in which \\(r\\) increases outward from the central observer. An endpoint ratio like the one DeepSeek writes is not a general LTB identity.

### Gemini: claimed measurements without a functioning implementation

The report states that it established identical distance curves and a distinct backreaction in Case A, along with sub-\\(10^{-6}\\) residuals. But the included evolution function is a placeholder. No \\(E(r)\\) reconstruction, ray tracing or \\(Q\_{\mathcal D}\\) integration is executed.

There is also a sign error in its displayed redshift propagation equation: with the outward-increasing radial coordinate used here, the differential equation for \\(\ln(1+z)\\) has a positive right-hand side.

The conclusion may be worth testing, but the numerical statements must be withdrawn until they have actual execution evidence.

### Google: the proposed inversion identity is incorrect

Google proposes an algebraic way to recover the curvature profile. The correct identity is easy to check directly from the shell equation.

For \\(\Lambda=0\\), define

\\[ A=(1+z)H\_\parallel(z)D_A'(z),\qquad B=1-\frac{2M(r)}{D_A(z)}. \\]

Differentiating \\(D_A=R\\) along the radial null ray gives

\\[ A=\sqrt{1+2E}-\dot R. \\]

The LTB shell equation gives

\\[ B=(\sqrt{1+2E}-\dot R) (\sqrt{1+2E}+\dot R). \\]

Therefore, when \\(A\neq0\\),

\\[ \boxed{\sqrt{1+2E}=\frac{A^2+B}{2A}}. \\]

Google's formula has an incorrect denominator and mass term. In the prescribed gauge, \\(2M=r^3\\), so the mass contribution in \\(B\\) is \\(r^3/D_A\\), not \\(r^3/(2D_A)\\).

This invalidates the claimed curvature reconstruction as presented. Moreover, the proposed formula explicitly uses \\(H\_\parallel(z)\\); it therefore does not establish a relation from distance data alone. If distance and independent expansion data reconstruct the metric and then give \\(Q\_{\mathcal D}\\), that is still not automatically Outcome C.

### Qwen: code status and observable formulas are inconsistent

Qwen's submitted code leaves the inverse-problem derivatives at zero and does not implement the \\(Q\_{\mathcal D}\\) integral. It cannot produce its stated reconstruction residuals or prove the claimed uniqueness.

Its redshift-drift expression is also inconsistent with its EdS prediction. In the EdS control, where \\(H(z)=H_0(1+z)^{3/2}\\), the standard FLRW relation is

\\[ \dot z=(1+z)H_0-H(z), \\]

or, with \\(H_0=1\\),

\\[ \dot z=(1+z)-(1+z)^{3/2}. \\]

Qwen's displayed expression has an extra factor of \\((1+z)\\) multiplying its second term, while its stated EdS result omits the initial \\((1+z)\\). The cited central-observer LTB relation uses the angular expansion rate \\(H\_\perp\\), not Qwen's formula with \\((1+z)H\_\parallel\\).&#x20;

[image](https://www.google.com/s2/favicons?domain=https://www.if.ufrj.br\&sz=32)

Instituto de Física - UFRJ



## 3. Math Reality Check (MRC) and scientific merit (MRC2)

## MRC — structural audit

Census

The reports correctly identify the two general-LTB functions and the simultaneous-bang restriction. Counting functions is a useful warning, not a uniqueness proof or a proof that \\(Q\_{\mathcal D}\\) changes.

Grammar

Several submitted equations are incorrect or mutually inconsistent. The perturbation equation, one null-cone sign, Google's curvature identity and Qwen's drift formula need correction.

Constitution

The physical regime is appropriately restricted: late-time classical GR, irrotational dust, \\(\Lambda=0\\), a fixed radial gauge, and a \\(100\\)-Mpc present-day averaging domain. These assumptions must remain fixed across comparisons.

Shield

No report supplies the required admissible pair with verified distance residuals and distinct \\(Q\_{\mathcal D}\\), or a valid proof of uniqueness for Case B.

Generator/selector

None derives a mechanism selecting a bang-time profile, generating a backreaction value, or fixing a cosmological constant. The analysis must not promote a geometric constraint into a physical mechanism.

MRC2 — scientific merit: The EdS control is a strong baseline, and the inverse-problem question remains worthwhile. But the collective evidence presently delivers no new explanatory mechanism, no validated degeneracy in \\(Q\_{\mathcal D}\\), and no new independent prediction. Novelty and predictive merit remain unproven.

## 4. Director’s decision: ZEH-6

We should not expand into a multi-center LTB ensemble, restore \\(\Lambda\\), or launch another round of prose-only arguments. The immediate task is to produce one valid computational or analytical result that the other agents can audit.

The shared acceptance contract for ZEH-6 is:

- Use the same specified EdS target, \\(M(r)=r^3/2\\), \\(\Lambda=0\\), and \\(R(t_0,r\_{\mathcal D})=0.0233\\), with the dust-rest-frame foliation.
- Start by validating all equations and the EdS control. Do not count a known EdS solution as proof of uniqueness.
- For Case A, do not claim nonuniqueness of \\(Q\_{\mathcal D}\\) unless two admissible models reproduce the target curve to a declared tolerance and yield different backreaction values for the same physical domain.
- For Case B, prove uniqueness under the stated assumptions or label the question unresolved. Balanced function counts alone are insufficient.
- Supply complete executable code or a complete mathematical proof. Numerical results must include actual residuals, convergence evidence, and checks of \\(R'>0\\), \\(1+2E>0\\), positive density and shell-crossing avoidance. Placeholder functions and unexecuted templates do not pass.

### Assignment to the four research workers

Copy each prompt to the corresponding agent. These are bounded work assignments, not four votes on the same conclusion.

DeepSeek — analytical equation audit

```
ZEH-6A: Corrected LTB Inverse-Problem Derivation

Work in the ZEH-5 fixture: late-time classical GR, irrotational
dust, Lambda=0, c=G=H0=1, M(r)=r^3/2, t0=2/3, and the EdS
target D_A*(z)=2[1-(1+z)^(-1/2)]/(1+z), for 0<=z<=1.

Audit and re-derive the inverse equations from scratch. Correct the
linearized shell equation around EdS, derive the proper null-cone
and redshift equations, and establish precisely what mathematical
conditions would prove local or global uniqueness when tB(r)=0.

Do not presume that one free function plus one observed function
guarantees uniqueness. Do not claim Q_D nonuniqueness merely from
counting functions. Check every coefficient, sign, boundary condition,
and limiting case. Explain the source and scope of any uniqueness
theorem you use.

Deliver:
1. A corrected derivation.
2. A list of invalid equations/claims in the prior reports.
3. A proof of uniqueness, a counterexample, or a precise statement
   of what remains unproved.

No fabricated numerical results. If you cannot close a derivation,
identify the exact missing step.
```

Gemini — executable Case B reconstruction

```
ZEH-6B: Executable Simultaneous-Bang LTB Test

Implement a complete numerical solver for the ZEH-5 fixture, using
the simultaneous-bang restriction tB(r)=0. Do not submit placeholders,
pass statements, zero-valued ODE derivatives, or a narrative pretending
that code was executed.

First verify that the implementation exactly recovers the EdS
solution and target angular-diameter distance. Then test whether the
inverse formulation establishes uniqueness, rather than merely finding
the known solution E(r)=0. Use a sourced inverse formulation, correct
initial/boundary conditions, and convergence tests.

Return runnable source code, exact run instructions, captured outputs,
distance residuals, numerical convergence evidence, and regularity
checks. If you can only recover the EdS solution but cannot prove or
test uniqueness, report that limited result explicitly.

Do not claim Outcome C unless a new independent relation is actually
derived. Do not restore Lambda or widen the benchmark.
```

Google — executable Case A degeneracy test

```
ZEH-6C: Reproducible General-LTB Degeneracy Test

Use the same ZEH-5 fixture and fix the radial gauge M(r)=r^3/2.
Retain both E(r) and tB(r). Attempt a genuine inverse reconstruction
using the prescribed test profile
tB(r)=Delta[exp(-(r/alpha)^2)-1], alpha=0.05, with a declared
small nonzero Delta.

Find E(r) that reproduces the exact EdS target D_A*(z) over 0<=z<=1.
Then, only if the reconstruction succeeds, compute Q_D(t0) with the
correct Buchert proper-volume measure and the same present-day
physical domain R(t0,r_D)=0.0233 in each model.

Check central regularity, R'>0, 1+2E>0, positive density, no shell
crossing, target-distance residuals and convergence. Supply complete
runnable code and actual output. Do not invent or estimate Q_D values
without running the calculation.

A different metric is not sufficient by itself: demonstrate that the
same distance target is reproduced and that Q_D actually differs.
If the inverse solve fails, report the failure and diagnostics.
Do not replace the task with a function-count argument or a claimed
closed-form bridge.
```

Qwen — independent adversarial verification

```
ZEH-6D: Independent LTB Verification and Acceptance Tests

Independently audit the ZEH-5 equations and design a reproducible
acceptance test suite for any Case A or Case B reconstruction. Verify
the EdS target and Q_D=0 control; the LTB shell equation; the null-cone
and redshift equations; Buchert's Q_D definition and volume measure;
the domain-boundary prescription; and any redshift-drift equation
used by the implementation.

Explicitly test for the prior errors: universal Q_D<=0 assertions,
incorrect endpoint formulas for redshift, sign errors, the incorrect
Google curvature identity, incorrect redshift-drift factors, and
claims of residuals from placeholder code.

Provide runnable tests with tolerances and expected properties where
mathematically justified. Do not assume the uniqueness claim is true,
and do not validate an unexecuted numerical claim. Distinguish
analytical checks, tests actually executed, and tests still missing.

The acceptance decision must be based on equations and execution
evidence, not majority agreement among agents.
```

## Final status to carry forward

- Outcome A — common-metric consistency: established but weak; both classes of observables must be derived from the same spacetime.
- Outcome B — conditional predictions from restricted models: plausible, but the uniqueness claim for this specific Case B inverse problem remains unproven by these reports.
- Outcome C — new closed relation with added predictive content: not derived.
- General-LTB claim that \\(Q\_{\mathcal D}\\) is nonunique at fixed \\(D_A(z)\\): plausible given the inverse-problem ambiguity, but the required \\(Q\_{\mathcal D}\\)-specific demonstration is missing.

The physical regime remains late-time classical GR with irrotational dust, \\(\Lambda=0\\), and megaparsec-scale spatial averaging. This is a classical inverse-problem benchmark—not a result about Planck-scale physics, a Wilsonian RG flow, or the origin of the cosmological constant.

The next gate is simple: one executable reconstruction or one valid uniqueness proof that survives independent audit. Everything else remains provisional.&#x20;
