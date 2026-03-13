# Safety Guidelines

## Purpose

This project is meant to help optimize the Legion Go for gaming without turning every tuning idea into an aggressive system-wide script.

## Safety rules for future work

### Prefer diagnostics first

Before changing services, registry values, or device behavior, provide a way to inspect the current state and explain what the change is meant to improve.

### Keep changes scoped

A gaming optimization script should not silently become a full system-hardening or developer-environment script. Legion Go gaming actions should stay tied to gaming needs.

### Treat registry edits as high impact

Registry changes should be:

- documented
- optional
- reversible
- grouped by purpose

### Be careful with services

Stopping or disabling services can have side effects outside gaming. Any future service-related action should explain tradeoffs and include rollback instructions.

### Avoid force-killing processes unless necessary

Closing background applications can help performance, but forced termination risks data loss and poor user trust. Prefer warning lists and opt-in actions.

### Separate core features from game-specific hacks

Display setup, power guidance, and diagnostics are reusable. A fix that only helps one game should live outside the core optimization path.

### Make admin requirements explicit

Only require elevation for features that truly need it. Users should know why admin rights are requested.

## Risk tiers for future repo content

### Low risk

- diagnostics
- documentation
- display guidance
- launch option recommendations

### Medium risk

- power-plan switching
- GPU profile suggestions
- startup app guidance
- game config edits with backup

### High risk

- registry edits
- service disablement
- network stack tuning
- forced process termination

## Recommended default posture

The future repo should default to:

1. explain
2. inspect
3. confirm
4. change
5. offer rollback

That order will keep the project more trustworthy and easier to maintain.
