---
name: process-future-pending
description: Process the Pending Queue in a repository FUTURE.md. Use when asked to "Process pending" or "Process pending tasks": research each pending request, validate it against the repository, add implementation questions, and promote only implementation-ready work into Prioritized Next Changes. Do not implement the tasks and do not promote Backlog work unless explicitly requested.
license: MIT
---

# Process FUTURE Pending Tasks

Use this skill only for `Process pending` and `Process pending tasks`.

Processing pending work is research and documentation work. Do not implement features unless the user explicitly combines the commands.

## Required Workflow

1. Locate the applicable `FUTURE.md`.
2. Read repository `AGENTS.md`, `Documents/RULES.md`, and relevant source-of-truth docs.
3. Read `references/FUTURE_TASK_STANDARD.md` and `references/PENDING_PROCESSING_CHECKLIST.md`.
4. Read the complete Pending Queue.
5. Inspect affected implementation, serialized assets, settings, tests, and docs.
6. Check whether each item is implemented, stale, duplicate, contradictory, blocked, or valid.
7. Merge overlapping requests only when they describe the same coherent change.
8. Expand valid items to the full prioritized-task standard.
9. Add `Questions and required clarifications:` to every promoted task.
10. Resolve questions from evidence where possible and mark the answer state.
11. Mark blocking unresolved questions explicitly.
12. Move only sufficiently researched, implementation-ready tasks.
13. Preserve priority placement.
14. Leave insufficiently understood items in Pending Queue with missing information.
15. Run `scripts/validate_future_document.py` when validation is allowed.
16. Report promoted, retained, merged, removed, and blocked items.

## Boundaries

- Do not process Backlog unless explicitly requested.
- Do not write product code.
- Do not promote lightly expanded bullets.
- Do not omit task-specific implementation questions.

## Local Validator

```bash
python3 scripts/validate_future_document.py /path/to/Documents/FUTURE.md
python3 scripts/validate_future_document.py /path/to/Documents/FUTURE.md --strict --format json
```

## Completion

Complete when every Pending Queue item has been researched and either promoted with a full task contract or retained with a clear blocker.
