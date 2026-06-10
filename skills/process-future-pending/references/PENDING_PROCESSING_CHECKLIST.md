# Pending Processing Checklist

## Locate

- Find the applicable `FUTURE.md`.
- Confirm it contains `Pending Queue`, `Prioritized Next Changes`, and `Backlog`.
- Read relevant repository rules before editing.

## Read Pending

- Read the complete Pending Queue.
- Preserve source context, evidence, reproduction, constraints, and requested priority.

## Research

- Search affected code, assets, scenes, prefabs, settings, tests, and docs.
- Check related items in all three queues.
- Determine implementation status: implemented, stale, duplicate, contradictory, blocked, or valid.

## Expand

- Identify ownership and likely paths.
- Add current behavior, desired behavior, touch list, discovery allowance, out of scope, implementation constraints, validation, acceptance, docs updates, and risks.
- Add task-specific questions covering UX, architecture, files, state, persistence, serialization, platform behavior, compatibility, migration, recovery, diagnostics, testing, rollout, and non-goals.

## Resolve Questions

- Use repository evidence where possible.
- Mark answers as resolved by evidence, resolved by owner decision, recommended default, unresolved blocking, or unresolved non-blocking.

## Promote or Retain

- Promote only implementation-ready work.
- Retain blocked or insufficiently understood items in Pending Queue.
- Merge overlapping entries only when no intent is lost.
- Remove original pending entries only after preserving their information.

## Stop Conditions

- Required owner decision blocks implementation.
- A request conflicts with current architecture or platform constraints and no safe resolution exists.
- Evidence is insufficient to identify affected ownership.
- The user asked to implement rather than process; route to `implement-next-future-task` only for prioritized tasks.
