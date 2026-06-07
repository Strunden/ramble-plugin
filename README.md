# Ramble — Claude Code plugin

Author full presentation videos from Claude Code. You write (or have Claude draft)
a script; Claude cuts it into beats, designs on-brand slides anchored to the spoken
words, and Ramble renders a finished ~3-minute video with an AI voiceover — which
you can re-record in your own voice.

This plugin bundles:
- **MCP tools** (`ramble_*`) — create a project, set the script, generate the
  voiceover, author HTML slides, and `ramble_render` the final video.
- **A slide-authoring skill** — the editorial doctrine (`narrative.md`: write for
  the ear, cut at value-turns, say ≠ show) + the v10 design system (`design.md`) +
  a library of on-brand HTML slide exemplars.
- **Slash commands** — `/ramble:draft`, `/ramble:slide`, `/ramble:render`,
  `/ramble:review`, `/ramble:doctor`.

## Install

```
/plugin marketplace add Strunden/ramble-plugin
/plugin install ramble@ramble-marketplace
```

## Prerequisite: a Ramble backend

The plugin talks to a running Ramble instance over REST (the heavy lifting — TTS,
slide rasterization, video render — happens there). Point it at one with the
`RAMBLE_BASE_URL` env var; it defaults to `http://localhost:3456`.

- **Local:** run the Ramble app and leave `RAMBLE_BASE_URL` unset.
- **Hosted:** set `RAMBLE_BASE_URL` to your Ramble URL (a gated instance also needs
  the appropriate access credentials).

Run `/ramble:doctor` after installing to confirm the backend is reachable.

## Flow

1. `/ramble:doctor` — health check.
2. `/ramble:draft <what you want to explain>` — script, chunked into beats.
3. `/ramble:slide` — one on-brand slide per beat.
4. `/ramble:render` — produce the MP4; returns a hosted watch URL.
5. Open the project to review and record your own voiceover.

---

The MCP server ships as a single dependency-free bundle (`mcp-server.bundle.mjs`),
so no `npm install` is needed to run the plugin.
