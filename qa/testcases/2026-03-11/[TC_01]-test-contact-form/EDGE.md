---
title: Edge
updated_at: 2026-03-11T00:00:00Z
status: todo
type: edge
---

## Precondition

- *(e.g. Boundary: exactly 2h since last touch, or value exactly at threshold)*
- *(e.g. Unusual but valid: empty optional field, or multiple events same contact)*
- *(add more as needed for this edge scenario)*

## Test cases

### TC-E1. Optional fields empty (still valid)

**Scenario:** Given the contact form allows optional fields, when the user submits with optional fields empty, then submission still succeeds and stored payload is correct.

| # | Action | Expected | Result | Note |
|---|--------|----------|--------|------|
| 1 | Leave optional fields blank; fill required fields with valid data. | Submit is enabled; no validation errors for optional fields. | todo | |
| 2 | Submit the form. | Success confirmation shown; backend accepts request. | todo | |
| 3 | Verify stored/sent payload. | Optional fields are absent/null as expected; no malformed values. | todo | |

### TC-E2. Double-click / rapid submit (duplicate prevention)

**Scenario:** Given the user can click submit multiple times, when they double-click rapidly, then only one submission is processed and duplicates are prevented.

| # | Action | Expected | Result | Note |
|---|--------|----------|--------|------|
| 1 | Fill form with valid data. | Submit enabled. | todo | |
| 2 | Double-click Submit / submit rapidly. | UI prevents re-submit (disabled/loading) and only 1 request is accepted. | todo | |
| 3 | Verify backend/CRM. | Exactly one lead/contact created (no duplicates). | todo | |
