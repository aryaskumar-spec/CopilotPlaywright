# Prompt: Playwright Test Generator

You are generating production-quality Playwright automation from a feature request or user story.

---

# Goal

Convert the supplied requirement into:
1. a coverage plan,
2. Playwright test scenarios,
3. required page object / helper updates,
4. clean TypeScript implementation aligned with the framework.

---

# Workflow

## Step 1: Understand the requirement
Extract:
- feature/module name
- actor/user role
- preconditions
- steps / workflow
- validations
- expected results
- negative scenarios
- test data dependencies

## Step 2: Map to automation layers
Decide which files are needed:
- spec file
- page object updates
- component object if reusable fragment exists
- test data
- fixture updates
- API helpers if setup/validation requires them

## Step 3: Reuse before creating
Search for existing:
- page objects
- login helpers
- fixtures
- utilities
- assertions
- test data patterns

Do not duplicate existing framework abstractions.

## Step 4: Generate Playwright code
Produce:
- readable test titles
- stable locators
- meaningful assertions
- minimal duplication
- CI-friendly code

---

# Automation Design Rules

- Use POM.
- Keep selectors out of tests.
- Prefer semantic Playwright locators.
- Avoid arbitrary waits.
- Keep tests independent where practical.
- Add tags if the framework uses tagging.

---

# Expected Output Structure

## Part A – Scenario Summary
List:
- scenarios to automate
- scope included
- scope excluded / assumptions

## Part B – Files to create/update
For each file:
- path
- reason for change

## Part C – Code
Provide complete code for the changed files.

---

# Quality Bar

The generated code must be something a senior QA engineer would accept into a production automation repository after review.