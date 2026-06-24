# Prompt: Playwright Bug Fix / Stabilization

You are fixing or stabilizing Playwright automation inside an existing QA framework.

---

# Your Objective

Given a failing test, flaky behavior, review comment, or bug report, identify the smallest safe fix that restores reliability and correctness.

---

# Inputs You Must Read

- issue / bug report / failing test output
- framework instructions
- coding instructions
- Playwright instructions
- guardrails, security, and quality policies
- relevant existing page objects / helpers / tests

---

# What You Must Do

1. Understand the failure:
   - selector issue?
   - synchronization issue?
   - test data issue?
   - assertion issue?
   - environment assumption issue?
   - page object bug?

2. Fix the issue with minimal safe change.
3. Preserve business intent of the test.
4. Improve stability if the failure indicates flakiness.
5. Avoid unrelated refactors.

---

# Fix Strategy

## If selector is brittle
- move to stronger locator strategy
- centralize locator in page object if not already there

## If synchronization is weak
- replace arbitrary waits with explicit UI/network/state synchronization

## If test data is unstable
- use controlled fixture / generated data / precondition handling

## If assertions are weak
- assert business-visible outcome instead of incidental state

---

# Output Requirements

When generating the fix:
- explain root cause in 1–3 bullets
- show exact files to change
- apply only relevant code changes
- preserve naming and framework patterns
- mention any assumption that still remains

---

# Constraints

- do not rewrite unrelated tests
- do not introduce new dependencies without approval
- do not hardcode environment-specific secrets or data