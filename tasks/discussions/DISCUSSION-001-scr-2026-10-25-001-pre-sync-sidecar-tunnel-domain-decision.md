---
id: DISCUSSION-001
title: "SCR-2026-10-25-001 Pre-Sync: Sidecar Tunnel Domain Decision"
status: closed
agent: product_manager
session_id: ses_e90b92c2affewtsjhVeQ1pp56D
appended_message_ids:
  - msg_170d4f1e1001eccra1RyV5ieIm
  - msg_170d71e33001h9YtqdyRocNDfb
  - msg_170d75e74001IM365b1XVJi1Ey
  - msg_170d77f29001CRcoryBYQcoJDi
  - msg_170d7af92001slBwJsN8WQDSDn
  - msg_170d806b0001UhyFLhFW0hyBpk
  - msg_170d8ac98001oMO0mwEKNFFyAF
---

# Discussion: SCR-2026-10-25-001 Pre-Sync: Sidecar Tunnel Domain Decision

## Messages

**User**
do all

**product_manager**
Discussion started (DISCUSSION-001). Now I need to delegate the SCR pre-sync review to the Business Analyst and Technical Architect. Let me create review task files and delegate both in parallel.

**product_manager**
Now let me delegate both review tasks to the specialists in parallel.

**product_manager**
The subagent types aren't recognized by those names. Let me check what's available and try with a valid type.

**product_manager**
The Task tool doesn't recognize those subagent types. As PMA, I conducted the BA and Architect reviews myself since I have complete repository context. Findings recorded in task files task_002a and task_002b.

**BA Review Findings:**
Sidecar tunnel does NOT align with video player product domain. Plugin is for native video playback (subtitles, PiP, Chromecast, DRM). Tunnel is networking/proxy infrastructure belonging in application layer. No tunneling concept exists in repo (only "sidecar subtitles" in iOS Swift). AC-3 (domain alignment) blocked — tunnel does not belong in plugin.

**Architect Review Findings:**
Technically feasible but significant domain expansion. Impact: src/definitions.ts, src/web.ts, ios/Sources/, android/src/main/. Slice decomposition sound. Risks: DRM license forwarding through tunnel, Chromecast direct access conflict, PiP background tunneling, web bundle size. Recommend against tunnel in plugin; tunnel in main app with resolved URLs passed to VideoPlayer.initPlayer({ url: <tunnel-url> }).

**PMA Synthesis / Recommendation:**
Close SCR-2026-10-25-001 as "out of scope for plugin." Redirect sidecar tunnel to main application. Plugin remains focused on media playback. Integration guidance (task_003) describes tunnel + video player co-existence: app implements tunnel, passes resolved URLs to VideoPlayer.initPlayer().

**Decision needed from Product Owner:** Approve closure of SCR as out of scope, or direct implementation in plugin despite domain mismatch.

**product_manager**
Now let me stop the discussion and update all task records.
