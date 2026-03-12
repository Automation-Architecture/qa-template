# AGENTS.md — AI setup for this QA template

**Tag or reference only this file.** At the start, ask: **Are you PM/CEO/Sales, Dev, or QA?** Then run that mode only. Do not suggest the next mode; if the user wants another mode, they tag this file again and pick.

For each mode: **check** the right docs, then **create** following the existing template files in this repo.

---

## Rules

- When you add or remove an overview-level file (e.g. new date folder, new workflow), update the **Table of Contents** in [README.md](README.md). One OVERVIEW per date folder only; no root testcases/OVERVIEW.
- Save every PDF, image, or any other asset in the mode's `assets/` folder (`ba/assets/`, `dev/assets/`, `qa/assets/`).
- After finishing work in a mode, ask the user: "Do you want me to update these changes to the repo so every team can use them?" Only if the user says yes, run git pull then git push (and handle conflicts with a new branch + pull request, telling Dev or Javier to fix).

---

## Project structure

Current folder tree of this template:

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
    │   └── <name>.md          # e.g. javier.md — per-BA access, credentials, quick links
    ├── assets/
    │   └── README.md
    └── testcases/
        └── <date>/            # e.g. 2026-03-11
            ├── OVERVIEW.md    # Test run summary + Pass/Failed/Block counts
            └── [TC_01]-<name>/
                ├── HAPPY.md
                ├── NEGATIVE.md
                ├── EDGE.md
                └── REGRESSION.md
```

---

## Mode 1: PM / CEO / Sales

- **Check:** Ask for requirements (or extract from PDF). If not enough, ask again.
- **Create:** Follow `ba/requirements/OVERVIEW.md` and `ba/requirements/CHANGELOG.md` template.
- Save any PDF, diagram, or asset used in `ba/assets/`.

---

## Mode 2: Dev

- **Check:** Ask for workflows, tech stack, ideas (or extract from PDF). If not enough, ask again.
- **Create:** Follow `dev/workflows/<feature>/OVERVIEW.md` template.
- Save any PDF, diagram, or asset used in `dev/assets/`.

---

## Mode 3: Tester / QA

### Mode 3.1 — Design testcase

- **Check:** Ask for the **BA name** (e.g. Javier). Look up `qa/access/<name>.md` to see that BA's access, credentials, and context.
- **Create:** Talk with the user to design test cases. Follow `qa/testcases/<date>/OVERVIEW.md` and `qa/testcases/<date>/[TC_01]-name/` (HAPPY.md, NEGATIVE.md, EDGE.md, REGRESSION.md) template.
- Track per-person access + notes in `qa/access/<name>.md` when relevant.
- Save any PDF, diagram, or asset used in `qa/assets/`.

### Mode 3.2 — Submit test result

Use this when the user has **finished running** a test and wants to submit the result.

- **Check:** Ask the user **which test case** they want to update (e.g. `qa/testcases/2026-03-11/[TC_01]-test-contact-form/HAPPY.md`).
- **Understand context:** Read that file and count **Preconditions**, **Actions**, and **Verification** table rows (each "Check" row). Use this to know how many items to ask about.
- **Gather result:** For each verification check (and any key actions if needed), ask the user: pass / fail / blocked? User can answer and attach screenshots. Save screenshots to `qa/assets/` and link them in the test file.
- **Update files:**
  1. Update the test file (e.g. HAPPY.md): set each Check row's **Result** and **Status** (✅ pass / ❌ fail / ⚠️ blocked), add **Note** with screenshot link when provided. Set `status` in frontmatter (e.g. `pass` / `fail` / `blocked`).
  2. Update the date folder's **OVERVIEW.md**: adjust the **Total score** table (✅ Pass, ❌ Failed, ⚠️ Block counts) and move or add the test link under the right section (Pass / Failed / Block).

---

## Summary

| Mode   | Who              | Output                        |
| ------ | ---------------- | ----------------------------- |
| 1      | PM / CEO / Sales | ba/requirements/             |
| 2      | Dev              | dev/workflows/<feature>/      |
| 3.1    | Tester / QA      | qa/testcases/<date>/ (design) |
| 3.2    | Tester / QA      | Update test file + OVERVIEW.md (submit result) |
