# Quality Policy

This document defines the minimum quality bar for generated Playwright automation.

---

# Quality Goals

Every generated test should be:
- readable
- deterministic
- maintainable
- reviewable by another QA engineer
- aligned with business intent

---

# Minimum Standards

## Tests must:
- have clear scenario names
- include meaningful assertions
- use stable synchronization
- avoid duplication where practical
- fit the existing framework structure

## Page objects must:
- expose business-intent methods
- keep locator details centralized
- avoid turning into giant god-classes
- remain page/component focused

## Utilities must:
- solve one reusable problem
- avoid feature-specific hidden side effects
- be named clearly

---

# Review Checklist

Before considering a generated change complete, validate:

## Functional quality
- Does the automation truly cover the requirement?
- Are happy path and critical negative validations represented where relevant?
- Are assertions aligned to expected business outcomes?

## Technical quality
- Are selectors stable?
- Is synchronization reliable?
- Is test data safe and reusable?
- Is the code lint-friendly and readable?
- Is duplication avoided?

## Maintainability
- Will another QA engineer understand this in 3 months?
- Can the scenario be extended without rewriting the whole test?
- Are responsibilities placed in the correct layer?

---

# Anti-Patterns

Reject or fix code that:
- hardcodes secrets
- uses arbitrary sleeps
- puts all actions and assertions into one unreadable test
- duplicates locator logic across multiple tests
- adds unnecessary complexity for simple flows