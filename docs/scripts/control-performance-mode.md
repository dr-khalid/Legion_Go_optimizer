# `control-performance-mode.ps1`

## Goal

Provide a clear interface for choosing or explaining Legion Go performance modes, TDP targets, and thermal tradeoffs.

## Source inspiration

This is based on `legion-performance-control.ps1`.

## In scope

- explain Quiet, Balanced, and Performance-style modes
- show recommended use cases for each mode
- detect available power information where possible
- attempt safe automation only if supported by the platform
- fall back to guided manual steps when direct control is unavailable

## Out of scope

- hidden vendor-specific hacks with unclear behavior
- permanent hardware changes
- undocumented WMI or registry writes without validation

## Planned user flow

1. inspect current power and system state
2. explain available performance modes
3. recommend a mode by scenario
4. attempt change only when safe and supported
5. show manual fallback instructions

## Risk notes

This script can affect battery life, noise, and thermals. Changes should be visible and reversible.

## Success criteria

- users understand the tradeoff between performance and thermals
- the script is still useful even when automatic control is not possible
- any automated control path is clearly labeled
