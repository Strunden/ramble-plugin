---
description: Health-check the Ramble plugin — connection, auth, and MCP tools.
allowed-tools: mcp__ramble__ramble_list_projects
---

Verify the Ramble plugin is correctly connected. Use the **MCP tool** — NOT a shell `curl`. The plugin's host (`RAMBLE_BASE_URL`) and token live inside the MCP server process, not your shell; a `curl` in this terminal reflects your shell, not the plugin, and will mislead you (it defaults to localhost).

1. Call **`ramble_list_projects`** and interpret the result:
   - **Returns a list →** connected and authenticated. Report the project count and that the token is valid. Done.
   - **Auth error (401 / "Invalid, expired, or revoked Ramble token") →** the token is missing or wrong. Tell the user to generate one at **ramble.video → account menu → Connect Claude Code**, then re-enter it when the plugin prompts (a fresh `/plugin install` re-prompts for it).
   - **Connection error (ECONNREFUSED / unreachable) →** the configured backend is unreachable. The plugin ships pointed at the hosted backend; for local dev, run `npm run dev` and override `RAMBLE_BASE_URL`.
2. Report the single most important next action.
