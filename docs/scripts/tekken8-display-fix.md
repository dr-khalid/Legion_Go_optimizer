# `tekken8-display-fix.ps1`

## Goal

Fix common Tekken 8 display and orientation problems on the Legion Go, especially issues related to portrait detection and handheld-friendly resolution setup.

## Source inspiration

This spec comes from `tekken8-fix.ps1` and the more general display guidance in the workspace.

## In scope

- inspect current display orientation
- explain and guide correction to landscape mode
- provide recommended resolution and fullscreen guidance
- optionally back up and update known game config values if needed

## Out of scope

- broad gaming optimization unrelated to Tekken 8
- killing unrelated background apps by default
- mixing game config edits with system-wide tuning unless clearly separated

## Planned user flow

1. detect current orientation and display state
2. explain the expected Tekken 8 handheld setup
3. offer guided correction steps
4. if config editing is needed, back up first and then apply targeted edits

## Safety notes

If the script edits a config file, it should create a visible backup and report exactly what changed.

## Success criteria

- resolves the most common Legion Go display issue for Tekken 8
- keeps config edits narrow and reversible
- stays clearly scoped to one game
