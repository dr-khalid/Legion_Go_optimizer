# Skill: Gaming Cleanup Planning

## Goal

Create a safe, staged cleanup plan that improves available memory and reduces background noise before launching a game.

## Inputs

This skill depends on:

- a fresh diagnostic snapshot
- process classification results
- user approval for any stop or disable actions

## Planning order

### Stage 1: low-risk app closures

Target obvious user applications first:

- browsers
- editors
- cloud sync tools
- optional store apps
- launchers not needed after startup

### Stage 2: optional overlay and helper reduction

Review vendor extras and overlays:

- Razer extras
- Xbox app components not required
- Steam overlay-related helpers when the user is comfortable disabling them

### Stage 3: startup and service review

Only after the easy wins are documented should the agent propose:

- startup reductions
- service review candidates
- reboot-based optimization ideas

## Required guardrails

- do not kill protected Windows processes
- do not disable services without documenting why
- do not mix diagnostics and destructive actions in one opaque step
- keep a before-and-after comparison

## Desired outcome

The cleanup plan should leave the machine in a state where:

- more RAM is available for gaming
- non-essential background apps are reduced
- the game launcher and required hardware tools still work
- the user can understand what changed
