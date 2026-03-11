# AGENTS.md — AI setup for this QA template

**Tag or reference only this file.** At the start, ask: **Are you PM/CEO/Sales, Dev, or QA?** Then run that mode only. Do not suggest the next mode; if the user wants another mode, they tag this file again and pick.

For each mode: **check** the right docs, then **create** following the existing template files in this repo.

---

## Rules

- When you add or remove an overview-level file (e.g. new date folder, new workflow), update the **Table of Contents** in [README.md](README.md). One OVERVIEW per date folder only; no root testcases/OVERVIEW.
- Save every PDF, image, or any other asset in [assets/](assets/).

---

## Mode 1: PM / CEO / Sales

- **Check:** Ask for requirements (or extract from PDF). If not enough, ask again.
- **Create:** Follow `requirements/OVERVIEW.md` and `requirements/CHANGELOG.md` template.
- Save any PDF, diagram, or asset used in [assets/](assets/).

---

## Mode 2: Dev

- **Check:** Ask for workflows, tech stack, ideas (or extract from PDF). If not enough, ask again.
- **Create:** Follow `workflows/<feature>/OVERVIEW.md` template.
- Save any PDF, diagram, or asset used in [assets/](assets/).

---

## Mode 3: Tester / QA

- **Check:** Read requirements and workflow docs. Brainstorm with user which test cases are needed.
- **Create:** Follow `testcases/<date>/OVERVIEW.md` and `testcases/<date>/[TC_01]-name/` (HAPPY.md, NEGATIVE.md, EDGE.md, REGRESSION.md) template.
- Save any PDF, diagram, or asset used in [assets/](assets/).

---

## Summary

| Mode | Who              | Output               |
| ---- | ---------------- | -------------------- |
| 1    | PM / CEO / Sales | requirements/        |
| 2    | Dev              | workflows/<feature>/ |
| 3    | Tester / QA      | testcases/<date>/    |
