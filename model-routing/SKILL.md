---
name: model-routing
description: Use at the start of every new task Alvaro gives, to check whether the current session model fits it and suggest a /model switch when that would save usage, and to decide whether large mechanical parts (sweeping many files, filling translations, bulk renames, running and summarising tests, collecting data) should go to a cheaper haiku or sonnet subagent, with verification so the result stays perfect.
---

## First: review the task and suggest a model (every new task)

Before starting, size up the task and compare it with the model this session runs on (shown in the system prompt).

| Task looks like | Best session model |
|---|---|
| Questions, explanations, small edits, copy/docs changes, config, installing tools, git chores | Sonnet |
| Routine feature work that follows existing patterns, UI tweaks, translations, tests for clear behaviour | Sonnet |
| New features with unclear behaviour, architecture, hard or unclear bugs, security/auth/RLS, money logic, big redesigns, final reviews | Opus |
| Trivial lookups or one-line answers | Haiku |

- If the session model is more expensive than the task needs, say so in **one line before starting**, e.g. "This is routine; you could save usage with `/model sonnet`. Continuing on Opus unless you switch."
- If the session model is too weak for the task, say so before starting and recommend `/model opus`. For risky work (security, money, database permissions), wait for the reply.
- Then do the task anyway. Don't block on the answer unless the model is too weak for risky work.
- Don't repeat the same suggestion for follow-ups in the same stretch of work. Suggest again only when the kind of task changes.
- If the current model already fits, say nothing about models.


# Model routing

Goal: spend the expensive model only where its judgment matters, without lowering the quality of what Alvaro receives.

## What can and cannot switch

- The main session's model cannot be changed from inside a session. Only Alvaro can, with `/model`.
- Parts of a task can go to a subagent on another model: the Agent tool's `model` parameter (`haiku`, `sonnet`, `opus`).
- A subagent starts cold: it re-reads files and rebuilds context. That cost is real, so routing only saves usage when the delegated work is large.

## Decide in one pass (no long deliberation)

Keep it in the main session (no subagent) when any of these holds:
- The task is small: one or two files, or under ~10 tool calls.
- It needs judgment: design, architecture, security, auth/RLS, money calculations, debugging an unclear bug, writing or reviewing a plan.
- It depends on context from this conversation that would be costly to hand over.

Delegate to a cheaper model when the work is large **and** mechanical, with a clear expected output:

| Work | Model |
|---|---|
| Find/locate across many files, list matches, summarise logs or test output | `haiku` |
| Fill or check translation files for the 7 languages from an English source | `sonnet` |
| Apply an already-decided, repetitive edit across many files | `sonnet` |
| Write tests for behaviour that is already specified | `sonnet` |
| New feature, hard bug, design, security review, final review | stay on the main model |

Several independent mechanical chunks can run as parallel subagents in one message.

## Hand-off rules

Every delegated prompt must include:
- the exact files or folders, and what is out of scope,
- the decision already made (the subagent never makes design or product choices),
- the expected output format (a list, a diff summary, pass/fail with errors),
- "do not commit, push, deploy or delete anything".

## Quality gate (never skip)

The main model owns the result. Before telling Alvaro the work is done:
1. Read the subagent's report and spot-check its actual changes (`git diff`), not just its summary.
2. Run the real checks the project has (for emet's dashboard: `npm run lint`, `npm test`, `npm run check:i18n`, `npm run build`; `npm run test:db` for database changes).
3. If anything is wrong, fix it in the main session. Do not send the same task back to the cheap model more than once.
4. If a cheap model failed twice on a kind of task, do that kind of task on the main model from then on.

## Reporting

Mention routing only when it happened, in one line: what was delegated, to which model, and that it was verified.
