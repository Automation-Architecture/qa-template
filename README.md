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
- [requirements/OVERVIEW.md](requirements/OVERVIEW.md)
- [requirements/CHANGELOG.md](requirements/CHANGELOG.md)
- [workflows/example-feature/OVERVIEW.md](workflows/example-feature/OVERVIEW.md)
- [testcases/2026-03-11/OVERVIEW.md](testcases/2026-03-11/OVERVIEW.md)
- [assets/](assets/)

---

## Structure

- **requirements/** — OVERVIEW.md + CHANGELOG.md (log, newest at top).
- **workflows/** — One folder per feature; each has OVERVIEW.md.
- **testcases/** — One OVERVIEW.md per date folder only (at root of that date, e.g. testcases/2026-03-11/OVERVIEW.md); test folders [TC_01]-name with HAPPY.md, NEGATIVE.md, EDGE.md, REGRESSION.md.
- **assets/** — Images, PDFs, and other attachments.

## AI setup

Use **AGENTS.md** to configure the AI (PM/CEO/Sales, Dev, or Tester/QA mode). The AI must always update this Table of Contents when adding or removing files.

```
base on @AGENTS.md setup project now
```
