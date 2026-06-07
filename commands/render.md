---
description: Produce the finished Ramble video — voiceover + slides — and return the hosted URL.
argument-hint: "[projectId — omit to use the project from this session]"
allowed-tools: mcp__ramble__ramble_render, mcp__ramble__ramble_get_project, mcp__ramble__ramble_open_project
---

Produce the video for: **$ARGUMENTS**

1. If no projectId was given, use the project you just authored in this session.
2. Call **`ramble_render(projectId)`**. Ramble does the rest server-side: generates the AI voiceover if missing, attaches each slide to its word segments, rasterizes the HTML slides, and renders the final MP4. It returns a hosted `/v/<id>` URL + a watch URL.
3. Report back the coverage line it returns (`Slides: N / M segments … edge-to-edge ✓`). **If it flags uncovered or double-anchored paragraphs, surface that** — author a slide per uncovered beat and re-render rather than shipping a gap.
4. Offer to `ramble_open_project` so the user can review playback and record their own voiceover take over the AI draft.

This can take ~a minute for longer scripts. The script + slides must already exist (use `/ramble:draft` and `/ramble:slide`, guided by `narrative.md`).
