---
name: ralph-tdd
description: Implements features using a rigorous "Ralph" TDD process involving a 3-person design quorum, strict TDD loops, and final critical review. Use for high-stakes or complex feature implementation where quality is paramount.
---

# Ralph-TDD Skill

This skill guides you through the "Ralph" methodology for high-quality software engineering. It enforces a strict separation of design, implementation, and review.

## Phases

### Phase 1: Critical Design Quorum

**Goal:** Establish a ratified design before coding.

1.  **Read Guidelines:** Review [quorum-guidelines.md](references/quorum-guidelines.md) to understand the personas (Architect, SE, QA).
2.  **Simulate Discussion:**
    *   Act as the **Software Engineer** to propose a solution based on the user's request.
    *   Act as the **Architect** to critique the design (focus on patterns, structure).
    *   Act as the **QA Engineer** to critique the testability and edge cases.
3.  **Iterate:** Refine the plan until all three personas agree.
4.  **Output:** Present the final **Ratified Design Plan** to the user for approval.

### Phase 2: Ralph-Based TDD Loop

**Goal:** Implement the ratified design using strict TDD.

1.  **Read Workflow:** Review [tdd-workflow.md](references/tdd-workflow.md).
2.  **Execute Loop:** For each component/feature in the plan:
    *   **RED:** Write a failing test. verify failure.
    *   **GREEN:** Write minimal code to pass.
    *   **REFACTOR:** Clean up.
    *   **RALPH CHECK:** Verify elegance and robustness.
3.  **Progress:** Use the `write_todos` tool to track the implementation steps.

### Phase 3: Critical Review Quorum

**Goal:** Final quality gate.

1.  **Review:** Once implementation is complete, simulate the Quorum again.
2.  **Critique:**
    *   **Architect:** Review for drift from the original design and code quality.
    *   **QA:** Review the comprehensive test suite coverage.
3.  **Decision:**
    *   If issues are found, move to Phase 4.
    *   If unanimous approval, the task is complete.

### Phase 4: Final Rework (If needed)

1.  Address specific feedback from Phase 3.
2.  Re-run the Review Quorum (Phase 3) until approval is granted.

## Instructions for the Agent

*   **Roleplay:** You must explicitly label your outputs with the persona speaking (e.g., "**[Architect]**: I have a concern about...").
*   **Strictness:** Do not bypass the Quorum steps. Do not start coding until the Design Quorum is complete and the user has approved the plan.
*   **Verification:** Always run tests after every change in the TDD loop.
