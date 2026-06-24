# Security Policy

This file defines security requirements for AI-generated test automation.

---

# Secret Management

- Credentials must come from environment variables, secret stores, or approved fixtures.
- Never hardcode:
  - usernames
  - passwords
  - bearer tokens
  - API keys
  - client secrets
  - OTP values
- Never print secrets to console, logs, reports, or screenshots when avoidable.

---

# Environment Safety

- Do not assume production access.
- Do not point tests to production unless explicitly approved.
- Do not modify environment configuration outside the intended scope.

---

# Test Data Safety

- Use synthetic / non-sensitive test data where possible.
- Do not commit real customer data, PHI, PII, or financial data.
- If example values are required in documentation, clearly mark them as placeholders.

---

# Authentication / Authorization

- Do not bypass authentication or authorization unless the test explicitly requires controlled mocking/stubbing and the framework supports it.
- Respect role-based access assumptions provided by the issue or environment setup.

---

# Reporting and Evidence

- Ensure screenshots, traces, logs, and reports do not intentionally expose secrets.
- If a failure page can reveal sensitive values, avoid logging raw page content blindly.

---

# Dependency and Code Safety

- Avoid introducing third-party packages without explicit approval.
- Do not add code that weakens environment security or disables platform protections.