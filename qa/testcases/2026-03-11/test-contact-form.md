---
title: Test Contact Form
date: 2026-03-11
tester: Javier
status: in-progress
---

# Test Contact Form

---

## 1. Overview

**Trigger:** UI — Contact form page

Submits user contact data from the form to the backend, creates a lead or contact record, and confirms success to the user.

---

## 2. Loom

**Recording:** This video was recorded live while filling in this test case and running each step. Watch it for a full walkthrough of what happened during the session.

<!-- Paste Loom link here -->

---

## 3. Test Cases

---

### Happy — TC-H

#### TC-H1 — Valid form submit → success + lead created

**Scenario:** Given the user is on the contact page, when they submit a valid form, then the UI confirms success and the backend creates exactly one lead.
**Severity:** P1

- **Step 1** — Open contact form
  - Action: Navigate to contact form page
  - Expected: Form loads with all required fields visible
  - Result:
  - Note:

- **Step 2** — Fill valid data
  - Action: Enter valid name, email, and message
  - Expected: Client-side validation allows submit
  - Result:
  - Note:

- **Step 3** — Submit form
  - Action: Click Submit
  - Expected: Success state shown (toast or message), no error banner
  - Result:
  - Note:

- **Step 4** — Verify backend
  - Action: Check CRM or logs for lead record
  - Expected: Exactly 1 lead created, payload values match, no duplicates
  - Result:
  - Note:

---

### Negative — TC-N

#### TC-N1 — Missing required field blocks submit

**Scenario:** Given required fields exist on the form, when the user submits with a required field missing, then validation blocks submission and no backend request is sent.
**Severity:** P2

- **Step 1** — Leave required field empty
  - Action: Clear email field, keep other fields valid
  - Expected: Inline validation error shown, submit blocked
  - Result:
  - Note:

- **Step 2** — Attempt submit
  - Action: Click Submit with empty required field
  - Expected: No submission, no lead created, error message clear
  - Result:
  - Note:

---

#### TC-N2 — Backend error → failure shown, no duplicate

**Scenario:** Given the backend fails (5xx), when the user submits valid data, then the UI shows a failure state and no duplicate lead is created on retry.
**Severity:** P2

- **Step 1** — Submit with backend down
  - Action: Submit valid form while backend returns 500 (or simulate offline)
  - Expected: UI shows error, submission not marked successful
  - Result:
  - Note:

- **Step 2** — Retry after recovery
  - Action: Retry submission once backend is back
  - Expected: Exactly 1 lead created, no duplicate from failed attempt
  - Result:
  - Note:

---

### Edge — TC-E

#### TC-E1 — Optional fields empty — still valid

**Scenario:** Given the form has optional fields, when the user submits with optional fields empty, then submission succeeds and payload is stored correctly.
**Severity:** P3

- **Step 1** — Leave optional fields blank
  - Action: Fill required fields only, leave optional fields empty
  - Expected: No validation errors, submit enabled
  - Result:
  - Note:

- **Step 2** — Submit form
  - Action: Click Submit
  - Expected: Success confirmation shown, backend accepts request
  - Result:
  - Note:

- **Step 3** — Verify stored payload
  - Action: Check lead record in CRM or logs
  - Expected: Optional fields absent or null, no malformed values
  - Result:
  - Note:

---

#### TC-E2 — Double-click submit — duplicate prevented

**Scenario:** Given the user can click submit multiple times, when they double-click rapidly, then only one submission is processed.
**Severity:** P2

- **Step 1** — Fill form
  - Action: Enter valid data in all required fields
  - Expected: Submit button enabled
  - Result:
  - Note:

- **Step 2** — Double-click Submit
  - Action: Click Submit twice in rapid succession
  - Expected: UI disables button or shows loading after first click, only 1 request sent
  - Result:
  - Note:

- **Step 3** — Verify backend
  - Action: Check CRM or logs for lead count
  - Expected: Exactly 1 lead created, no duplicates
  - Result:
  - Note:

---

### Regression — TC-R

#### TC-R1 — Re-run core paths after changes

**Scenario:** Given the latest build is deployed after any change to the contact form, when core flows are re-tested, then behavior matches the expected baseline.
**Severity:** P2

- **Step 1** — Re-run TC-H1
  - Action: Run valid submit flow end to end
  - Expected: Happy path passes, 1 lead created
  - Result:
  - Note:

- **Step 2** — Re-run TC-E2
  - Action: Double-click Submit with valid data
  - Expected: Duplicate prevention still works
  - Result:
  - Note:

- **Step 3** — Re-run TC-N1
  - Action: Submit with required field empty
  - Expected: Validation still blocks submit
  - Result:
  - Note:

---

## 4. Report

| ✅ Pass | ❌ Failed | ⚠️ Block |
|---------|----------|----------|
|         |          |          |

### Pass

- *(fill after test run)*

### Failed

- *(fill after test run)*

### Block

- TC-R1 — Not run yet (0 steps executed)

### Final verdict

*(fill after test run)*
