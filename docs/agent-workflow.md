# AI Agent Workflow

## Purpose

This document explains how future AI agents should operate inside this repository when preparing the Legion Go for gaming. The goal is to keep the work structured, safe, and repeatable before any high-impact command is run.

## Operating principles

- diagnose before changing anything
- prefer markdown planning before script execution
- separate observation from action
- keep high-risk commands opt-in
- never treat core Windows processes as cleanup targets by default

## Standard workflow

### 1. Capture a baseline

The first step is always to inspect the current system state. That baseline should include:

- memory usage
- top processes by memory and CPU
- common user apps and launchers
- startup entries
- non-Windows auto-running services
- running scheduled tasks when relevant

### 2. Classify findings

After gathering data, the agent should sort findings into categories:

- safe to close before gaming
- maybe close if not needed
- leave alone
- investigate further

### 3. Write the findings down

Before running cleanup actions, the agent should document:

- what is consuming memory
- what is consuming CPU
- what background apps are optional
- what should not be touched
- what proposed actions come next

### 4. Ask for approval before actions

Agents should not automatically stop applications or disable services based only on a diagnostic pass. The cleanup plan should be presented first.

### 5. Run only scoped actions

When cleanup begins, actions should target user-approved items such as:

- browsers
- editors
- cloud sync tools
- launchers not required after game start
- overlays or vendor extras that are known to be optional

### 6. Re-check after cleanup

After any cleanup step, the agent should compare:

- free RAM before and after
- top process list before and after
- whether required game tools are still available

## Current baseline observations

The latest live diagnostic snapshot showed:

- only about `1.47 GB` free RAM before gaming
- large memory use from VS Code, Edge, Steam web helpers, Xbox app, Legion Space, OneDrive, and Razer Cortex
- multiple startup entries for Steam, OneDrive, EA Desktop, Edge auto-launch, and Razer tools
- several non-Windows auto-running services that may deserve review later, especially Razer and Lenovo extras

## Default safe targets

These are good first candidates to review for gaming cleanup:

- `Code`
- `msedge`
- `OneDrive`
- `XboxPcApp`
- `EADesktop` when not needed
- extra `steamwebhelper` activity
- `RazerCortex` and related optional Razer apps

## Default protected targets

These should not be killed or disabled casually:

- `explorer`
- `dwm`
- `svchost`
- `Memory Compression`
- `Secure System`
- `MsMpEng`

## How this document relates to the skills folder

This runbook is the high-level flow. The `skills` folder contains the narrower playbooks an agent can follow for specific tasks such as diagnostics, process classification, and cleanup planning.
