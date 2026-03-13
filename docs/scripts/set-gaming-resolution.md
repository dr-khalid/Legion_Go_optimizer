# `set-gaming-resolution.ps1`

## Goal

Help users configure a correct Legion Go gaming resolution path, especially for handheld-friendly targets like `1280x800`.

## Source inspiration

This spec comes mainly from `set-gaming-resolution.ps1` and the display-focused parts of `fc26-resolution-fix.ps1` and `tekken8-fix.ps1`.

## In scope

- detect current resolution and orientation
- explain recommended handheld resolutions
- provide launch option examples
- open display settings when requested
- give lightweight guidance for AMD or in-game scaling choices

## Out of scope

- direct registry edits
- deep driver tuning
- game-specific config rewriting unless a separate game script owns it

## Planned user flow

1. display current resolution and orientation
2. show recommended settings for native handheld play
3. offer quick links or commands for adjustment
4. provide per-store launch option examples

## Outputs

- a current state summary
- recommended resolution targets
- Steam launch option examples
- optional links to Windows display settings

## Safety notes

This script should remain mostly instructional. It should avoid forcing changes unless a future implementation can do so reliably and reversibly.

## Success criteria

- users know the correct target resolution quickly
- the script is easy to use during game setup
- it stays low-risk and understandable
