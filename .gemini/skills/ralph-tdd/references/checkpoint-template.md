# Checkpoint File Templates

This document provides templates for Ralph-TDD checkpoint files.

---

## PLAN.md Template

```markdown
# Ralph-TDD Plan

**Session ID:** {{uuid}}
**Created:** {{ISO8601 timestamp}}
**Updated:** {{ISO8601 timestamp}}

---

## Current Phase

- Phase: {{1|2|3|4}}
- Phase Status: {{in_progress|completed|pending}}

---

## Ratified Design

### Problem Statement
{{One-paragraph description of the problem}}

### Goals
- {{Goal 1}}
- {{Goal 2}}

### Non-Goals
- {{Non-goal 1}}

---

## Technical Design

### Architecture
{{High-level architecture}}

### Components
| Component | Status |
|-----------|--------|
| {{Component}} | {{pending|implemented|reviewed}} |

---

## Next Steps

1. {{Immediate next action}}
2. {{Following action}}

---

## Approval

| Persona | Name | Date | Vote |
|---------|------|------|------|
| Architect | | | YES/NO |
| Software Engineer | | | YES/NO |
| QA Engineer | | | YES/NO |
```

---

## STATUS.md Template

```markdown
# Ralph-TDD Status

**Session ID:** {{uuid}}
**Updated:** {{ISO8601 timestamp}}

---

## Session Info

- **Current Phase:** {{1|2|3|4}}
- **Phase Status:** {{in_progress|completed}}
- **TDD Iterations:** {{count}}

---

## Phase 1: Design Quorum

- **Status:** {{pending|in_progress|completed}}
- **Completed:** {{ISO8601 timestamp}}

---

## Phase 2: TDD Loop

- **Status:** {{pending|in_progress|completed}}
- **Iterations Completed:** {{count}}
- **Current Component:** {{component name}}

### Components
| Component | Tests | Status |
|-----------|-------|--------|
| {{name}} | {{passing/failing}} | {{pending|implemented|reviewed}} |

---

## Phase 3: Critical Review

- **Status:** {{pending|in_progress|completed}}
- **Verdict:** {{PASS|REWORK}}

---

## Phase 4: Final Rework

- **Status:** {{pending|in_progress|completed}}
- **Issues Addressed:** {{count}}

---

## Overall Status

- **Complete:** {{yes|no}}
- **Last Checkpoint:** {{ISO8601 timestamp}}
```

---

## IMPLEMENTATION.md Template

```markdown
# Ralph-TDD Implementation Notes

**Session ID:** {{uuid}}
**Updated:** {{ISO8601 timestamp}}

---

## Important Decisions

### {{Decision title}}
- **Date:** {{ISO8601 timestamp}}
- **Context:** {{Why this decision was needed}}
- **Decision:** {{What was decided}}
- **Rationale:** {{Why this is the right choice}}

---

## Code Changes Summary

### {{Component name}}
- **Files modified:** {{list of files}}
- **Tests added:** {{count}}
- **Notes:** {{implementation notes}}

---

## Test Results

| Component | Tests | Pass | Fail |
|-----------|-------|------|------|
| {{name}} | {{count}} | {{count}} | {{count}} |

---

## Open Questions

- {{Question 1}}
- {{Question 2}}

---

## Notes

{{Additional implementation notes. Do NOT include secrets or API keys.}}
```

---

## Usage Notes

1. **Session ID:** Generate UUID for each new session
2. **Timestamps:** Use ISO8601 format (e.g., `2026-03-01T10:30:00Z`)
3. **No Secrets:** Never store API keys, passwords, or credentials
4. **Keep Current:** Update files after each phase/iteration
5. **Human Readable:** These files are for both agent and human review
