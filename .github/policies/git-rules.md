# Git Rules

These rules govern how AI interacts with git-managed source code.

---

# Branching

- Use a feature-specific branch for generated work.
- Branch names should follow naming instructions.
- Do not push directly to main/master.
- Do not merge PRs automatically unless explicitly configured and approved.

---

# Change Scope

- Only change files relevant to the current issue / story / bug fix.
- Do not refactor unrelated files.
- Do not rename framework-wide files unless explicitly requested.
- Do not delete tests, helpers, or docs unless the task explicitly requires it.

---

# Commit Discipline

If commit messages are generated, they should be clear and scoped.

Examples:
- `test(login): add valid and invalid login Playwright coverage`
- `fix(appointment): stabilize booking flow assertions`
- `refactor(page-object): extract reusable search helper`

---

# Pull Request Expectations

A generated PR should include:
- feature / issue summary
- what was automated
- any assumptions made
- known gaps / risks if applicable

---

# Forbidden Git Actions

- force push to protected branches
- rewriting shared history
- deleting remote branches unrelated to the current task
- bundling unrelated changes into the same PR