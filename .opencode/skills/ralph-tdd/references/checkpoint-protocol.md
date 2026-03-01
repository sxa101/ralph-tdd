# Checkpoint Protocol

This document defines the session persistence protocol for the Ralph-TDD skill.

## Overview

Checkpoint files allow the Ralph-TDD process to continue across multiple sessions. They store the minimum context needed to resume work without losing design decisions or implementation progress.

## Checkpoint Files

All checkpoints are stored in `.ralph/` directory at the project root:

```
project-root/
└── .ralph/
    ├── PLAN.md           # Design and phase tracking
    ├── STATUS.md         # TDD iteration progress
    └── IMPLEMENTATION.md # Decisions and notes
```

## Session Lifecycle

### 1. Session Start

When a session begins:

1. Agent checks for `.ralph/` directory
2. If exists, read all three `.md` files
3. Parse and validate content
4. If valid: restore context, greet user with resume summary
5. If missing: start fresh (no checkpoint files)
6. If corrupted: log warning, start fresh

**Resume summary example:**
> "Resuming session from [date]. Last phase: Phase 2 (TDD Loop). Next: Implement component X."

### 2. During Session

After completing each phase, update checkpoint files:

| Phase | Update File | Content |
|-------|-------------|---------|
| Phase 1 (Design Quorum) | PLAN.md | Ratified design, approval signatures |
| Phase 2 (TDD Loop) | STATUS.md, IMPLEMENTATION.md | Iteration count, completed components, test results |
| Phase 3 (Review Quorum) | STATUS.md | Review verdict, any rework items |
| Phase 4 (Final Rework) | STATUS.md | Completion status |

### 3. Session End

- No explicit save required
- Files persist in `.ralph/`
- User can end session at any checkpoint

### 4. Resume Request

User can explicitly request resume:
- "resume" / "continue" / "pick up where we left off"
- Agent reads checkpoints and restores context

## Validation Rules

1. **Missing files:** OK - start fresh
2. **Corrupted markdown:** Log warning, start fresh
3. **Stale data (>7 days):** Warn user, offer to start fresh
4. **No session ID match:** Accept (single-user assumption)

## Security

- **DO NOT** store API keys, passwords, or secrets
- **DO NOT** store sensitive file contents
- Checkpoint files may be committed to version control (they're documentation)

## Manual Intervention

Users can:
- Delete `.ralph/` to start fresh
- Edit files manually (agent will read current state)
- Use version control to restore previous checkpoints

## Migration

If checkpoint format changes:
1. Old format is read with best-effort parsing
2. Missing fields default to empty/fresh
3. No automatic migration needed
