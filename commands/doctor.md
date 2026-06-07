---
description: Health-check the Ramble plugin — backend reachability, MCP tools, and prerequisites.
allowed-tools: Bash, mcp__ramble__ramble_list_projects
---


Run a quick diagnostic of the Ramble authoring setup and report PASS/FAIL per line:

1. **Backend reachable** — curl `${RAMBLE_BASE_URL:-http://localhost:3456}/api/projects` (or the app root). If it fails, tell the user to start Ramble with `npm run dev` in the ramble repo, or set `RAMBLE_BASE_URL` if their instance is elsewhere.
2. **MCP wired** — call `ramble_list_projects`. If it errors, the MCP server didn't start: check that `node_modules` exists at the plugin root (`npm install` in the ramble repo) and that Node ≥18.
3. **Skill present** — confirm the `ramble-slide-authoring` skill is loaded (its design.md + exemplars are what make slides on-brand).
4. **Render path** — confirm `ramble_render` is available; it produces the finished MP4 (voiceover + slides) server-side and returns a hosted `/v/<id>` URL. ffmpeg must be on PATH for the app's render step.

Keep the output to one line per check. End with the single most important next action if anything failed.
