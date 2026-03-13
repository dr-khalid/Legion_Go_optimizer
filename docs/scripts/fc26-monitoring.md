# FC 26 Monitoring Concept

## Goal

Document a possible optional FC 26 monitoring feature without committing to a production script yet.

## Why documentation only

The earlier FC 26 monitoring scripts were highly heuristic. They may be useful for experimentation, but they also risk false positives and unnecessary noise. For now, this feature should remain documented rather than promoted as a core repo capability.

## Source inspiration

This note is based on `fc26-cheat-detector.ps1` and `fc26-live-alert.ps1`.

## Possible future scope

- detect obviously conflicting tools during play
- log unusual process activity around FC 26 sessions
- provide a local summary for personal troubleshooting

## Non-goals

- claiming reliable cheat detection
- encouraging punitive action based only on heuristics
- monitoring unrelated system behavior

## If built later

Any future implementation should:

- clearly label findings as heuristic
- avoid alarming wording
- separate live alerts from report generation
- include a way to disable noisy checks

## Recommendation

Keep this as a design note unless there is a very specific user need for session monitoring.
