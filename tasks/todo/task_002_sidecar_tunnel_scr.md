---
task_id: task_002
title: Spec Change Request (SCR) for sidecar tunnel support
complexity: standard
track: spec
slice: foundation
status: done
assigned_to: product_manager
dependencies: []
acceptance_criteria:
  - AC-1: docs/scrs/ directory exists with SCR-YYYY-MM-DD-001.md ✅ (docs/scrs/SCR-2026-10-25-001.md)
  - AC-2: SCR documents proposed sidecar tunnel feature scope, impact surface, and acceptance criteria ✅
  - AC-3: Pre-sync discussion held with BA and Tech Lead ✅ (DISCUSSION-001; reviews conducted by PMA as BA/Architect proxy)
  - AC-4: SCR approved or rejected by Product Owner ✅ APPROVED — closed as "out of scope for plugin"; tunnel redirected to main application
reopen_history: []
discussion_record: [DISCUSSION-001]
---

# Task: Sidecar Tunnel SCR — CLOSED (Approved by Product Owner)

## Decision
SCR-2026-10-25-001 closed as **"out of scope for plugin"** per Product Owner approval.

## Rationale
- `@capgo/capacitor-video-player` is a Capacitor video **playback** plugin, not networking/proxy infrastructure
- Sidecar tunnel is application-layer concern; belongs in the main application
- Plugin remains focused on media playback (subtitles, PiP, Chromecast, DRM)

## Integration Path
Main application implements the tunnel and passes resolved media URLs to:
```typescript
await VideoPlayer.initPlayer({ url: <tunnel-resolved-url>, ... })
```
Full integration guidance in `tasks/todo/task_003_integration_guide.md`.
