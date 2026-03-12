---
title: QA documentation template
updated_at: 2026-03-12T00:00:00Z
---

# QA documentation template

> Reusable structure for requirements, workflows, and test cases. Replace examples with your project content.

---

## Table of Contents

- [README.md](README.md)
- [AGENTS.md](AGENTS.md)
- [ba/requirements/OVERVIEW.md](ba/requirements/OVERVIEW.md)
- [ba/requirements/CHANGELOG.md](ba/requirements/CHANGELOG.md)
- [ba/assets/README.md](ba/assets/README.md)
- [dev/workflows/example-feature/OVERVIEW.md](dev/workflows/example-feature/OVERVIEW.md)
- [dev/assets/README.md](dev/assets/README.md)
- [qa/testcases/2026-03-11/OVERVIEW.md](qa/testcases/2026-03-11/OVERVIEW.md)
- [qa/access/javier.md](qa/access/javier.md)
- [qa/assets/README.md](qa/assets/README.md)

---

## Structure

- **ba/** — Business/requirements docs
  - **ba/requirements/** — OVERVIEW.md + CHANGELOG.md (log, newest at top)
  - **ba/assets/** — attachments for BA docs (index in `ba/assets/README.md`)
- **dev/** — Workflow/engineering docs
  - **dev/workflows/** — one folder per feature; each has OVERVIEW.md
  - **dev/assets/** — attachments for Dev docs (index in `dev/assets/README.md`)
- **qa/** — QA/testing docs
  - **qa/testcases/** — one OVERVIEW.md per date folder only (at root of that date, e.g. `qa/testcases/2026-03-11/OVERVIEW.md`); test folders `[TC_01]-name` with HAPPY.md, NEGATIVE.md, EDGE.md, REGRESSION.md
  - **qa/access/** — per-person QA notes (access, quick links, current testing)
  - **qa/assets/** — attachments for QA docs (index in `qa/assets/README.md`)

## AI setup

Use **AGENTS.md** to configure the AI (PM/CEO/Sales, Dev, or Tester/QA mode). The AI must always update this Table of Contents when adding or removing files.

```
base on @AGENTS.md setup project now
```
