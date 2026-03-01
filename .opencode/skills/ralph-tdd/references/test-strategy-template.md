# Test Strategy Template

**Version:** 1.0
**Date:** {{date}}
**Related Design:** {{Link to design document}}

---

## 1. Test Scope

### In Scope
- {{Feature/Component 1}}
- {{Feature/Component 2}}

### Out of Scope
- {{Explicitly state what is NOT tested}}

---

## 2. Test Categories

### Unit Tests
| Test Case | Input | Expected Output | Rationale |
|-----------|-------|-----------------|-----------|
| {{TC-001}} | {{Input}} | {{Expected}} | {{Why this matters}} |
| {{TC-002}} | {{Input}} | {{Expected}} | {{Why this matters}} |

### Integration Tests
| Test Case | Input | Expected Output | Rationale |
|-----------|-------|-----------------|-----------|
| {{ITC-001}} | {{Input}} | {{Expected}} | {{Why this matters}} |

### Edge Cases
| Test Case | Input | Expected Output | Rationale |
|-----------|-------|-----------------|-----------|
| {{EC-001}} | {{Edge case}} | {{Expected}} | {{Why this matters}} |
| {{EC-002}} | {{Edge case}} | {{Expected}} | {{Why this matters}} |

---

## 3. Baseline Coverage

**Minimum Requirements:**
- 1 happy path test per feature
- 2 negative/edge case tests per feature
- 3 edge cases as baseline

---

## 4. Test Execution

### Run Order
1. Unit tests
2. Integration tests
3. Manual verification (if needed)

### Success Criteria
- All tests pass
- No regressions
- Code coverage: {{target percentage}}%

---

## 5. Approval

| Persona | Name | Date | Vote |
|---------|------|------|------|
| QA Engineer | | | YES/NO |
| Software Engineer | | | YES/NO |
