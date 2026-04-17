# AGENTS.md — AI setup for this QA template

**On open:** Ask: *PM/CEO/Sales, Dev, or QA?* Run **only** that mode. Do not suggest switching modes; user tags this file again to pick another.

**Each mode:** Read the paths below, then **create or update** files so they match existing templates in this repo.

**Interactive asks:** When you need the user to **choose** (PM / Dev / QA, or QA **3.1 / 3.2**, or similar multiple-choice), **prefer** a host-provided **question / picker tool** if this session has one (e.g. `AskUserQuestion`, multi-select modal, or whatever the IDE exposes)—so the user gets a popup or structured choices instead of only free-form chat. **If no such tool is available**, fall back to a short numbered list and wait for the reply.

---

## Global rules


| Rule            | Detail                                                                                                                                                                                             |
| --------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| README TOC      | Add/remove entries in [README.md](README.md) when you add or remove overview-level items (e.g. new `qa/testcases/<date>/`, new workflow).                                                          |
| QA date folders | One `.md` file per feature under `qa/testcases/<date>/`. No `OVERVIEW.md`, no subfolders.                                                                                                          |
| Assets          | PDFs/images → `ba/assets/`, `dev/assets/`, or `qa/assets/` by mode.                                                                                                                                |
| Git push        | After work, ask: *"Do you want me to update these changes to the repo so every team can use them?"* Only if **yes**: `git pull` then `git push`. On conflict: new branch + PR; tell Dev or Javier. |


---

## Repo layout (where files live)

```
.
├── AGENTS.md
├── README.md
├── ba/
│   ├── assets/
│   │   └── README.md
│   └── requirements/
│       ├── CHANGELOG.md
│       └── OVERVIEW.md
├── dev/
│   ├── assets/
│   │   └── README.md
│   └── workflows/
│       └── <feature>/
│           └── OVERVIEW.md
└── qa/
    ├── access/
    │   └── <name>.md          # per-person access/notes/quick links
    ├── assets/
    │   └── README.md
    └── testcases/
        └── <date>/            # e.g. 2026-04-10
            └── <feature-name>.md   # single file per feature — all sections inside
```

---

## QA conventions (Modes 3.1–3.2)


| Topic         | Convention                                                                                                                                                            |
| ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Severity      | `P1` Blocker · `P2` Critical · `P3` Minor                                                                                                                             |
| Scenario IDs  | Happy `TC-H`, Negative `TC-N`, Edge `TC-E`, Regression `TC-R` — numbered within each section (TC-H1, TC-H2, etc.)                                                     |
| Per scenario  | `**Severity:**` + `**Scenario:**` (Given/When/Then) + list of steps                                                                                                   |
| Step format   | One step = `- **Step N** — <title>` with four sub-lines: `Action`, `Expected`, `Result` (PASS / FAIL / BLOCK), `Note` (always present, leave blank if nothing to add) |
| Atomic steps  | One action per step. Short and direct — no combining two actions in one step.                                                                                         |
| Result values | `PASS` · `FAIL` · `BLOCK` (blocked by a previous failure or missing dependency)                                                                                       |
| File language | English throughout                                                                                                                                                    |
| Evidence      | Store screenshots/files under `qa/assets/`; link from the Note line of the relevant step                                                                              |


---

## Mode 1: PM / CEO / Sales

### 1.1 — Create requirements (existing mode)

- **Check:** Requirements (or PDF). Re-ask if unclear.
- **Create:** `ba/requirements/OVERVIEW.md` + `CHANGELOG.md`; extras in `ba/assets/`.

### 1.2 — Generate UAT Notice

**Goal:** Create a client-facing UAT note that summarizes the feature, shares test access, and guides what to verify.

**Inputs (user will tag or provide):**

- BA context: `ba/requirements/OVERVIEW.md` (and `CHANGELOG.md` if available)
- Dev context: `dev/workflows/<feature>/OVERVIEW.md` (if available)
- UAT template: `ba/_uat-notice-template.md`
- Optional: Loom link, staging URL, login, password, client name

**Steps:**

1. Read `ba/_uat-notice-template.md` first and keep its section order and tone.
2. Extract the feature summary and key acceptance points from BA/Dev files.
3. Create one UAT file under `ba/` named `uat-notice-<feature-name>.md`.
4. Fill the "Please test" section with clear customer checks (short bullets, action-oriented).
5. If any input is missing (demo link, access credentials, client name), keep placeholders and ask the user to fill them.

**Output format (same structure as template):**

- `To` + `Date`
- `Demo`
- `Access` (URL/Login/Password)
- `Please test` (customer checklist)
- `Feedback` (bug vs new request note)

## Mode 2: Dev

- **Check:** Workflows, stack, ideas (or PDF). Re-ask if unclear.
- **Create:** `dev/workflows/<feature>/OVERVIEW.md`; extras in `dev/assets/`.

