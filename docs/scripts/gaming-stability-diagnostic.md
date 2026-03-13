# `gaming-stability-diagnostic.ps1`

## Goal

Diagnose likely causes of gaming crashes, shutdowns, or unstable sessions on the Legion Go without immediately applying aggressive fixes.

## Source inspiration

This spec is based on the diagnostic and event-log ideas in `gaming-stability-fix.ps1`.

## In scope

- inspect recent shutdown or thermal-related events
- summarize power and battery context
- report system pressure during instability investigation
- identify common stability risk factors
- suggest next steps based on findings

## Out of scope

- automatic registry-heavy tuning
- automatic virtual-memory rewriting by default
- broad service changes

## Planned report sections

### Event evidence

Recent critical or thermal-related entries that may explain instability.

### Hardware and power context

Battery state, power mode, and other indicators that may affect sustained gaming.

### Resource pressure

CPU, memory, and storage conditions that can contribute to instability.

### Next-step guidance

Recommendations such as cooling checks, background load reduction, or targeted follow-up scripts.

## Safety notes

Any future remediation features should be separated from the core diagnostic mode and presented as opt-in actions.

## Success criteria

- helps users narrow down whether instability is thermal, power-related, or workload-related
- remains primarily diagnostic
- produces actionable next steps without overreaching
