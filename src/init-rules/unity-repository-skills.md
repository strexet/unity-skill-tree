These repository skills are installed:

- `unity-repo-documentation` handles Unity repository documentation initialization, audit, and repair.
- `process-future-pending` handles `Process pending` and `Process pending tasks` by researching the Pending Queue and promoting only implementation-ready work.
- `implement-next-future-task` handles `Implement next` and `Implement next: <task name>` by selecting exactly one task from `Prioritized Next Changes`.

`Implement next` never selects from `Pending Queue` or `Backlog`. It never falls back to Backlog when a named prioritized task is absent.

Blocking unresolved questions in a prioritized task stop implementation until the owner answers them.
