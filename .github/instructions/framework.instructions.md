# Framework Instructions

This document explains how AI must work inside this Playwright automation framework.

---

# Framework Principles

The framework is built on the following principles:

1. **Readability** – test code should be easy for manual and automation QA engineers to understand.
2. **Reusability** – shared flows belong in page objects, components, fixtures, or helpers.
3. **Stability** – selectors and synchronization must minimize flakiness.
4. **Scalability** – the framework should support new modules without duplication.
5. **Security** – secrets and environment details must never be hardcoded or exposed.

---

# Expected Framework Layers

The AI should assume the project may contain or evolve into the following layers under `src/`:

- `src/pages` → page objects
- `src/components` → reusable page fragments/components
- `src/tests` → spec files
- `src/fixtures` → Playwright fixtures / custom test setup
- `src/test-data` → static or generated test data
- `src/utils` → helpers
- `src/api` → API clients/helpers
- `src/assertions` → custom assertion helpers where useful

If a requested feature needs one of these layers, place code in the most appropriate location.

---

# Test Design Philosophy

Each test should clearly answer:
- What business behavior is being validated?
- What data/setup is required?
- What outcome proves the feature works?
- What failure messages would help diagnose a problem?

Tests should not become implementation dumps. Prefer clarity over over-abstraction.

---

# Preferred Automation Flow

1. Read the issue / story.
2. Identify coverage areas.
3. Reuse existing framework objects.
4. Create missing page objects / helpers only if necessary.
5. Write tests with clear titles and tags.
6. Run and review for flakiness patterns.
7. Keep PR scope limited to the feature being automated.

---

# Page Object Model Expectations

Page Objects should:
- encapsulate locators and page-level actions
- expose intent-based methods such as `login()`, `searchAppointment()`, `submitForm()`
- avoid exposing raw locator details to tests unless justified
- remain page-focused rather than turning into entire end-to-end workflow managers

---

# Test Data Strategy

Use the simplest safe test-data strategy that fits the scenario:
- fixture-provided user accounts
- environment-specific test accounts
- generated data for non-sensitive entities
- API setup if it makes tests faster and more reliable

Never embed production-sensitive or personal data.

---

# CI / Automation Expectations

Code must be safe for CI:
- headless-friendly
- deterministic
- environment-aware
- not dependent on local machine state
- not dependent on manual intervention

---

# If Requirement Is Ambiguous

If a requirement is incomplete, infer only what is safe and reasonable from:
- issue title
- acceptance criteria
- existing test patterns
- existing page objects and utilities

Do not invent unsupported business rules when they materially affect expected behavior.