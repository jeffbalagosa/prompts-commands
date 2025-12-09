---
name: /prepare-for-review
id: prepare-for-review
category: RepoHygiene
description: Full PR preparation workflow - commit cleanup, quality checks, self-review, and PR draft creation.
---

**Guardrails**

- Do not modify commits on shared branches (main, develop, etc.).
- Do not force-push without explicit confirmation.
- Keep functional logic intact; only clean noise/clutter.
- If tests or linting fail, report and offer to fix before proceeding.
- If unsure about any destructive action, ask first.

**Steps**
Track these as TODOs and complete sequentially:

1. **Analyze branch state**

   - Run `git log main..HEAD --oneline` to list commits.
   - Run `git diff main...HEAD --stat` to summarize changes.
   - Identify files changed, commits to clean, and scope of review.

2. **Clarify and align with the user**

   - Consider, "Do I have enough context to answer why these changes were made?"
   - Consider if these changes have a related story or epic.
   - Ask up to seven multiple-choice clarifying questions to the user to get more context about the changes.

3. **Commit hygiene**

   - Squash fixup/WIP commits into meaningful units.
   - Rewrite commit messages to follow `<type>(<scope>): <summary>` format.
   - Rebase onto latest `main` if behind (confirm before force-push).

4. **Run quality checks**

   - Execute test suite; all tests must pass.
   - Execute linter; all lint errors must be resolved.
   - Report results before proceeding.

5. **Code cleanup**

   - Remove console logs used for debugging.
   - Remove commented-out code, trivial narrations, orphan TODOs.
   - Fix misleading or outdated comments.
   - Keep concise doc comments and JSDoc/docstrings.

6. **Self-review checklist**
   Before submitting, confirm:

   - [ ] All tests pass locally
   - [ ] No linting errors
   - [ ] No debug logs or commented code left behind
   - [ ] Commit messages are clear and follow conventions
   - [ ] Changes are scoped to the stated objective
   - [ ] No unintended file changes (package-lock, config drift)
   - [ ] Reviewed diff one more time for obvious issues

7. **Draft PR**
   Create `PR_DRAFT.md` using this template:

   **Title:** `<type>(<scope>): <concise summary>`

   **What?**

   - Summarize core code changes (bullets).

   **Why?**

   - Briefly explain the problem or motivation.

**Output**

- Report branch analysis summary.
- Report test/lint results.
- List any cleanup actions taken.
- Present self-review checklist with status.
- Output final `PR_DRAFT.md` content ready to copy.

**Style**

- Output style: structured, actionable, concise.
- Output verbosity: medium (show results, skip noise).
- Thinking effort: high (catch issues before reviewer does).
