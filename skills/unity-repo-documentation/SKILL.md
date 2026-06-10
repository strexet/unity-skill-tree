---
name: unity-repo-documentation
description: Deeply analyze an existing Unity repository and create, initialize, audit, or repair its AI-oriented repository documentation. Use for requests to document an unfamiliar Unity project, create PROJECT.md, TECHNICAL.md, FEATURES.md, FUTURE.md, RULES.md, AGENTS.md, or establish repository documentation. Do not use for ordinary feature implementation, isolated copy edits, Unity/package upgrades, Process pending, or Implement next.
license: MIT
---

# Unity Repository Documentation

Use this skill for documentation initialization, audit, or repair in an existing Unity project, Unity package, or Unity monorepo.

Do not use it to implement product features, upgrade Unity, upgrade packages, process pending tasks, or implement `FUTURE.md` work.

## Required Workflow

1. Confirm repository root and worktree state.
2. Find every Unity root by checking for `Assets/`, `Packages/`, and `ProjectSettings/`.
3. Read `references/REPO_INIT_INSTRUCTIONS.md` completely.
4. Read `references/DOCUMENTATION_OUTPUT_CONTRACT.md` and `references/UNITY_DISCOVERY_CHECKLIST.md`.
5. Build an evidence inventory before writing narrative documentation.
6. Inspect code, assemblies, scenes, prefabs, ScriptableObjects, packages, settings, build tooling, platform integrations, tests, and existing docs.
7. Create or repair the required live documents.
8. Keep implemented, configured, partial, disabled, deprecated, planned, assumption, and open-question states distinct.
9. Do not modify Unity behavior, serialized assets, package versions, build settings, generated files, or product code as part of documentation initialization.
10. Run `scripts/validate_unity_documentation.py` against the target repository when validation is allowed.
11. Review the final diff for unsupported claims, secrets, broken links, snapshot-named live files, accidental Unity asset changes, and stale placeholders.
12. Report created/updated docs, evidence gaps, checks run, checks not run, and remaining risks.

Run skill-local helpers by path relative to this skill directory:

```bash
python3 scripts/inspect_unity_repository.py /path/to/unity-repo --format markdown
python3 scripts/validate_unity_documentation.py /path/to/unity-repo
python3 scripts/create_documentation_snapshot.py /path/to/unity-repo --dry-run
```

## Activation Examples

- Initialize repository documentation for this Unity project.
- Document this existing Unity repository.
- Audit and repair the project documentation.
- Create AI-oriented documentation for this Unity package.

## Negative Examples

- Fix this gameplay bug.
- Update one README sentence.
- Upgrade Unity.
- Implement the next `FUTURE.md` task.
- Process pending tasks.

## Completion

The task is complete only when the documentation contract is satisfied or unresolved evidence gaps are explicitly reported. Never claim semantic correctness from structural validation alone.
