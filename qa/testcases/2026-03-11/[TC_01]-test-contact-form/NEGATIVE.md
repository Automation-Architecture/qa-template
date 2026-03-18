---
title: Negative
updated_at: 2026-03-11T00:00:00Z
status: todo
type: negative
---

## Precondition

- *(e.g. Invalid or missing data: contact with sms_opt_out = true, or malformed payload)*
- *(e.g. System state: API returns 4xx, or duplicate event ID already processed)*
- *(add more as needed for this negative scenario)*

## Test cases

### TC-N1. Missing required field(s) → validation error (no submit)

**Scenario:** Given required fields exist on the form, when the user submits with a required field missing/invalid, then validation blocks submission and no backend request is processed.

| # | Action | Expected | Result | Note |
|---|--------|----------|--------|------|
| 1 | Leave a required field empty (e.g. email). | Inline validation shows error; submit disabled or blocks on click. | todo | |
| 2 | Attempt to submit. | No successful submission; no lead created; error message is clear. | todo | |

### TC-N2. Backend returns error → user sees failure and no duplicate side effects

**Scenario:** Given the backend fails (4xx/5xx), when the user submits valid data, then the UI shows a failure state and no duplicate lead/contact is created on retries.

| # | Action | Expected | Result | Note |
|---|--------|----------|--------|------|
| 1 | Submit valid data while backend is forced to 500 (or simulate offline). | UI shows error; submission not marked successful. | todo | |
| 2 | Retry submission once backend recovers. | Exactly one successful submission is processed; no duplicates from the failed attempt. | todo | |
