---
title: <Feature Name>
date: YYYY-MM-DD
tester: <Name>
status: in-progress
---

# <Feature Name>

---

## 1. Overview

**Endpoint / Trigger:** `POST /api/example` or `UI — <Entry point>`

<One sentence: what the feature does and what a passing run produces.>

---

## 2. Loom

**Recording:** This video was recorded live while filling in this test case and running each step. Watch it for a full walkthrough of what happened during the session.

<!-- Paste Loom link here -->

---

## 3. Test Cases

---

### Happy — TC-H

#### TC-H1 — <Happy scenario title>

**Scenario:** Given <starting state>, when <user action>, then <expected outcome>.
**Severity:** P1

- **Step 1** — <Verb + object>
  - Action: <Verb + what, e.g. "Submit form with valid payload">
  - Expected: <Outcome, e.g. "Request accepted (2xx)">
  - Result:
  - Note:

- **Step 2** — <Verb + object>
  - Action: <e.g. "Check Parse Input node output">
  - Expected: <e.g. "Normalized fields produced">
  - Result:
  - Note:

- **Step 3** — <Verb + object>
  - Action:
  - Expected:
  - Result:
  - Note:

---

### Negative — TC-N

#### TC-N1 — <Negative scenario title>

**Scenario:** Given <starting state>, when <invalid action>, then <system blocks or shows error>.
**Severity:** P2

- **Step 1** — <Verb + object>
  - Action: <e.g. "Submit form with empty required fields">
  - Expected: <e.g. "Validation errors shown">
  - Result:
  - Note:

- **Step 2** — <Verb + object>
  - Action:
  - Expected:
  - Result:
  - Note:

---

### Edge — TC-E

#### TC-E1 — <Edge scenario title>

**Scenario:** Given <boundary or unusual condition>, when <user action>, then <expected outcome>.
**Severity:** P2

- **Step 1** — <Verb + object>
  - Action: <e.g. "Enter minimum valid string in text field">
  - Expected: <e.g. "No validation error">
  - Result:
  - Note:

- **Step 2** — <Verb + object>
  - Action:
  - Expected:
  - Result:
  - Note:

---

### Regression — TC-R

#### TC-R1 — <Previously fixed bug being re-checked>

**Scenario:** Given <condition from old bug>, when <same action>, then <bug must not recur>.
**Severity:** P2

- **Step 1** — <Verb + object>
  - Action:
  - Expected:
  - Result:
  - Note:

---

## 4. Report

| ✅ Pass | ❌ Failed | ⚠️ Block |
|---------|----------|----------|
|         |          |          |

### Pass

- TC-H1 — PASS steps: X of Y
- TC-N1 — PASS steps: X of Y

### Failed

- TC-H1 step N — <Short bug statement>

### Block

- TC-R1 — Not run yet (0 steps executed)

### Final verdict

<One sentence: Ready for UAT / Not ready — and the key reason.>

**Required fixes before release:**

1. TC-XX step N — <What to fix>
