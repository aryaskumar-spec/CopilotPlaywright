# Playwright Instructions

This file contains Playwright-specific implementation rules.

---

# Core Playwright Rules

- Use Playwright Test with TypeScript.
- Use `test.describe()` to group related scenarios where helpful.
- Use `test.step()` for important multi-step business flows if it improves readability.
- Use Playwright `expect()` assertions.
- Use locators over brittle selector strings where possible.
- Prefer `getByRole`, `getByLabel`, `getByPlaceholder`, `getByTestId` where available.
- Fall back to CSS/XPath only when semantic locators are not viable.

---

# Synchronization Strategy

Preferred waiting hierarchy:

1. Built-in auto waiting from Playwright locators/actions
2. `await expect(locator).toBeVisible()` / `toHaveText()` / `toBeEnabled()`
3. `waitForResponse` / `waitForURL` / `waitForLoadState` when truly relevant
4. `page.waitForTimeout()` only as a last resort and must be justified

---

# Locator Strategy

Priority order:
1. Accessible role-based locators
2. Stable test IDs
3. Labels / placeholders / text where stable
4. CSS selectors
5. XPath only if unavoidable

Avoid:
- nth-child selectors
- very long CSS chains
- brittle text fragments that change frequently
- indexes unless there is no stable alternative

---

# Page Object Design

A Page Object should usually expose methods such as:
- `goto()`
- `login(username, password)`
- `fillAppointmentForm(data)`
- `submit()`
- `getErrorMessage()`

Page Objects may also expose assertion helpers if they improve readability:
- `expectSuccessToast(message)`
- `expectValidationError(field, message)`

---

# Test Design

A good Playwright test should:
- prepare minimal setup
- call intent-based page methods
- assert outcomes clearly
- avoid hidden side effects
- cleanly separate setup, action, and verification

---

# Network / API Handling

If UI behavior depends on network responses:
- wait for relevant UI outcome first
- use `waitForResponse()` only when the test genuinely depends on the backend response
- avoid asserting every API call unless the requirement is specifically API validation

---

# Flakiness Prevention

Do:
- assert visibility before interaction when state is dynamic
- wait for post-submit state changes
- use stable data
- isolate tests where practical

Do not:
- chain many actions without intermediate validation in unstable flows
- depend on previous tests
- rely on random timing
- leave browser state assumptions undocumented

---

# Recommended Test Skeleton

```ts
test('should allow user to perform business action', async ({ page }) => {
  const featurePage = new FeaturePage(page);

  await featurePage.goto();
  await featurePage.performAction();
  await expect(featurePage.successMessage).toHaveText('Success');
});