# Gaming Cleanup Policy

## Purpose

This document defines the staged policy for reducing background load before gaming on this Legion Go system. The goal is to free RAM and reduce avoidable background activity while protecting core Windows stability.

## Why this policy exists

The latest baseline snapshot showed:

- total RAM of about `9.69 GB`
- used RAM of about `8.22 GB`
- free RAM of about `1.47 GB`

That means the system is already under heavy memory pressure before a game even starts. Cleanup should therefore focus on high-value user applications first, not risky service changes.

## Main rule

Close optional user applications before touching startup settings or services.

## Cleanup stages

### Stage 0: capture a fresh baseline

Before any cleanup, collect:

- free RAM
- top processes by memory
- top processes by CPU
- launchers currently running
- optional vendor tools

This step is mandatory because the exact process mix changes over time.

### Stage 1: close obvious user applications

These are the best first targets on this machine:

- `Code`
- `msedge`
- `OneDrive`
- `XboxPcApp`
- `RazerCortex`

Why these first:

- they are not core Windows components
- they can consume significant RAM
- closing them usually has low system risk

### Stage 2: close optional launchers and helpers

These should be reviewed next:

- `EADesktop` after game launch if no longer needed
- extra `steamwebhelper` load if Steam browser windows or overlays are not needed
- `RadeonSoftware` if only the UI is open and no tuning work is being done

These are not always safe to close blindly, so they belong in a separate stage.

### Stage 3: review handheld and vendor extras

These need caution and should only be reduced when their role is understood:

- `LegionSpace`
- Lenovo support daemons
- Logitech updater components
- Razer background services and helper apps

The rule here is:

- close user-facing apps first
- document service names before stopping anything
- avoid disabling startup or services in the same pass unless specifically approved

### Stage 4: review startup reductions

If more headroom is still needed after closing active apps, review startup entries such as:

- Steam
- OneDrive
- EA Desktop
- Edge auto-launch
- Razer tools

This is a policy stage, not an automatic action stage.

### Stage 5: service review

Only after the first four stages should agents even consider service changes. Candidates for future review may include:

- non-essential Razer services
- optional updater services
- optional vendor extras

Service changes should never be the first response to normal gaming preparation.

## Protected processes

The following should be treated as protected by default:

- `explorer`
- `dwm`
- `svchost`
- `Memory Compression`
- `Secure System`
- `MsMpEng`
- core audio, input, and graphics infrastructure

These support the shell, rendering, security, or memory model and should not be blindly targeted by cleanup logic.

## Classification table for this machine

| Item | Category | Default action | Reason |
| --- | --- | --- | --- |
| `Code` | Safe to close | Close first | Heavy user application, not needed for gaming |
| `msedge` | Safe to close | Close first | Multiple browser processes consuming RAM |
| `OneDrive` | Safe to close | Close first | Sync client not needed during gaming |
| `XboxPcApp` | Safe to close | Close first | Optional store app overhead |
| `RazerCortex` | Safe to close | Close first | Optional tuning layer, not core Windows |
| `EADesktop` | Maybe close | Close after launch if not needed | Game-dependent launcher |
| `steamwebhelper` | Maybe close | Reduce only when safe | Steam may still need some helper processes |
| `LegionSpace` | Investigate further | Keep unless role is confirmed | Handheld-specific controls may rely on it |
| Razer services | Investigate further | Review later | Could affect devices or integrations |
| `explorer` | Leave alone | Do not target | Windows shell |
| `dwm` | Leave alone | Do not target | Desktop composition and rendering |
| `svchost` | Leave alone | Do not target | Windows service host |
| `Memory Compression` | Leave alone | Do not target | Memory management |
| `Secure System` | Leave alone | Do not target | Security/virtualization component |
| `MsMpEng` | Leave alone | Do not target blindly | Microsoft Defender engine |

## Execution rules for AI agents

An AI agent following this repo should:

1. capture baseline metrics
2. classify running items
3. propose the exact close list
4. get approval for the action set
5. run scoped commands
6. capture the after-state

## Recommended command style

When commands are eventually run, use targeted process IDs or exact process names for approved user apps only.

Example command patterns:

```powershell
Get-Process Code, msedge, OneDrive, XboxPcApp, RazerCortex -ErrorAction SilentlyContinue
```

```powershell
Stop-Process -Id <PID>
```

```powershell
Get-Process | Sort-Object WorkingSet64 -Descending | Select-Object -First 20 ProcessName, Id, @{Name='WS_MB';Expression={[math]::Round($_.WorkingSet64 / 1MB, 1)}}
```

## What not to automate by default

- disabling services
- registry edits
- startup modifications
- killing unknown vendor daemons
- stopping security components

## Success criteria

This policy succeeds when:

- gaming sessions start with more available RAM
- optional apps are reduced first
- the cleanup process is easy to explain
- Windows stability is preserved
- future agents can follow a repeatable order of operations
