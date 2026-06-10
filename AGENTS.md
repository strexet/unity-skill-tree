# Repository Agent Instructions

## Required Reading

- Read `SKILL_REPOSITORY_CREATION_INSTRUCTIONS.md` before changing repository structure, installer behavior, provider metadata, tests, or skill contracts.
- Read `REPO_INIT_INSTRUCTIONS.md` before changing Unity documentation workflow behavior.
- Read `docs/INSTALLATION_ARCHITECTURE.md` before changing the installer or provider matrix.
- Read `docs/AGENT_COMPATIBILITY.md` before changing agent support claims.

## Source-of-Truth Rules

- `REPO_INIT_INSTRUCTIONS.md` is canonical for Unity repository analysis, documentation initialization, `FUTURE.md` queue semantics, `Process pending`, and `Implement next`.
- `scripts/sync_skill_references.py` owns generated references. Do not edit generated references manually.
- `config/providers.json` is canonical for provider ids, paths, detection metadata, upstream profiles, and adapter bridges.
- `LICENSE` is the existing repository license. The SPDX identifier is `MIT`.

## Portable Skill Rules

- Canonical skills live only in `skills/<skill-name>/`.
- Installed skills must remain self-contained after copying.
- `SKILL.md` files must follow the open Agent Skills format: YAML frontmatter with `name` and `description`, then focused Markdown instructions.
- Keep detailed behavior in `references/` and deterministic helpers in `scripts/`.
- Do not create divergent skill implementations for specific agents.

## Provider and Adapter Rules

- Vendor behavior belongs in `adapters/`, optional `agents/openai.yaml`, or `config/providers.json`.
- Verify version-sensitive agent claims against official docs or the current open `skills` CLI.
- Directory-only probes are soft and must not trigger automatic installation.
- Soft providers install only when explicitly selected.

## Validation Commands

Run these before staging, when owner policy permits tests:

```bash
python3 scripts/sync_skill_references.py
python3 scripts/sync_skill_references.py --check
python3 scripts/validate_skill_repository.py --strict
python3 -m unittest discover -s tests -p 'test_*.py'
node --test tests/test_installer.js tests/test_provider_matrix.js
node bin/install.js --list
node bin/install.js --dry-run --all
git diff --check
git status --short
```

## Git and Release Safety

- Do not add a remote, push, publish, tag, or create marketplace packages without owner instruction.
- Do not commit unless explicitly asked.
- Do not select or change the repository license without owner input.
- Do not overwrite unrelated user files or complete instruction files.
