# Naming Instructions

Use consistent naming across tests, page objects, fixtures, helpers, and generated branches.

---

# File Naming

## Test files
Format:
- `<feature>.spec.ts`
- `<feature>-<scenario>.spec.ts`

Examples:
- `login.spec.ts`
- `appointment-booking.spec.ts`

## Page objects
Format:
- `<page>.page.ts`
- `<component>.component.ts`

Examples:
- `login.page.ts`
- `appointment.page.ts`
- `header.component.ts`

## Fixtures
Format:
- `<domain>.fixture.ts`
- `test.fixture.ts`

## Test data
Format:
- `<feature>.data.ts`
- `<feature>.json`

---

# Class Naming

## Page objects
Use PascalCase ending with `Page`

Examples:
- `LoginPage`
- `AppointmentPage`

## Components
Use PascalCase ending with `Component`

Examples:
- `HeaderComponent`
- `NavigationMenuComponent`

## Utilities
Use PascalCase only if class-based; otherwise prefer named exported functions.

---

# Test Titles

Test titles should be business-readable.

Preferred:
- `should allow a valid user to log in successfully`
- `should display validation error when mandatory fields are missing`

Avoid:
- `test login`
- `verify page`
- `check appointment`

---

# Variable Naming

- Use descriptive camelCase names.
- Prefer `expectedErrorMessage` over `msg`.
- Prefer `appointmentDate` over `date`.
- Prefer `loginPage` over `lp`.

---

# Branch Naming

AI-created branches should follow:

- `ai/<feature-name>`
- `ai/bugfix/<feature-name>`
- `ai/review/<topic>`

Examples:
- `ai/login-tests`
- `ai/bugfix/appointment-validation`

---

# Tag Naming

Use Playwright tags consistently:
- `@smoke`
- `@regression`
- `@sanity`
- `@ui`
- `@api`
- `@negative`

Do not invent multiple tag variants for the same purpose.