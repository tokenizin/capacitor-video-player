---
task_id: task_002a
title: BA review of SCR-2026-10-25-001 (sidecar tunnel requirements)
complexity: standard
track: spec
slice: foundation
status: done
assigned_to: product_manager (acting as BA - no business_analyst subagent type available)
dependencies: [task_002]
acceptance_criteria:
  - AC-1: Review SCR-2026-10-25-001.md for requirements completeness
  - AC-2: Validate acceptance criteria are measurable and testable
  - AC-3: Confirm product truth alignment (does tunnel belong in plugin or main app?)
  - AC-4: Provide BA findings and recommendations to PMA
reopen_history: []
discussion_record: [DISCUSSION-001]
---

# Task: BA Review of SCR-2026-10-25-001

## Objective
Review the sidecar tunnel SCR from a business analysis / requirements perspective.

## SCR Document
`docs/scrs/SCR-2026-10-25-001.md`

## Key Questions for BA
1. Does sidecar tunnel support align with the video player product domain?
2. Are the acceptance criteria measurable and testable?
3. Should this feature live in the plugin or the main application?
4. What is the user value proposition?

## Deliverable
BA findings and recommendations recorded in DISCUSSION-001 and task file.

# BA Review Findings (from product_manager acting as BA)

## Summary
Sidecar tunnel support does NOT align with the video player product domain. The `@capgo/capacitor-video-player` plugin is a native video playback plugin for Capacitor apps — its purpose is playing video in native fullscreen/embedded players with subtitles, PiP, Chromecast, and DRM. A sidecar tunnel is networking/proxy infrastructure, which belongs in the application layer, not in a media playback plugin.

## Work Performed
- Read SCR-2026-10-25-001.md in full
- Analyzed product domain from README.md, src/definitions.ts, and native platform code
- Confirmed no tunneling concept exists anywhere in the repository (only "sidecar subtitles" references in iOS Swift code)

## Acceptance Criteria Coverage
- AC-1: Review SCR for requirements completeness — SATISFIED (SCR is complete and well-structured)
- AC-2: Validate acceptance criteria are measurable and testable — SATISFIED (AC-1 through AC-8 are measurable)
- AC-3: Confirm product truth alignment — BLOCKED (tunnel does NOT belong in video player plugin; recommend main application)
- AC-4: Provide BA findings and recommendations to PMA — SATISFIED (this document)

## Documentation Impact
- SCR document created at docs/scrs/SCR-2026-10-25-001.md
- No product docs need updating (tunnel not in plugin domain)

## Open Risks
- If Product Owner insists on tunnel in plugin, it would require expanding plugin scope beyond video playback (domain creep)
- Tunnel auth, protocol selection, and DRM interaction are unresolved

## Recommended Next Step
Present findings to Product Owner. Recommend redirecting sidecar tunnel implementation to the main application. If PO approves, close SCR as "not in plugin scope" and provide integration guidance (task_003) for tunnel + video player co-existence in the app.

