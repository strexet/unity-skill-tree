# Security and Privacy

Last verified: 2026-06-10.

## Telemetry

This repository and installer implement no first-party telemetry.

The upstream open `skills` CLI may have its own telemetry behavior. Use `DISABLE_TELEMETRY=1` or `DO_NOT_TRACK=1` when invoking upstream tooling if required by policy.

## Network Access

No network is needed for:

- validation scripts;
- skill-local deterministic tools;
- `node bin/install.js --list`;
- `node bin/install.js --dry-run ...`;
- local copy or symlink installation.

Network may be used by:

- `npx -y skills ...`;
- Git source resolution;
- future native installers, if explicitly added later.

## Path Safety

Tools validate paths before writing, refuse filesystem-root destinations, and print every planned destination. Symlink mode displays the resolved target.

## Overwrite Policy

Existing skill folders are skipped unless `--force` is used. Unrelated skills are never deleted. Copy mode stages replacements before swapping.

## Bridge Safety

Optional bridges are marker-fenced, idempotent, and backed up before modifying existing files. Uninstall removes only the marker block.

## Secrets

Scripts do not collect secrets. Inventory tools report paths and metadata instead of dumping file contents. Documentation examples must use secret names or placeholders, not values.

## Installed Scripts

Installation does not execute scripts bundled inside skills. Agents may run skill-local scripts later as part of an explicit workflow.
