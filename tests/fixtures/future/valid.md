# Future Work

Last validated: 2026-06-10.

## Pending Queue

- None.

## Prioritized Next Changes

### Add Save Migration Validation

Priority: High
Status: Ready
Origin: Test fixture
Evidence:
- `Assets/Game/Save`
Goal:

Current behavior:
- Save migrations are not validated by a dedicated test.

Desired behavior:
- Add validation for save migration compatibility.

Touch:
- `Assets/Game/Save`

Discovery allowance:
- Follow save migration references only.

Dependencies:
- None identified.

Out of scope:
- Save format redesign.

Implementation constraints:
- Preserve existing save data.

Possible implementation approaches:
1. Add deterministic unit coverage.

Recommended approach:
- Add unit coverage around current migration path.

Implementation notes:
- Keep behavior narrow.

Data, persistence, and migration:
- No schema change.

Unity/serialization considerations:
- No asset edits expected.

Platform considerations:
- Applies to all platforms.

Failure handling and recovery:
- Existing save loading errors remain unchanged.

Diagnostics and observability:
- Test failure identifies migration incompatibility.

Questions and required clarifications:
- No unresolved questions. Repository evidence and existing project rules establish the implementation decisions listed above.

Validation:
- Run save migration unit tests.

Acceptance:
- Save migration validation exists and passes.

Documentation updates:
- Update `Documents/TESTING.md`.

Risks:
- Test fixture could miss platform-specific persistence.

## Backlog

- Future save UX improvements.
