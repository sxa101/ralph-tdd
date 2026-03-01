# Ralph-TDD Skill

A specialized skill that implements features using a rigorous "Ralph" Test-Driven Development (TDD) process. This process involves a 3-person design quorum, strict TDD loops, and a final critical review to ensure the highest quality of code and design.

## Features

- **Critical Design Quorum:** Simulate a discussion between an Architect, a Software Engineer, and a QA Engineer to ratify a design before implementation.
- **Ralph-Based TDD Loop:** A strict Red-Green-Refactor-Ralph cycle for implementation.
- **Critical Review Quorum:** A final quality gate involving the three personas to approve the completed work.

## Usage

### OpenCode

```bash
/skill ralph-tdd
```

### Gemini CLI

```bash
activate_skill ralph-tdd
```

### 2. The Process

Once activated, the skill will guide you through the following phases:

#### Phase 1: Critical Design Quorum
The agent will roleplay three personas to design the solution:
- **Architect:** Focuses on system design and patterns.
- **Software Engineer (SE):** Focuses on implementation details and feasibility.
- **QA Engineer:** Focuses on edge cases and testability.

The process iterates until a **Ratified Design Plan** is agreed upon and approved by you.

#### Phase 2: Ralph-Based TDD Loop
Implementation follows a strict TDD cycle:
1. **RED:** Write a failing test and verify failure.
2. **GREEN:** Write minimal code to pass the test.
3. **REFACTOR:** Clean up the code.
4. **RALPH CHECK:** An "elegant audit" to ensure superior quality and resilience.

#### Phase 3: Critical Review Quorum
A final review by the three personas to ensure the implementation matches the design and meets quality standards.

#### Phase 4: Final Rework
If any issues are found during the Review Quorum, they are addressed and re-reviewed.

## File Structure

- `SKILL.md`: The skill definition and instructions.
- `references/quorum-guidelines.md`: Detailed protocols for the Design and Review Quorums.
- `references/tdd-workflow.md`: Detailed steps for the Ralph-Based TDD Loop.