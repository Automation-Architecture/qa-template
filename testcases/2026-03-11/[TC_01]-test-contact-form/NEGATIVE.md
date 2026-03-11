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

## Action

1. *(e.g. Send webhook with duplicate event ID)*
2. *(e.g. Verify workflow skips and does not send SMS or call)*
3. *(add more steps as needed)*

## Verification

| Check | Result | Status | Note |
|-------|--------|--------|------|
| *(e.g. Duplicate event → workflow exits early)* | | todo / ✅ pass / ❌ fail / ⚠️ blocked | |
| *(e.g. No duplicate SMS sent)* | | todo / ✅ pass / ❌ fail / ⚠️ blocked | |
