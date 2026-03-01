---
name: ralph-tdd
description: Implements features using a rigorous "Ralph" TDD process involving a 3-person design quorum, strict TDD loops, and final critical review. Use for high-stakes or complex feature implementation where quality is paramount.
---

# Ralph-TDD Skill

This skill guides you through the "Ralph" methodology for high-quality software engineering. It enforces a strict separation of design, implementation, and review.

## Reference Documents

| Document | Purpose |
|----------|---------|
| [quorum-guidelines.md](references/quorum-guidelines.md) | Personas and quorum protocols |
| [tdd-workflow.md](references/tdd-workflow.md) | TDD loop instructions |
| [design-document-template.md](references/design-document-template.md) | Design doc format |
| [test-strategy-template.md](references/test-strategy-template.md) | Test plan format |
| [exit-criteria.md](references/exit-criteria.md) | Phase completion requirements |
| [sample-quorum.md](references/sample-quorum.md) | Example discussions |
| [timeboxing.md](references/timeboxing.md) | Duration guidelines |

## Phases

### Phase 1: Critical Design Quorum

**Goal:** Establish a ratified design before coding.

1.  **Clarify:** If user request is ambiguous, ask clarifying questions before proceeding.
2.  **Read Guidelines:** Review [quorum-guidelines.md](references/quorum-guidelines.md) to understand the personas.
3.  **Simulate Discussion:**
    *   Act as the **Software Engineer** to propose a solution.
    *   Act as the **Architect** to critique the design.
    *   Act as the **QA Engineer** to critique testability and edge cases.
4.  **Iterate:** Refine until unanimous approval.
5.  **Output:** Present the **Ratified Design Plan** using [design-document-template.md](references/design-document-template.md).

**Checkpoint:** Verify against [exit-criteria.md](references/exit-criteria.md) before proceeding.

### Phase 2: Ralph-Based TDD Loop

**Goal:** Implement the ratified design using strict TDD.

1.  **Read Workflow:** Review [tdd-workflow.md](references/tdd-workflow.md).
2.  **Execute Loop:** For each component/feature:
    *   **RED:** Write failing test. Verify failure message.
    *   **GREEN:** Write minimal code to pass.
    *   **REFACTOR:** Clean up.
    *   **RALPH CHECK:** Verify elegance.
3.  **Track Progress:** Use `write_todos` to track iterations.

**Checkpoint:** Run tests after each iteration. Verify against exit criteria.

### Phase 3: Critical Review Quorum

**Goal:** Final quality gate.

1.  **Review:** Simulate the Quorum again.
2.  **Critique:**
    *   **Architect:** Check for design drift.
    *   **QA:** Check test coverage (minimum: happy path + 2 negative cases).
3.  **Decision:**
    *   Issues found → Phase 4.
    *   Unanimous approval → Complete.

**Checkpoint:** Verify against [exit-criteria.md](references/exit-criteria.md).

### Phase 4: Final Rework

1.  Address specific feedback.
2.  Re-run Review Quorum until approval.

---

## Clarification Protocol

If the user request is ambiguous:

1.  **Identify gaps:** What is unclear?
2.  **Ask questions:** Get concrete requirements
3.  **Document assumptions:** State what you're assuming
4.  **Proceed only when clear:** Don't guess at requirements

Example ambiguous requests:
- "Make it faster" → What specifically? By how much?
- "Add validation" → What rules? For what inputs?
- "Improve error handling" → Which errors? What should happen?

---

## Instructions for the Agent

*   **Roleplay:** Label outputs with persona (e.g., "**[Architect]**: ...").
*   **Strictness:** Do not bypass Quorum. Do not code until Design Quorum is approved.
*   **Verification:** Always run tests after TDD changes.
*   **Timeboxing:** Use [timeboxing.md](references/timeboxing.md) as a guide.
