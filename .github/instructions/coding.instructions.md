# Coding Instructions

This file defines the coding rules for all AI-generated Playwright automation.

---

# Language and Style

- Use **TypeScript** only.
- Use `async/await` consistently.
- Prefer small focused methods over long procedural blocks.
- Keep functions single-purpose.
- Avoid deeply nested `if/else`.
- Prefer descriptive names over abbreviations.
- Do not use `any` unless unavoidable; prefer explicit interfaces/types.
- Avoid dead code, commented-out code, and placeholder TODO blocks unless explicitly requested.

---

# File-Level Expectations

## Test files
- Test files must contain business-flow orchestration and assertions.
- Test files must not contain low-level locator logic.
- Test files should be readable by a QA engineer without digging through implementation details.

## Page Object files
- Page Objects should contain:
  - locators
  - page interactions
  - page-specific assertions when appropriate
- Avoid embedding entire business workflows into page objects if they span multiple pages.

## Utility files
- Keep utilities framework-generic.
- Do not place feature-specific business logic into shared utilities.

---

# Imports and Dependencies

- Use existing framework imports and utilities when available.
- Avoid adding new dependencies unless explicitly requested.
- Keep imports clean and deterministic.
- Remove unused imports.

---

# Error Handling

- Fail fast with meaningful assertions.
- Prefer Playwright `expect()` assertions over manual boolean checks.
- If a helper can fail due to missing UI state, throw a descriptive error or assert expected state before interacting.

---

# Data Handling

- Use test data builders / fixtures / external test data where appropriate.
- Do not hardcode usernames, passwords, tokens, OTPs, or account numbers.
- If sample values are needed in code examples, use obvious placeholders such as:
  - `process.env.TEST_USERNAME`
  - `process.env.TEST_PASSWORD`

---

# Reusability Rules

Before creating new code, check whether similar functionality already exists:
- page objects
- components
- API clients
- helpers
- fixtures
- test data generators

If similar code exists:
- extend it safely
- do not create a duplicate abstraction

---

# Assertions

Good assertions:
- validate business outcome
- validate visible state change
- validate success/error message when relevant
- validate navigation or persisted state if part of the requirement

Weak assertions to avoid:
- only checking that a click happened
- only checking that a page did not crash
- asserting on unstable cosmetic text if not required

---

# Forbidden Patterns

- `page.waitForTimeout(...)` as a default synchronization strategy
- giant “do everything” helper methods
- selectors copied into tests instead of page objects
- hardcoded sleeps
- silent try/catch that hides failures
- swallowing Playwright errors
- magic numbers without explanation