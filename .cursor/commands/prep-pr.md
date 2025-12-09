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

**Clarifying Questions (Example)**
1) Change type: A) feat B) fix C) chore D) refactor
2) Logging baseline: A) errors+warn only B) +info C) guard behind DEBUG D) remove non-error
3) Remove logs in tests: A) yes B) no
4) Comment policy: A) delete noise B) keep JSDoc/docstrings C) keep TODO/FIXME with issue refs D) convert TODO→issue+link
5) Scope: A) repo-wide B) changed files only C) specified dirs D) affected workspaces
6) PR reviewers: A) top owners B) team default C) none D) provide names
7) Default branch name: A) main B) master C) develop D) other (specify)

**PR Draft (`PR_DRAFT.md`)**
* **Title:** `<type>(<scope>): <concise summary>`

* **What?**
  * Summarize core code changes (1–3 bullets).

* **Why?**
  * Briefly explain the problem or motivation.

<!-- PREP-PR-LITE:END -->
