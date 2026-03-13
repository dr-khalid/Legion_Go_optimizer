# Skill: System Diagnostics

## Goal

Capture a reliable snapshot of the current Windows runtime state before any gaming cleanup action is attempted.

## When to use

Use this skill when:

- preparing the device for gaming
- trying to understand why memory is already low
- investigating background process load
- collecting a before-state ahead of cleanup

## Minimum checks

The agent should gather:

- total, used, and free memory
- top processes by working set
- top processes by CPU where useful
- common background apps and launchers
- startup entries
- non-Windows auto-running services
- running scheduled tasks if they appear relevant

## Output format

The result should clearly state:

1. the memory situation
2. the biggest background consumers
3. likely close candidates
4. protected items that should not be touched

## Current known pressure points

From the latest snapshot on this machine:

- RAM is tight before gaming
- VS Code is consuming a large amount of memory
- Edge has many child processes running
- Steam web helpers are active
- OneDrive is active
- Xbox app is active
- Legion Space is active
- Razer Cortex and related software are active

## Command guidance

The diagnostic step should favor read-only commands such as:

- `Get-Process`
- `Get-CimInstance Win32_OperatingSystem`
- `Get-CimInstance Win32_StartupCommand`
- `Get-CimInstance Win32_Service`
- `Get-ScheduledTask`

## Do not do during this skill

- kill processes
- disable services
- change startup settings
- change registry values