## Mode 3: Tester / QA

### 3.1 — Create test file

**Inputs (user will tag or provide):**

- BA requirements: `ba/requirements/OVERVIEW.md` (+ `CHANGELOG.md` if available)
- Dev feature: `dev/workflows/<feature>/OVERVIEW.md`

**Steps:**

1. Confirm the date folder to use: `qa/testcases/<date>/`. Create if it does not exist.
2. Read the tagged BA and dev files.
3. Create `qa/testcases/<date>/<feature-name>.md` using the structure below.

**File structure (4 sections, in order):**

```
# <Feature Name>

## 1. Overview
<endpoint or trigger> + one sentence describing what the feature does.

## 2. Loom
Default recording message + blank link placeholder.

## 3. Test Cases

### Happy — TC-H
### Negative — TC-N
### Edge — TC-E
### Regression — TC-R

## 4. Report
Pass/Failed/Block score table + Pass / Failed / Block / Final verdict lists.
Required fixes numbered list when verdict is Not ready.

```

**Loom section (Section 2, always present, link filled after recording):**

```markdown
## 2. Loom

**Recording:** This video was recorded live while filling in this test case and running each step. Watch it for a full walkthrough of what happened during the session.

<!-- Paste Loom link here -->
```

**Step format (use for every step, no exceptions):**

```markdown
- **Step N** — <short title>
  - Action: <what to do>
  - Expected: <what should happen>
  - Result: PASS / FAIL / BLOCK
  - Note:
```

**Writing style for steps — keep everything short and direct:**

| Field | Rule | Good | Avoid |
|-------|------|------|-------|
| Step title | Verb + object, ≤ 4 words | `Complete payment` | `Complete the payment flow successfully` |
| Action | Start with a verb, one action only | `Click Submit` | `Click the Submit button to confirm and send the form` |
| Expected | State the outcome, not the process | `Redirected to will form` | `User should be redirected back to the Generate Will form page` |
| Note | Only bug detail or warning — blank if nothing | `Missing doc link for plan 499` | `I noticed that the document link is missing` |

**Report section format:**

```markdown
| ✅ Pass | ❌ Failed | ⚠️ Block |
|---------|----------|----------|
| X       | X        | X        |

### Pass
- <scenario ID> — PASS steps: X of Y

### Failed
- <scenario ID> step N — <short bug statement>

### Block
- <scenario ID> — <reason>

### Final verdict
<one sentence: Ready / Not ready and why>

**Required fixes before release:**
1. <scenario step> — <what to fix>
```

**Severity in Final verdict:** Any P1 FAIL or BLOCK → Not ready. Only P2/P3 → Ready with follow-ups listed.

---

### 3.2 — Sync JIRA

**GitHub blob URL (always compute, never guess):**

1. `git remote get-url origin` → normalize to `https://github.com/<owner>/<repo>`
2. `git branch --show-current` → branch name
3. File URL: `https://github.com/<owner>/<repo>/blob/<branch>/<repo-relative-path>`

**Jira note:** Never use bare `Source link: <url>` on its own line — Jira renders it as a giant heading. Always wrap URLs inside a markdown list item with a label.

---

**Parent ticket**

- **Title:** `QA — <Feature Name>`
- **Description:** Short bullet list — what the feature does and what passing QA means. 3–5 bullets max. No verbatim file content here.

Example:

```markdown
- Generates an Islamic will document via POST /amra/generate-full-will
- Orchestrates two parallel subworkflows, produces a Google Doc, and saves to Supabase
- QA covers: full API flow, UI end-to-end, form validation, plan 499 doc link, boundary values
- Passing QA means: all P1 scenarios pass and no BLOCK items remain
```

---

**Subtask**

- **Title:** `QA Session — <Feature Name> — <YYYY-MM-DD>`
- **Body:**

```markdown
- [QA file — <feature-name>.md](<GitHub blob URL of the QA file>)

---

**Recording**

This video was recorded live while filling in this test case and running each step. Watch it for a full walkthrough of what happened during the session.
<paste Loom link from Section 2 of the QA file>

---

**Report**

<paste Section 4 Report of the QA file verbatim>
```

**Sync rule:** If the parent or subtask already exists, update it. If missing, create it.

---

## Summary


| Mode | Who              | Output                                                                   |
| ---- | ---------------- | ------------------------------------------------------------------------ |
| 1.1  | PM / CEO / Sales | `ba/requirements/`                                                       |
| 1.2  | PM               | `ba/uat-notice-<feature-name>.md` (client UAT summary + test guidance)  |
| 2    | Dev              | `dev/workflows/<feature>/`                                               |
| 3.1  | QA               | `qa/testcases/<date>/<feature-name>.md` (single file, all sections)      |
| 3.2  | QA               | Jira parent `QA — <feature>` + subtask `QA Session — <feature> — <date>` |


