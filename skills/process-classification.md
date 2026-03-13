# Skill: Process Classification

## Goal

Turn a raw process list into an actionable decision table for gaming preparation.

## Classification buckets

### Safe to close

User applications that are not required for the game session and are known to consume memory, CPU, or background network activity.

Examples on this machine:

- VS Code
- Edge
- OneDrive
- Xbox app
- Razer Cortex

### Maybe close

Apps that depend on the game or user preference.

Examples:

- EA Desktop after launch
- Steam helpers depending on overlay use
- Legion Space depending on whether it is needed for handheld controls or power changes

### Leave alone

Core Windows and platform processes that support the shell, graphics stack, security model, memory management, or essential services.

Examples:

- `explorer`
- `dwm`
- `svchost`
- `Memory Compression`
- `Secure System`
- `MsMpEng`

### Investigate further

Services or processes that are not clearly essential but should not be stopped without understanding their role.

Examples:

- Lenovo device daemons
- Logitech updater services
- Gaming Services
- third-party emulator services

## Decision rules

- if the process is clearly user-launched and non-essential, it is a close candidate
- if the process is a launcher, decide whether it is still needed after the game starts
- if the process belongs to Windows internals, protect it by default
- if a service is auto-running in the background, document it before deciding to disable or stop it

## Expected output

The agent should produce a short table with:

- process or service name
- category
- reason
- recommended action
