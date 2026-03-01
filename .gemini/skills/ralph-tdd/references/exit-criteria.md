# Exit Criteria

**Version:** 1.0

This document defines the requirements that must be met to exit each phase of the Ralph-TDD process.

---

## Phase 1: Critical Design Quorum

### Entry Criteria
- [ ] User request is clearly documented
- [ ] All three personas are available

### Exit Criteria
- [ ] Design document is complete (all sections filled)
- [ ] Test strategy is defined (minimum 3 edge cases per feature)
- [ ] Unanimous YES vote from all three personas
- [ ] No open concerns or unresolved objections

### Partial Approval Handling
- If any persona votes NO, document the specific concern
- Iterate until unanimous approval
- Maximum 3 rounds before escalation

---

## Phase 2: Ralph-Based TDD Loop

### Per Iteration Exit Criteria (RED → GREEN → REFACTOR → RALPH CHECK)
- [ ] Test fails for the expected reason
- [ ] Implementation passes the test
- [ ] Code is refactored (no duplication, clear naming)
- [ ] Ralph Check questions answered:
  - [ ] Is this the most efficient solution?
  - [ ] Is the code resilient to future changes?
  - [ ] Does it handle edge cases gracefully?
  - [ ] Does it meet project standards?

### Phase Exit Criteria
- [ ] All tests pass
- [ ] No regressions in existing tests
- [ ] Code follows project conventions
- [ ] All items from design document implemented

---

## Phase 3: Critical Review Quorum

### Entry Criteria
- [ ] All code is committed
- [ ] All tests pass locally
- [ ] lint/typecheck commands have been run

### Exit Criteria
- [ ] Architect approval: No drift from ratified design
- [ ] QA approval: Comprehensive test coverage
  - [ ] Minimum baseline: happy path + 2 negative cases
  - [ ] Edge cases documented
- [ ] No critical or major issues open

---

## Phase 4: Final Rework (If Needed)

### Exit Criteria
- [ ] All Phase 3 exit criteria met
- [ ] Original objector confirms resolution
- [ ] Re-review quorum passes

---

## Escalation Protocol

If unanimous approval cannot be reached after 3 rounds:

1. **Document the disagreement** - Record the specific objections
2. **Escalate to user** - Present both sides to the user for decision
3. **User decision is final** - Proceed with user's choice
