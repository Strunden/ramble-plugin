---
description: Review a Ramble project — list its script beats, slides, and gaps; open it for playback.
argument-hint: "[projectId — omit to list all projects]"
allowed-tools: mcp__ramble__ramble_list_projects, mcp__ramble__ramble_get_project, mcp__ramble__ramble_open_project
---

Review: **$ARGUMENTS**

1. If no projectId was given, `ramble_list_projects` and show them; ask which one (or pick the most recent if obvious).
2. `ramble_get_project` and produce a tight read of the storyboard:
   - The script, with each anchored clip/slide noted at the phrase it covers (`coversText`, `slideLayout`).
   - **Coverage gaps** — stretches of script with no visual, and moments that clearly want one (a stat, a comparison, a definition, a screenshot) but have none.
   - **Anchor health** — any slide whose anchor phrase no longer matches the script (drifted after an edit).
3. Recommend the 2–3 highest-value slides to add or fix, each as a one-liner (phrase → exemplar). Offer to author them via `/ramble:slide`.
4. `ramble_open_project` so the user can watch it back with the voiceover.

Keep it brief — a storyboard read, not an essay.
