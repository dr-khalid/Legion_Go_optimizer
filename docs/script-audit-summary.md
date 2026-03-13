# Script Audit Summary

## Summary

The original workspace was useful, but it mixed together documentation, diagnostics, aggressive system tuning, and game-specific fixes without much separation. This repo should keep the good ideas while removing duplication and reducing risk.

## Key findings

### 1. Duplicate Legion Go optimization scripts

`legion-go-optimize.ps1` and `legion-go-optimize-fixed.ps1` cover nearly the same ground. The future repo should keep one core optimization path only.

### 2. FC 26 tooling overlaps

The FC 26 scripts split across setup, resolution fixes, monitoring, and live alerts. In a cleaner repo, these should become one setup document or script and one optional monitoring component.

### 3. Diagnostics are valuable

`system-diagnostic.ps1` and parts of `gaming-stability-fix.ps1` provide the most reusable troubleshooting logic because they help users understand problems before changing the system.

### 4. Some scripts are much riskier than others

The broadest and most invasive script is `coding-optimization.ps1`, which changes services, registry values, and power-related behavior beyond gaming-specific needs. Future Legion Go repo work should avoid using that style as the default model.

### 5. Documentation matters

`gaming-optimization-guide.md` proves that some of the knowledge is better delivered as guidance instead of immediate automation.

## Recommended keep, merge, or drop decisions

| Source item | Recommendation | Reason |
| --- | --- | --- |
| `legion-go-optimize.ps1` | Merge | Good concept, too much overlap |
| `legion-go-optimize-fixed.ps1` | Merge | Cleaner duplicate of the same idea |
| `legion-performance-control.ps1` | Keep | Useful handheld-specific capability |
| `set-gaming-resolution.ps1` | Keep | Low-risk and practical |
| `system-diagnostic.ps1` | Keep | Strong diagnostic foundation |
| `gaming-stability-fix.ps1` | Split | Keep diagnostic parts, narrow the fix logic |
| `tekken8-fix.ps1` | Keep selectively | Useful if orientation issues remain common |
| `fc26-fix-tool.ps1` | Merge | Scope is too broad in current form |
| `fc26-resolution-fix.ps1` | Merge | Better folded into one setup path |
| `fc26-cheat-detector.ps1` | Optional | Niche and heuristic-heavy |
| `fc26-live-alert.ps1` | Optional | Overlaps with detector and may be noisy |
| `gaming-optimization-guide.md` | Adapt | Good source for docs and rationale |

## Recommended repo direction

Build the new project around:

- safe baseline optimization
- diagnostics-first workflow
- clear separation between generic and game-specific tooling
- smaller scripts with narrower responsibility
- markdown guidance for risky topics before automation
