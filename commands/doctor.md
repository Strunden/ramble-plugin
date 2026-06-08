---
description: Health-check the Ramble connection — is the hosted MCP connected and authenticated?
allowed-tools: mcp__ramble__ramble_list_projects
---

Verify Claude Code is connected to the hosted Ramble MCP. The `ramble_*` tools come from a remote server (`https://mcp.ramble.video/mcp`) authenticated with your Google account via Cloudflare Access — there is no local server, no token, and no `RAMBLE_BASE_URL` to check. Do NOT shell out to `curl`; use the MCP tool.

1. Call **`ramble_list_projects`** and interpret the result:
   - **Returns a list →** connected and authenticated. Report the project count. Done.
   - **Tool not found / "No such tool" / the `ramble` server isn't listed in `/mcp` →** the remote MCP isn't connected yet. Tell the user to connect it (one time):
     - Easiest: at **ramble.video → account menu → Connect Claude Code**, download the `.mcp.json` into their project folder (Claude Code picks it up and asks once to approve), **or** copy the one-line `claude mcp add --transport http --scope user ramble https://mcp.ramble.video/mcp`.
     - Then run **`/mcp`** → pick **ramble** → sign in with Google in the browser that opens.
   - **Auth error / 401 / "needs authentication" →** the server is added but the OAuth session isn't active. Tell the user to run **`/mcp`** → select **ramble** → **Authenticate**, and sign in. If sign-in fails, confirm their email is on the Ramble beta allowlist.
2. Report the single most important next action.
