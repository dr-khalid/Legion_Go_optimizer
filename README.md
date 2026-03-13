# Legion Go K

Documentation-first repository for building a cleaner, safer Legion Go gaming optimization toolkit.

## Purpose

This repo is intended to turn a loose set of gaming and system-tuning scripts into a more organized project focused on:

- Legion Go performance optimization
- gaming stability diagnostics
- resolution and display setup
- game-specific fixes where they are truly useful
- safer documentation around high-impact Windows changes

## Why this repo exists

The source workspace already contains useful ideas, but it also has overlap, duplicated scripts, and a mix of safe and invasive system changes. This repo is the cleanup path: document first, then rebuild intentionally.

## Current status

This repository is currently in the planning and documentation stage.

For now, it contains markdown only:

- project overview
- repo blueprint
- script audit summary
- safety guidelines
- script catalog
- per-script design specs

## Planned repo shape

```text
Legion_go_k/
├── README.md
├── docs/
│   ├── repo-blueprint.md
│   ├── script-audit-summary.md
│   └── safety-guidelines.md
├── scripts/
│   ├── core/
│   ├── diagnostics/
│   └── games/
└── assets/
```

## Planned focus areas

### Core Legion Go optimization

Safe baseline tuning for power profile guidance, display setup, gaming mode checks, and handheld-specific recommendations.

### Diagnostics

Read-first tools that help identify memory pressure, thermal issues, background app interference, startup load, and storage pressure before making changes.

### Game-specific helpers

Small, targeted tools for games that actually need device-specific fixes, such as FC 26 resolution setup or Tekken 8 orientation handling.

## Design principles

- prefer diagnostics before modification
- document every risky system change
- avoid duplicate scripts
- separate generic tuning from game-specific fixes
- keep rollback instructions close to every optimization

## What comes next

Next steps for this repo will likely be:

1. finalize categories and naming
2. define a safe baseline optimization profile
3. merge overlapping concepts from existing Legion Go scripts
4. rebuild scripts with clearer scope and rollback guidance

See `docs\repo-blueprint.md` for the target structure.

See `docs\script-catalog.md` for the planned script set.
