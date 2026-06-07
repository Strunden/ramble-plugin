---
description: Draft a new Ramble from a topic — create the project, write the script, generate AI voiceover.
argument-hint: "<topic or paste a script>"
allowed-tools: mcp__ramble__ramble_create_project, mcp__ramble__ramble_set_script, mcp__ramble__ramble_generate_tts, mcp__ramble__ramble_get_project, mcp__ramble__ramble_open_project
---

The user wants to draft a Ramble about: **$ARGUMENTS**

A Ramble is a ~1–3 minute presentation video where the **script is the durable spine**: visuals (slides) and audio (AI voiceover) hang off spoken words via stable word-IDs. Author in this order:

1. **Script first.** If the user pasted a script, use it. Otherwise write a tight, spoken-word script for the topic — short sentences, one idea per beat, conversational. Aim for the length the user asked for (default ~150 words ≈ 1 minute). The script is what everything anchors to, so make it good before anything else.
2. `ramble_create_project` with a clear name, then `ramble_set_script` with the script.
3. `ramble_generate_tts` to lay down the AI voiceover — this also produces the stable `wordTimestamps` that slides anchor to. **Do this before authoring slides** so word-IDs exist.
4. `ramble_get_project` to read back the word-anchored script, then propose 3–6 slide moments (which phrases get a slide and which exemplar fits each). Do NOT author the slides here — hand off to `/ramble:slide` per moment, or offer to continue.
5. `ramble_open_project` and give the user the URL to review playback with the voiceover.

To produce the finished video, the agent just authors (script + slides) and calls **`ramble_render`** once — Ramble generates the voiceover (if missing), attaches the slides to the word segments, and renders the MP4, returning a hosted `/v/<id>` URL. Slides can be authored before TTS; their anchors are resolved at render time.

Surface the script for the user before committing to TTS if it was AI-written — let them tweak the spine first.
