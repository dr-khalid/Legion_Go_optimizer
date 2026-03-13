# Repo Blueprint

## Goal

Create a maintainable Legion Go gaming optimization repository that is easier to understand and safer to use than the original script collection.

## Source insights used

The planning for this repo comes from reviewing the earlier script workspace, which showed:

- strong focus on Legion Go gaming optimization
- repeated overlap between multiple scripts
- some useful diagnostics
- a few high-risk scripts with broad registry and service changes
- game-specific helpers that should stay isolated from core system tooling

## Proposed structure

```text
Legion_go_k/
├── README.md
├── docs/
│   ├── repo-blueprint.md
│   ├── script-audit-summary.md
│   ├── safety-guidelines.md
│   ├── script-catalog.md
│   └── scripts/
│       ├── optimize-legion-go.md
│       ├── set-gaming-resolution.md
│       ├── control-performance-mode.md
│       ├── system-diagnostic.md
│       ├── gaming-stability-diagnostic.md
│       ├── fc26-setup.md
│       ├── fc26-monitoring.md
│       └── tekken8-display-fix.md
├── scripts/
│   ├── core/
│   │   ├── optimize-legion-go.ps1
│   │   ├── set-gaming-resolution.ps1
│   │   └── control-performance-mode.ps1
│   ├── diagnostics/
│   │   ├── system-diagnostic.ps1
│   │   └── gaming-stability-diagnostic.ps1
│   └── games/
│       ├── fc26/
│       │   ├── fc26-setup.ps1
│       │   └── fc26-monitoring.md
│       └── tekken8/
│           └── tekken8-display-fix.ps1
└── assets/
```

## Structure rules

### `scripts\core`

Contains handheld-wide utilities that apply to the Legion Go regardless of game. These should be conservative and easy to explain.

### `scripts\diagnostics`

Contains read-first tools that help users understand the system before applying tweaks. These should be the default starting point for troubleshooting.

### `scripts\games`

Contains narrowly scoped game-specific fixes. Each game should live in its own folder so that core system logic does not become mixed with one-off patches.

### `docs`

Contains planning, usage guidance, change-risk documentation, and migration notes from the original script collection.

## Phased build plan

### Phase 1: documentation

Define scope, risks, structure, and naming before moving any code.

### Phase 2: consolidation

Merge duplicate Legion Go optimization ideas into one core script design and identify which game-specific helpers are worth keeping.

### Phase 3: script rebuild

Recreate scripts with tighter scope, clearer prompts, and explicit rollback notes.

### Phase 4: polish

Add examples, usage docs, and a cleaner onboarding flow.

## Naming guidance

- use descriptive verbs
- avoid vague names like `fix-tool`
- prefer one responsibility per script
- reserve `optimize` for broad but still bounded workflows
- reserve `diagnostic` for reporting-only tools

## Immediate recommendation

The first real script worth rebuilding later is a safe `optimize-legion-go.ps1` that focuses on display, power-plan guidance, Game Mode checks, and optional diagnostics instead of making wide registry changes by default.
