# Authoring protocol — pick & adapt, never from scratch

This is the loop the agent runs to slide a whole ramble. The quality comes from
**design.md (the law) + the exemplar floor**, not from cleverness per slide. You
pick the right exemplar and adapt its content. That's the job.

## Once, before authoring any slides

1. Read `design.md` end to end. It is the law.
2. Skim `catalog.md` so you know the 14 jobs and which exemplar serves each.
3. Confirm the word timeline exists (`ramble_generate_tts` has run) so you can
   anchor by phrase.

## Per slide

1. **Read the next script chunk** (one beat — roughly one sentence or idea).
2. **Pick the job.** Scan the catalog's "reach for it when…" column; choose the one
   that matches. If two fit, prefer the more *content-carrying* one (a comparison
   over a big-word) — this is product comms, not a hype reel. Default-to-big-word
   is the most common mistake; resist it.
3. **Open that exemplar HTML.** It is your starting floor — correct tokens,
   spacing, hierarchy, one entrance animation already in place.
4. **Adapt content only.** Swap the words/numbers/rows for this moment's content.
   Keep the structure, the tokens, the type scale, the single-accent discipline.
   - Adjust the auto-sizing notes in the exemplar's comments (e.g. shrink the hero
     font for a longer number) but stay within the documented scale.
   - If the moment needs N rows/columns/boxes, follow the exemplar's max and the
     "split before you cram" rule.
5. **Run the §8 self-check** (in `design.md`). One idea, one accent, hierarchy,
   serif/sans correct, margins, renders. Fix before attaching.
6. **Attach** with `ramble_create_html_slide(projectId, html, phrase)` — quote the
   EXACT consecutive words from the script for `phrase` so it anchors to stable
   word-ids over the right span.
7. **Vary the composition** across consecutive slides (alternate the off-axis
   anchor corner, alternate stat vs content) so the ramble has rhythm and doesn't
   feel like a single repeating template.

## When no exemplar fits

Rare. First ask: is this really a new job, or am I forcing it? If genuinely new,
author from `design.md` tokens + boilerplate, obeying every rule, and keep it as
restrained as the closest exemplar. Then it becomes a candidate for a new exemplar.

## Choosing the slide *rate*

Not every sentence gets a slide. A slide holds for the span you anchor it to
(~3–8s). Slide the *beats that benefit from a visual* — a number, a term, a
contrast, a diagram. Let the face/voiceover carry the connective narration. A good
product-comms ramble is maybe one slide per 1–3 sentences, not one per sentence.

## Exemplar file conventions

- One file per job, named for the job (`big-stat.html`, `comparison-table.html`…).
- Each is a **complete, attachable slide** — opens with the §0 boilerplate root
  (fixed 1920×1080 + own bg), self-contained, one entrance animation.
- A top-of-file HTML comment block states: **JOB**, **WHEN**, **ADAPT** (which
  fields to swap), and **RULES** (the 1–2 make-or-break rules). The agent reads
  that comment to know what to change.
- Placeholder content is realistic SaaS product-comms copy (so a rendered exemplar
  looks like a real slide, and so the agent sees the intended density), not lorem.
