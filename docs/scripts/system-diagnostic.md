# `system-diagnostic.ps1`

## Goal

Provide a clear gaming-readiness diagnostic for the Legion Go and Windows environment before any tuning is attempted.

## Source inspiration

This spec comes from the strongest reporting aspects of `system-diagnostic.ps1`.

## In scope

- memory usage summary
- CPU load summary
- disk free-space checks
- startup pressure overview
- background app inventory
- gaming-readiness summary

## Out of scope

- making automatic system changes
- modifying startup apps directly
- forcing process closure

## Planned report sections

### Resource health

Show RAM, CPU, and storage pressure in a simple summary.

### Background activity

Highlight commonly heavy applications such as browsers, launchers, overlays, and communication tools.

### Startup load

Estimate whether startup clutter may be affecting performance.

### Recommendations

Suggest the next best action, such as closing apps or running a more targeted script.

## Safety notes

This should remain a read-only script by design.

## Success criteria

- useful as the first script a user runs
- no admin rights required for basic reporting
- clear enough for non-expert users
