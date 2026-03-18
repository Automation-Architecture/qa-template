# Test case template (copy one block per scenario)

**Inspired by:** Gherkin (Given/When/Then) + step/expected/result table (TestRail, Zephyr style).

---

## How to use

1. **Precondition** — bullets: env, credentials, data needed.
2. **Per scenario** — one **Scenario** line + one table. Fill **Result** and **Note** when you run.

---

### TC-XX. [Scenario name]

**Scenario:** Given [context], when [user action], then [expected outcome].

| # | Action | Expected | Result | Note |
|---|--------|----------|--------|------|
| 1 | [What you do] | [What should happen] | ✅ / ❌ / ⚠️ | Screenshot, ticket, etc. |
| 2 | ... | ... | | |

---

**Result:** ✅ pass / ❌ fail / ⚠️ block  
**Note:** *(optional sample response or evidence)*

