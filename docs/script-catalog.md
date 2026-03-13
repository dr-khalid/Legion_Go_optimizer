# Script Catalog

## Purpose

This document maps the planned future scripts for the repository. It is the bridge between the high-level repo blueprint and the individual script specs.

## Core scripts

| Planned script | Purpose | Risk level | Spec |
| --- | --- | --- | --- |
| `optimize-legion-go.ps1` | Safe baseline Legion Go gaming optimization | Medium | `docs\scripts\optimize-legion-go.md` |
| `set-gaming-resolution.ps1` | Guided resolution and display setup | Low | `docs\scripts\set-gaming-resolution.md` |
| `control-performance-mode.ps1` | TDP and thermal mode selection guidance | Medium | `docs\scripts\control-performance-mode.md` |

## Diagnostic scripts

| Planned script | Purpose | Risk level | Spec |
| --- | --- | --- | --- |
| `system-diagnostic.ps1` | General system health and gaming readiness report | Low | `docs\scripts\system-diagnostic.md` |
| `gaming-stability-diagnostic.ps1` | Focused stability and shutdown analysis | Medium | `docs\scripts\gaming-stability-diagnostic.md` |

## Game-specific scripts

| Planned script | Purpose | Risk level | Spec |
| --- | --- | --- | --- |
| `fc26-setup.ps1` | FC 26 setup and troubleshooting helper | Medium | `docs\scripts\fc26-setup.md` |
| `fc26-monitoring.md` | Documentation-only design for optional FC 26 monitoring | Medium | `docs\scripts\fc26-monitoring.md` |
| `tekken8-display-fix.ps1` | Tekken 8 orientation and display helper | Medium | `docs\scripts\tekken8-display-fix.md` |

## Guiding rules

- core scripts should stay useful across games
- diagnostics should prefer reporting over changing
- game-specific scripts should remain isolated
- high-risk actions should be opt-in and documented
- each script should have one clear responsibility

## Build order recommendation

1. `system-diagnostic.ps1`
2. `set-gaming-resolution.ps1`
3. `optimize-legion-go.ps1`
4. `control-performance-mode.ps1`
5. `gaming-stability-diagnostic.ps1`
6. `tekken8-display-fix.ps1`
7. `fc26-setup.ps1`

`fc26-monitoring.md` should remain documentation-only until there is a strong reason to turn it into code.
