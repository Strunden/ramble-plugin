# Ramble — Claude Code plugin

> **Generated artifact — do not edit here.** This repo is published from the
> private Ramble app repo via `npm run publish:plugin`. Edit the plugin
> (skill, commands, README) there; changes land here on publish.

Author full presentation videos from Claude Code. You write (or have Claude draft)
a script; Claude cuts it into beats, designs on-brand slides anchored to the spoken
words, and Ramble renders a finished ~3-minute video with an AI voiceover — which
you can re-record in your own voice.

## What this plugin gives you

- **A slide-authoring skill** — the editorial doctrine (`narrative.md`: write for
  the ear, cut at value-turns, say ≠ show) + the v10 design system (`design.md`) +
  a library of on-brand HTML slide exemplars.
- **Slash commands** — `/ramble:draft`, `/ramble:slide`, `/ramble:render`,
  `/ramble:review`, `/ramble:doctor`.

The `ramble_*` **tools** (create a project, set the script, generate the voiceover,
author HTML slides, `ramble_render` the final video) are **not** bundled here — they
come from the **hosted Ramble MCP server**, which you connect once.

## Connect Ramble (one time)

The tools authenticate with your Google account — no token to paste, no local
server, no relaunch. Two ways, pick either:

1. **Drop a file in your project (no terminal).** At
   **ramble.video → account menu → Connect Claude Code**, download `.mcp.json` into
   your project folder. The next time you run `claude` there, it asks once to
   approve, then connects.
2. **One command (available everywhere):**
   ```
   claude mcp add --transport http --scope user ramble https://mcp.ramble.video/mcp
   ```

Then run `/mcp` → pick **ramble** → sign in with Google. Verify with
`claude mcp get ramble` (it should say *Connected*) or `/ramble:doctor`.

> Access is currently limited to the Ramble beta cohort. If sign-in is denied,
> your email isn't on the allowlist yet.

## Install the plugin

```
/plugin marketplace add Strunden/ramble-plugin
/plugin install ramble@ramble-marketplace
```

This gives you the skill + commands. Connect the MCP (above) for the tools.
