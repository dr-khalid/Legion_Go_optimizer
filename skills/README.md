# Skills Folder

## Purpose

This folder contains markdown playbooks for AI agents working in the `Legion_Go_optimizer` repository.

Each skill should help an agent do one focused job well, such as:

- collecting diagnostics
- classifying running processes
- deciding what can be closed before gaming
- preparing a cleanup plan without touching protected Windows components

## Current skills

- `system-diagnostics.md`
- `process-classification.md`
- `gaming-cleanup-planning.md`

## How to use these files

An AI agent should:

1. read `docs\agent-workflow.md`
2. open the relevant skill file
3. perform the diagnostic or planning task
4. document findings before running actions

## Scope rule

These skill files are operational guidance, not proof that an action is always safe. Agents must still validate the live system state before making changes.
