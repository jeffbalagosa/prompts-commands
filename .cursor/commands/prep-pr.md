---

name: /prep-pr-lite
id: prep-pr-lite
category: RepoHygiene
description: Ask key MCQs, clean logs/comments, and draft a minimal PR (What/Why) with safety guardrails.

---

<!-- PREP-PR-LITE:START -->

**Guardrails**
* Do not modify commits on shared branches.
* Keep scope to the current branch unless explicitly expanded.
* Never delete logs or comments tied to error handling, metrics, or security.
* Keep all functional logic intact; only remove noise or clutter.
* If unsure, ask before applying destructive actions.

**Steps**
Track these steps as TODOs and complete them one by one.
* Study the diff between this branch and the master/main branch.
* Ask up to seven clarifying questions in multiple-choice format.
* Remove console logs used for debugging.
* Remove: commented-out code, trivial narrations, orphan TODOs.
* Fix: update misleading or outdated ones.
* Keep: concise doc comments.

**Clarifying and aligning with the user**
- Consider, "Do I have enough context to answer why these changes were made?"
- Consider if these changes have a related story or epic.
- Ask up to seven multiple-choice clarifying questions to the user to get more context about the changes.

**PR Draft (`PR_DRAFT.md`)**
* **Title:** `<type>(<scope>): <concise summary>`

* **What?**
  * Summarize core code changes (1–3 bullets).

* **Why?**
  * Briefly explain the problem or motivation.

<!-- PREP-PR-LITE:END -->
