---
task_id: task_001
title: Release plugin v8.2.16 (tag push -> npm publish -> GitHub release)
complexity: tiny
track: implementation
slice: foundation
status: blocked
assigned_to: product_manager
dependencies: []
acceptance_criteria:
  - AC-1: Version bumped in package.json from 8.2.15 to 8.2.16 ✅ (committed locally as d81182d)
  - AC-2: Git tag v8.2.16 created locally ✅ — PUSH TO ORIGIN BLOCKED (403 permission denied)
  - AC-3: build.yml triggered (tag push) and completes successfully — PENDING push
  - AC-4: Package staged to npm via npm stage publish — PENDING push
  - AC-5: GitHub release created — PENDING push
reopen_history: []
discussion_record: []
---

# Task: Release plugin v8.2.16 — BLOCKED (remote push denied)

## Local Work Complete
- `bun.lock` updated — committed as df002b7
- `package.json` version 8.2.15 → 8.2.16 — committed as d81182d "chore(release): 8.2.16"
- Git tag `v8.2.16` created locally

## Blocker
`git push origin main --follow-tags --tags` → **403 Permission denied** to Cap-go/capacitor-video-player
No write access to remote repository.

## Required Action (by User)
Run locally:
```bash
git push origin main --follow-tags --tags
```
This triggers `.github/workflows/build.yml` → build → npm stage publish → GitHub release.

## CI Secrets Required
NPM_TOKEN, NPM_STAGE_DISPATCH_TOKEN, PERSONAL_ACCESS_TOKEN, CLOUDFLARE_API_TOKEN, CLOUDFLARE_ACCOUNT_ID
