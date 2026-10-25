---
task_id: task_003
title: Video player plugin integration guide for main application
complexity: standard
track: implementation
slice: foundation
status: done
assigned_to: product_manager
dependencies: []
acceptance_criteria:
  - AC-1: Installation steps documented (bun add, bunx cap sync) ✅
  - AC-2: API wiring example (initPlayer, play, pause, etc.) provided ✅
  - AC-3: Platform-specific setup notes (iOS Info.plist, AndroidManifest, web) ✅
  - AC-4: Example app reference identified (example-app/ in this repo) ✅
reopen_history: []
discussion_record: []
---

# Task: Integration Guide for Main Application

## Objective
Provide complete integration steps for adding @capgo/capacitor-video-player to the main application.

## Deliverable
Complete integration guide at tasks/todo/task_003_integration_guide.md covering:
- Installation (bun add, bunx cap sync)
- Import and API wiring (initPlayer, play, pause, seek, volume, rate, etc.)
- Platform-specific setup (iOS Info.plist, AndroidManifest, web embedded mode)
- DRM support (FairPlay iOS, Widevine Android)
- Chromecast (Android)
- Example app reference (example-app/ in this repo)
- Sidecar tunnel note: tunnel belongs in app, not plugin; pass resolved URLs to VideoPlayer.initPlayer()
