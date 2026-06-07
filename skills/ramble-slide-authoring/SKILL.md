---
name: ramble-slide-authoring
description: >
  Author high-quality, on-brand HTML slides for a Ramble video via the
  ramble_create_html_slide MCP tool. Use whenever you are slideing a ramble —
  turning script beats into slides — or asked to "make slides", "add slides",
  "design the deck" for a Ramble project. Provides the v10 design system law
  (design.md), the key-slide taxonomy (catalog.md), the pick-and-adapt protocol
  (PROTOCOL.md), and a library of starting-floor exemplar HTML slides the agent
  copies and adapts rather than authoring from scratch.
---

# Ramble authoring

Authoring a ramble is two jobs in order: **write the script and cut it into beats**
(the editorial spine), then **give each beat a slide**. Do neither from scratch —
the quality floor for both lives in this skill.

## Load order

1. **`narrative.md`** — the EDITORIAL law: how to write the one-take script and cut
   it into value-turn **beats** (NOT one slide per paragraph), the SAY-vs-SHOW split,
   transitions, the arc per ICP use-case. Read this BEFORE writing any script. Each
   beat becomes one paragraph in the script and one slide.
2. **`design.md`** — the v10 design system. How a slide looks. The law. Read fully, once.
3. **`catalog.md`** — the 14 key-slide jobs and which exemplar serves each. Your
   map from a beat to the right slide.
4. **`PROTOCOL.md`** — the per-slide pick-and-adapt loop and file conventions.
5. **`exemplars/*.html`** — starting-floor slides. Each opens with the fixed
   1920×1080 boilerplate, is self-contained, and carries a top-of-file comment
   stating its JOB / WHEN / ADAPT / RULES.

The SAY (spoken line) is the script paragraph; the SHOW (slide) carries the
noun/number, never the spoken sentence. One beat = one paragraph = one slide, so
ramble_render's segment coverage stays edge-to-edge.

## The loop (full detail in PROTOCOL.md)

For each script beat: pick the catalog job → open its exemplar → swap content only
→ run the design.md §8 self-check → attach with `ramble_create_html_slide(projectId,
html, phrase)`, quoting exact script words as the `phrase` anchor.

## Dev note

`_render-check.mjs` renders every exemplar to `_renders/*.png` at 1920×1080
(`node .claude/skills/ramble-slide-authoring/_render-check.mjs` from the ramble
repo root, Playwright required) so you can eyeball a new or edited exemplar the
way the MP4 export will see it. Not part of the runtime path.
