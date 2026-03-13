# `optimize-legion-go.ps1`

## Goal

Provide a safe baseline optimization path for Legion Go gaming without defaulting to aggressive registry and service changes.

## Source inspiration

This script is meant to consolidate the useful parts of `legion-go-optimize.ps1`, `legion-go-optimize-fixed.ps1`, and the lower-risk guidance from `gaming-optimization-guide.md`.

## In scope

- check current power plan
- explain recommended gaming settings
- offer Game Mode verification
- suggest visual-effect tuning
- surface background apps that commonly affect gaming
- present optional actions with clear confirmation

## Out of scope

- disabling unrelated Windows services by default
- broad registry tuning unrelated to gaming
- development-environment optimization
- silent process termination

## Default flow

1. inspect current system state
2. show recommended baseline settings
3. offer low-risk actions first
4. separate medium-risk actions into explicit opt-in steps
5. provide rollback notes

## Planned actions

### Low-risk

- report current power plan
- report display resolution and refresh rate
- report Game Mode state if available
- list high-impact background apps
- provide recommended handheld gaming profile

### Medium-risk optional

- switch to a gaming-focused power plan
- adjust selected visual-effect settings
- open relevant Windows settings pages

## Safety notes

The script should start in report mode. Any setting changes should be grouped, explained, and confirmed before execution.

## Success criteria

- users can understand what the script will change before anything happens
- the script is useful even if the user declines all changes
- the default path avoids wide registry modifications
