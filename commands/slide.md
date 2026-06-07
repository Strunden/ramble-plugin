---
description: Author one on-brand HTML slide for a script moment and anchor it to the spoken phrase.
argument-hint: "<projectId> \"<exact phrase from the script>\" [what the slide should show]"
allowed-tools: mcp__ramble__ramble_get_project, mcp__ramble__ramble_create_html_slide, mcp__ramble__ramble_add_media
---

Author a slide for: **$ARGUMENTS**

Use the **`ramble-slide-authoring` skill** — it is the design law. Do not author a slide from scratch and do not invent CSS ad-hoc.

1. `ramble_get_project` to read the script and confirm the anchor phrase exists verbatim (the slide anchors to a stable word-ID range resolved from the quoted phrase).
2. Map the **script moment** → ONE exemplar via the skill's `manifest.json` (`pick_when` / `moment_phrases`). Read ONLY that exemplar file, copy it, fill the `[SLOT]`s, swap any image slots per the `image_contract` (data-URI default mock → real image via `ramble_add_media` if the user supplied one). Honor the locked rules: one idea per slide; accent = the single most important idea (may repeat within it, never a second unrelated thing); self-contained 1920×1080; ≤120px margins (the stage clips silently past 1080).
3. `ramble_create_html_slide(projectId, html, phrase)` with the exact phrase as the anchor.
4. Tell the user the slide is in; offer to open the project so they can play it back against the voiceover.

If no exemplar fits the moment, say so and use the matching built-in layout via `jobs_without_authored_exemplar` rather than forcing a bad fit.
