---
name: implement-next-future-task
description: Implement exactly one task from the Prioritized Next Changes section of FUTURE.md. Use for "Implement next", "Implement next feature", "Implement next: <task name>", or "Implement next feature: <task name>". Never select from Pending Queue or Backlog, and stop for blocking unresolved questions or when a named prioritized task is absent.
license: MIT
---

# Implement Next FUTURE Task

Use this skill to implement exactly one eligible task from `Prioritized Next Changes`.

Never select from Pending Queue or Backlog. Never use Backlog as hidden implementation context for a missing named task.

## Selection

Without a task name:

1. Open `FUTURE.md`.
2. Select the first task in `Prioritized Next Changes`.
3. Stop if that section is empty.
4. Do not skip a blocked first task automatically.
5. Perform the clarification gate before editing.

With a task name:

1. Search only prioritized headings.
2. Normalize heading comparison by Unicode normalization, trim, whitespace collapse, and case folding.
3. Require one unambiguous match.
4. Stop if absent.
5. Stop if duplicate normalized matches exist.
6. Never fall back to a similarly named pending or backlog item.
7. Perform the clarification gate before editing.

Use the local selector when helpful:

```bash
python3 scripts/select_prioritized_task.py /path/to/Documents/FUTURE.md
python3 scripts/select_prioritized_task.py /path/to/Documents/FUTURE.md --name "Task Name" --format json
```

## Clarification Gate

Before editing:

1. Read the complete selected task.
2. Read all required repository documentation.
3. Read `Questions and required clarifications`.
4. Identify unresolved blocking questions.
5. Ask the owner those questions.
6. Stop implementation until answers exist.
7. Update the task with answers before implementation.

Do not guess to keep moving.

## Scope

- Honor `Touch`.
- Honor `Discovery allowance`.
- Honor `Out of scope`.
- Update the task before justified scope expansion.
- Avoid opportunistic refactors.
- Add or update tests appropriate to the task.
- Update current-state documentation when behavior ships.
- Remove the completed task from `FUTURE.md` instead of keeping completed entries indefinitely.
- Report checks actually run.

## Completion

Complete only after one selected task is implemented, relevant docs are updated, validations are reported, and the task is removed from `FUTURE.md`.
