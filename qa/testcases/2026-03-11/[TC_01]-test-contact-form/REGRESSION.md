---
title: Regression
updated_at: 2026-03-11T00:00:00Z
status: todo
type: regression
---

<!-- Leave empty if not related to newest feature. -->

## Purpose

Run after any changes to the contact form (UI, validation, API integration) to confirm key paths still work.

## Test cases

### TC-R1. Re-run core paths

**Scenario:** Given the latest build is deployed, when the contact form is submitted in core happy/edge/negative flows, then behavior matches the expected baseline with no new errors or duplicates.

| # | Action | Expected | Result | Note |
|---|--------|----------|--------|------|
| 1 | Execute TC-P1 (valid submit). | Happy path passes. | todo | |
| 2 | Execute TC-E2 (double submit prevention). | Duplicate prevention still works. | todo | |
| 3 | Execute TC-N1 (missing required field). | Validation still blocks submit correctly. | todo | |
