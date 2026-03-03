---
name: ralph-tdd
description: Implements features using a rigorous "Ralph" TDD process involving a 3-person design quorum, strict TDD loops, and final critical review. Use for high-stakes or complex feature implementation where quality is paramount.
---

# Ralph-TDD Skill

This skill guides you through the "Ralph" methodology for high-quality software engineering. It enforces a strict separation of design, implementation, and review, with mandatory file-based checkpoints for persistence.

## The Ralph Personas

1.  **The Architect:** Focuses on system design, scalability, patterns, and adherence to SOLID principles.
2.  **The Software Engineer (SE):** Focuses on clean, idiomatic implementation, readability, and execution.
3.  **The QA Engineer:** Focuses on edge cases, failure modes, testability, and "what if" scenarios.

---

## Phase 1: Critical Design Quorum (Pre-Implementation)

**Goal:** Establish a ratified design and test strategy before coding.

1.  **Simulate Discussion:** Explicitly label outputs with the persona speaking (e.g., "**[Architect]**: ...").
    *   **SE:** Proposes a solution and a test plan.
    *   **Architect:** Critiques the design (patterns, structure, debt).
    *   **QA:** Critiques testability and identifies edge cases.
2.  **Iterate:** Refine until all three personas vote "YES".
3.  **Checkpoint (MANDATORY):** Write the final **Ratified Design Plan** and **Test Strategy** to `RALPH_DESIGN.md` in the project root.
4.  **User Approval:** Present the plan to the user and wait for approval before proceeding.

## Phase 2: Ralph-Based TDD Loop (Implementation)

**Goal:** Implement the ratified design using strict, high-IQ TDD.

1.  **Checkpoint (MANDATORY):** Create `RALPH_STATUS.md` in the project root. Use this file to track all implementation steps and current status (Todo/Doing/Done).
2.  **Execute the Loop:** For each component defined in `RALPH_DESIGN.md`:
    *   **RED:** Write a failing test. Verify it fails for the expected reason.
    *   **GREEN:** Write minimal, correct code to pass the test.
    *   **REFACTOR:** Apply SOLID principles, remove duplication, and improve naming.
    *   **RALPH CHECK (The "High IQ" Audit):**
        *   Is this the most efficient and elegant solution?
        *   Is the code resilient and consistent with project standards?
        *   If "No" to any, return to **REFACTOR**.
3.  **Verification:** Run the full test suite after every "Ralph Check". Update `RALPH_STATUS.md` after each loop iteration.

## Phase 3: Critical Review Quorum (Post-Implementation)

**Goal:** Final quality gate to ensure the "Ralph" standard is met.

1.  **Review:** Simulate the Quorum again to inspect the final code and tests.
    *   **Architect:** Checks for architectural drift and code structure.
    *   **QA:** Verifies comprehensive coverage of all edge cases.
2.  **Verdict:**
    *   **Pass:** Finalize the task.
    *   **Rework:** Identify specific issues and move to Phase 4.

## Phase 4: Final Rework (If needed)

1.  Address feedback from Phase 3.
2.  Update `RALPH_STATUS.md` and re-run the Review Quorum (Phase 3) until unanimous approval.

---

## Instructions for the Agent

*   **Roleplay:** Always maintain the three-persona dialogue during Quorums.
*   **Persistence:** Use `RALPH_DESIGN.md` and `RALPH_STATUS.md` as the "source of truth" for the current state. Read these files upon resuming a task.
*   **Strictness:** Never bypass a Phase or a Checkpoint. Verification via testing is mandatory.
