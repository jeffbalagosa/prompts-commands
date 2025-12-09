---
description: Improve or construct prompts with clarifying questions, expert personas, and structured outputs.
argument-hint: draft prompt or objective
---

$ARGUMENTS

**Guardrails**
- Follow the clarify -> plan -> execute -> validate -> iterate loop; keep the human in control.
- Do not assume ambiguous intent; ask only targeted, essential follow-ups.
- Keep improvements substantial, focused, and free of filler or fluff.
- Select an expert persona that best fits the stated objective before writing the final prompt.

**Steps**
1. If invoked with arguments, treat them as the draft prompt: analyze it, call out missing info (domain, output type, constraints, audience, style, tool usage), and ask only essential clarifying questions.
2. If invoked with no arguments, immediately ask: "What is your objective or goal for this prompt?"
3. Once the objective is known, pick the optimal expert role/persona and complete missing context so a colleague could deliver a stellar result.
4. Produce an improved, clearly structured prompt that includes the persona, objective, constraints, formatting, and any supplied examples.
5. Offer 2-3 optional enhancements the user may want to add.
6. End by confirming: "Does this meet your intention, or should I refine it?"

**Output**
- Start with a brief analysis when refining an existing prompt.
- Provide the improved prompt in a clean, copy-ready block with clear sections.
- Write the final prompt to `.codex/prompts/{nnn}-{semantic-name}.md` (zero-padded `nnn` starting at `001` for each semantic name; increment `nnn` only when that semantic name already exists). Examples: `001-add-dark-mode.md`, `001-create-config-file.md`, `002-add-dark-mode.md`.
- List 2-3 optional add-ons.
- Close with a concise confirmation question.

**Context (fill as you gather it)**
- objective:
- constraints:
- domain:
- preferred tone:
- target audience:
- examples provided:

**Style**
- Output style: precise, structured, helpful, zero fluff.
- Output verbosity: medium.
- Thinking effort: high.
