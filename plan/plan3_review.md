My verdict on Plan3: REVISE, then proceed to implementation. Its architecture and scope are sound. I would keep it as the base rather than reopen the broader design, but I would close several gaps before allowing the coding agent to implement it.

Plan3 correctly centers the reference implementation on the ZEH/LTB research workflow, preserves the frozen-system boundary, applies the growth gate, and limits the work to a small, auditable slice.&#x20;

plan3.md



## What Plan3 did right

1\. It correctly separates the scientific goal from the infrastructure goal.

The objective is not to solve the LTB theorem in Go. It is to demonstrate how Phys can faithfully represent a problem, assumptions, claims, derivations, evidence, and unresolved proof obligations. The science remains open without invalidating the reference implementation.

2\. It respects the architectural boundary.

`phys` and `phys-gr` remain frozen; new work belongs in the current architecture. Its growth-gate criteria also guard against adding mathematical primitives simply to make a demo work.

3\. It includes meaningful adversarial verification.

Premise linkage, independent goldens, anti-goldens, stale-evidence detection, replay, and verification coverage are the right kinds of tests. These reflect the actual lessons of the `phys-lib/bohm/minisuperspace` reference rather than treating a passing test as a proof.

4\. It keeps the EdS baseline conditional on the available capabilities.

The \\(Q\_{\mathcal D}=0\\) homogeneous baseline is useful reference material, but the plan does not demand that the infrastructure pretend to support spatial averaging if it cannot faithfully represent and verify it.

## What I would correct before coding

### 1. Correct the epistemic status of Q-02

Plan3 labels Q-02 “conditional.” That is ambiguous and could be interpreted as an established conditional theorem.

Use an explicit status such as candidate construction — incomplete; exact analytic existence and admissibility unproved. Keep Q-03, the backreaction non-identifiability theorem, explicitly conjectural/open.

Q-01 should likewise be recorded as a background literature claim whose sources and applicability require verification, not as an unquestioned premise.

### 2. Treat `plan2_z.md` as a research draft, not verified evidence

Plan3 calls it the strongest source, which is reasonable as a prioritization decision. However, the source itself describes its proposed Phys artifacts and tests as unexecuted, with no canonical workspace specification available during that work.&#x20;

plan2_z(2).md



Therefore, its claimed propositions and series expansions must be independently checked before being promoted to verified mathematical results. Preserve them as sourced claims, candidate derivations, or open obligations according to the actual evidence.

### 3. Resolve the open decisions through explicit implementation rules

Plan3 leaves the package path, Q-04 scope, Lemma B scope, and new mathematical primitives versus documentation-only gaps open.&#x20;

plan3.md



Do not leave these as an indefinite planning phase. Determine the package boundary from the live architecture; keep LTB-specific semantics in the appropriate GR package, and keep workflow coordination in PhysTrace only where its actual contract supports it. Default to excluding Q-04 from this first slice, because it is a separate research branch.

### 4. Name the proof obligations precisely

O1–O7 should each have a stable identifier, a concrete statement of what remains unresolved, the associated claim, and the evidence that would discharge it. At minimum, preserve:

- Exact matching of \\(D_A(z)\\).
- Vertex regularity and analytic existence.
- Admissibility and off-cone extension.
- The backreaction response and a valid nonzero distinguishing result.
- Remainder control for the perturbative route.
- The prior-art and novelty audit.

These are documentation and verification targets for the reference artifact—not instructions for the coding agent to prove the physics.

### 5. Make claim-state integrity testable

A test that merely checks that Q-03 is initially marked open is too weak. Where existing capabilities permit, test that unsupported evidence cannot justify promoting it to “proved.”

Do not invent a new state machine solely for this fixture. If the existing artifact model cannot enforce such a transition, record the limitation and demonstrate that the unresolved status is faithfully preserved.

There are two additional scientific details worth preserving explicitly: distinguish the area radius \\(R=D_A\\) on the central observer's light cone from any rescaled distance notation, and state normalization assumptions rather than silently incorporating them into the model class. Both are known hazards in the current research draft.

## The instruction I would return to the coding agent

Revise Plan3 with the following corrections, then proceed to implementation without reopening the overall architecture.

1. Classify Q-02 as an incomplete candidate construction, not an established conditional result. Keep Q-03 as an open conjecture. Treat `plan2_z.md` as the strongest candidate research draft, not as verified mathematical evidence; independently check every mathematical claim before recording it as established.
2. Resolve the package path and responsibility boundaries using the live workspace and package-local contracts. Keep the ZEH/LTB fixture specific to the GR/LTB model, and do not introduce generic research abstractions unless they pass the growth gate. Exclude Q-04 from the initial implementation; preserve it as a deferred research branch.
3. Give O1–O7 stable identities and explicit descriptions of their open mathematical obligations, links to affected claims, and required discharge evidence. Preserve the exact-distance, vertex-regularity, admissibility, off-cone extension, backreaction-variation, remainder-control, and prior-art obligations.
4. Make the formal claim status and its evidence auditable. Test that Q-03 remains unresolved and, if supported by the existing architecture, that unsupported evidence cannot promote it to a proved result. If that enforcement is unavailable, document the exact gap rather than inventing a state machine.
5. Keep the EdS (Q\_{\mathcal D}=0) baseline only to the extent that the existing representation faithfully supports its premises and averaging semantics. Distinguish structural validation, executed operations, replay, mathematical proof, physical interpretation, and empirical evidence.
6. Deliver the smallest coherent, tested vertical slice. Do not modify `phys` or `phys-gr`. Do not expand into solving the LTB inverse problem, building a numerical solver, or implementing a generic ontology. Run the applicable tests and report exact commands, actual results, representation gaps, and remaining proof obligations.

## Final assessment

I would not restart Plan3 or request another broad design exercise. The underlying direction is correct. These corrections close the gaps between its intent and executable requirements.

The implementation should answer one practical question: can Phys preserve a real scientific investigation from its problem definition through its assumptions, candidate derivations, evidence, and unresolved theorem—without turning a conjecture into a proof merely because the software validates it?

That is the right reference milestone. The LTB theorem can remain open while the formalization workflow becomes demonstrably useful.