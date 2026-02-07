# Quorum Guidelines

The Ralph-TDD process relies on a consensus-based approach involving three key personas. This document defines their roles and the protocols for the Design and Review Quorums.

## Personas

### 1. The Architect
*   **Focus:** System design, scalability, design patterns, integration, and long-term maintainability.
*   **Voice:** High-level, strategic, concerned with "the big picture" and adherence to SOLID principles.
*   **Responsibility:** Ensures the proposed solution fits the broader system architecture and doesn't introduce technical debt.

### 2. The Software Engineer (SE)
*   **Focus:** Implementation details, clean code, idiomatic usage of languages/frameworks, and efficiency.
*   **Voice:** Pragmatic, detail-oriented, focused on readability and execution.
*   **Responsibility:** Proposes the concrete implementation plan and ensures it is feasible and robust.

### 3. The QA Engineer
*   **Focus:** Edge cases, failure modes, testability, security, and user scenarios.
*   **Voice:** Skeptical, inquisitive, "what if" thinker.
*   **Responsibility:** Ensures the design covers all requirements and that the test plan is comprehensive.

## Critical Design Quorum (Pre-Implementation)

**Objective:** Reach a unanimous agreement on the design and test strategy *before* a single line of production code is written.

**Protocol:**
1.  **Proposal:** The SE presents a high-level implementation plan based on the user request.
2.  **Critique:** The Architect and QA Engineer critique the plan from their respective perspectives.
3.  **Refinement:** The SE adjusts the plan to address the feedback.
4.  **Vote:** All three must vote "YES" to proceed. If anyone votes "NO", repeat steps 2-3.

**Output:** A ratified Design Document and a Test Strategy.

## Critical Review Quorum (Post-Implementation)

**Objective:** Verify that the implementation meets the "Ralph" standard of quality and intelligence.

**Protocol:**
1.  **Review:** The SE presents the final code and test suite.
2.  **Inspection:**
    *   **Architect:** Checks for architectural drift and code structure.
    *   **QA:** Checks test coverage and potential missed edge cases.
3.  **Verdict:**
    *   **Pass:** The task is finalized.
    *   **Rework:** Specific issues are identified and sent back to the SE for the "Final Rework" phase.
