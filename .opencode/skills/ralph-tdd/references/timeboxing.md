# Timeboxing Guidelines

**Version:** 1.0

This document provides time recommendations for each phase of the Ralph-TDD process.

---

## Phase 1: Critical Design Quorum

| Activity | Recommended Duration | Maximum |
|----------|---------------------|---------|
| Initial proposal (SE) | 5-10 min | 15 min |
| Architect critique | 5 min | 10 min |
| QA critique | 5 min | 10 min |
| Refinement rounds | 10 min each | 3 rounds |
| **Total per feature** | **25-45 min** | **60 min** |

### Escalation
If quorum cannot reach agreement within max time:
1. Document unresolved issues
2. Escalate to user for decision
3. Proceed with user's choice

---

## Phase 2: Ralph-Based TDD Loop

### Per Iteration (One Test → Implementation)

| Activity | Recommended Duration |
|----------|---------------------|
| Write failing test (RED) | 5-10 min |
| Verify failure message | 2 min |
| Implement minimal code (GREEN) | 10-20 min |
| Verify pass | 2 min |
| Refactor | 5-10 min |
| Ralph Check | 5 min |
| **Total per iteration** | **29-49 min** |

### Phase 2 Total Estimate
- Small feature (1-3 iterations): 1-3 hours
- Medium feature (4-10 iterations): 3-8 hours
- Large feature (10+ iterations): Plan in chunks

---

## Phase 3: Critical Review Quorum

| Activity | Recommended Duration |
|----------|---------------------|
| Code presentation | 10 min |
| Architect review | 15 min |
| QA review | 15 min |
| Discussion/resolution | 10 min |
| **Total** | **50 min** |

---

## Phase 4: Final Rework

| Activity | Recommended Duration |
|----------|---------------------|
| Address each issue | 15-30 min per issue |
| Re-review quorum | 30 min |
| **Total** | **Per issue + review** |

---

## Daily Workflow Recommendation

```
Session 1 (Morning):
  - Phase 1: Design Quorum for new features
  - Phase 2: First 1-2 TDD iterations

Session 2 (Afternoon):
  - Phase 2: Remaining iterations
  - Phase 3: Review (if complete)
```

---

## Adjusting for Complexity

| Complexity | Design Quorum | TDD Iterations |
|------------|---------------|-----------------|
| Simple (bug fix) | 15 min | 1-2 |
| Medium | 30 min | 3-5 |
| Complex (new system) | 60 min | 10+ |

---

## Warning Signs

- Design Quorum taking > 60 min → Request clarification or simplify scope
- TDD iteration > 60 min → Feature may be too large, break it down
- Multiple rework cycles → Review process needs improvement
