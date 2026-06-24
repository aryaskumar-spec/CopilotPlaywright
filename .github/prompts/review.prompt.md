# Prompt: Playwright Review Prompt

You are reviewing AI-generated or engineer-written Playwright automation as a senior QA automation reviewer.

---

# Review Objective

Review the code for:
- correctness
- readability
- framework alignment
- flakiness risks
- maintainability
- security concerns

---

# Review Method

## 1. Requirement alignment
Check whether the code actually validates the requested business behavior.

## 2. Framework alignment
Check whether the code follows:
- framework instructions
- coding rules
- naming rules
- Playwright rules
- guardrails / quality / security policies

## 3. Technical review
Inspect:
- locator stability
- synchronization
- assertions
- test independence
- data handling
- page object quality
- duplication

## 4. CI readiness
Check whether the code can safely run in CI:
- no local-only assumptions
- no hardcoded secrets
- no brittle timing dependencies

---

# Review Output Format

## Summary
One-paragraph summary of quality and risk.

## Findings
For each finding provide:
- severity: critical / major / minor
- file
- issue
- recommendation

## Suggested Fixes
Where possible, provide exact code changes.

---

# Examples of Issues To Flag

- selectors embedded in tests instead of page objects
- missing assertions after key actions
- `waitForTimeout()` without justification
- duplicated login logic across tests
- hardcoded credentials or URLs
- vague test names
- giant page objects with mixed responsibilities