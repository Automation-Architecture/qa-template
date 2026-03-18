---

## title: Happy path

updated_at: 2026-03-11T00:00:00Z
status: todo
type: happy

## Precondition

- *(e.g. Contact in system with valid phone, sms_opt_out = false)*
- *(e.g. Trigger/webhook configured and reachable)*
- *(e.g. No duplicate or cooldown blocking this run)*
- *(add more as needed for this scenario)*

## Test cases

### TC-P1. Submit valid contact form → success shown → lead created (or sent)

**Scenario:** Given the user is on the contact page, when they submit a valid form payload, then the UI confirms success and the backend receives/creates the lead without errors.


| #   | Action                                                        | Expected                                                                     | Result | Note                            |
| --- | ------------------------------------------------------------- | ---------------------------------------------------------------------------- | ------ | ------------------------------- |
| 1   | Open the contact form page.                                   | Form loads with all required fields visible.                                 | todo   |                                 |
| 2   | Fill fields with valid data (name, email, message, etc.).     | Client-side validation allows submit.                                        | todo   |                                 |
| 3   | Click **Submit**.                                             | Success state is shown (toast/message) and no error banner appears.          | todo   |                                 |
| 4   | Verify backend/CRM/email side-effect (whichever is the spec). | Exactly 1 lead/contact is created/sent; payload values match; no duplicates. | todo   | Link logs / screenshot / ticket |


