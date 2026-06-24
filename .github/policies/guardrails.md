# Guardrails

These are non-negotiable operational guardrails for AI-generated automation work.

---

# Repository Safety

- Do not delete existing framework files unless explicitly asked.
- Do not remove existing test coverage unless explicitly asked.
- Do not alter unrelated modules.
- Do not change package manager strategy or package versions unless explicitly requested.
- Do not modify CI/CD workflow intent without a clear reason tied to the issue.

---

# Code Generation Safety

- Reuse existing page objects / utilities / fixtures where practical.
- Do not create duplicate abstractions for the same page or component.
- Do not place selectors directly in tests if they belong in a page object.
- Do not generate fake code references to utilities that do not exist.
- Do not invent backend behavior that is not supported by the issue or existing code patterns.

---

# Test Reliability Guardrails

- Avoid fixed waits.
- Avoid brittle selectors.
- Avoid tests that depend on execution order.
- Avoid coupling multiple business validations into one massive scenario unless required.
- Prefer deterministic setup and assertions.

---

# Security Guardrails

- Never hardcode credentials, tokens, or secrets.
- Never log secrets in console output, reports, or screenshots.
- Never commit `.env` values or private environment details.
- Never expose production-sensitive data in test data files.

---

# Scope Guardrails

For every issue, keep changes limited to:
- relevant tests
- required page objects / components
- supporting test data / helpers
- documentation only if directly relevant

Do not perform framework-wide cleanup as part of a feature request unless explicitly asked.