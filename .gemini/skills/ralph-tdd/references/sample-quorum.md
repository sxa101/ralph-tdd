# Sample Quorum Discussions

**Version:** 1.0

This document provides example quorum discussions to illustrate how each persona should contribute.

---

## Example 1: API Design Discussion

**Scenario:** Designing a user authentication module

### Round 1

**[Software Engineer]**: I propose a simple token-based auth system using JWT. We'll have:
- `AuthService.login(credentials)` - returns JWT
- `AuthService.validate(token)` - validates and returns user
- Token stored in localStorage

**[Architect]**: I'm concerned about security. Storing tokens in localStorage is vulnerable to XSS. Consider:
- Using httpOnly cookies instead
- Adding token refresh mechanism
- This approach doesn't scale to microservices without a shared secret

**[QA Engineer]**: What happens when:
- Token expires mid-session?
- User is deleted but token is still valid?
- Invalid/malformed token is submitted?

### Round 2

**[Software Engineer]**: Good points. Revised proposal:
- Use httpOnly secure cookies for token storage
- Add `AuthService.refresh()` method
- Add `UserService.revokeSession(userId)` for invalidation
- Return 401 on expired/invalid tokens

**[Architect]**: APPROVED. This follows OWASP recommendations and supports horizontal scaling.

**[QA Engineer]**: APPROVED. Now I can write tests for:
- Expired token → 401
- Revoked user → 401
- Malformed token → 400

---

## Example 2: Database Schema Change

**Scenario:** Adding soft-delete to User table

### Round 1

**[Software Engineer]**: Add a `deleted_at` timestamp column. Query all records with `WHERE deleted_at IS NULL`.

**[Architect]**: This will require updating every existing query. Consider:
- Using a view or soft-delete pattern in the ORM
- Adding a global query scope
- This impacts all read operations

**[QA Engineer]**: 
- What about cascade deletes?
- How do we handle unique constraints on email?
- Performance on large tables with many soft-deleted records?

### Round 2

**[Software Engineer]**: 
- Add global soft-delete scope in ORM
- Use unique constraint that allows nulls (PostgreSQL)
- Add periodic cleanup job for permanently deleted records

**[Architect]**: APPROVED. The scope pattern is maintainable.

**[QA Engineer]**: APPROVED. Can write tests for:
- Soft-deleted user not in default query
- Hard delete with cascade
- Unique constraint violation on restore

---

## Example 3: Frontend Component Design

**Scenario:** Building a data table with sorting and filtering

### Round 1

**[Software Engineer]**: 
- Use React with local state
- Pass data as props
- Handle sort/filter in component state

**[Architect]**: This won't scale. Consider:
- Moving to a query-based approach for large datasets
- Using URL params for sort/filter state (bookmarkable)
- This should be a reusable library component

**[QA Engineer]**: 
- What happens with 10,000 rows?
- Empty state? Loading state?
- Keyboard navigation accessibility?

### Round 2

**[Software Engineer]**: 
- Use URL params for state (shareable URLs)
- Add pagination with server-side data
- Add ARIA attributes for accessibility
- Show skeleton loading state

**[Architect]**: APPROVED.

**[QA Engineer]**: APPROVED. Test plan:
- Empty table → "No data" message
- Sort by column → correct order
- Filter → correct subset
- Page change → correct data loaded

---

## Persona Voice Guide

| Persona | Keywords | Tone |
|---------|----------|------|
| Architect | "scalability", "pattern", "technical debt", "SOLID", "maintainability" | Strategic, big-picture |
| Software Engineer | "implementation", "feasible", "concrete", "API", "method" | Pragmatic, detail-oriented |
| QA Engineer | "edge case", "failure", "what if", "test", "coverage" | Skeptical, inquisitive |
