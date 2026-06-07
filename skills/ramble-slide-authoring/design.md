# Ramble slide design system — for the authoring agent

You are authoring **HTML slides** for a Ramble video via `ramble_create_html_slide`.
This file is your design law. The exemplar library (`exemplars/`) is your starting
floor. **Never author a slide from scratch** — pick the closest exemplar for the
script moment, then adapt its content. Restraint is the brand: the aesthetic *is*
the product. A slide that is calm, typographic, and one-idea is always better than
a busy one.

Read this whole file once before authoring a ramble's slides. Then, per slide:
**map the script moment → catalog job → exemplar file → adapt.** The protocol is
in `PROTOCOL.md`; the job→exemplar map is in `catalog.md`.

---

## 0. The hard render contract (break these and the slide breaks)

- **Canvas is exactly 1920×1080 (16:9).** Author at that size. The renderer scales
  the whole stage to fit; you never write responsive CSS. Treat 1920×1080 as fixed.
- **The slide is dropped full-bleed into a stage that already sets the page
  background.** You still MUST paint your own background on the root element —
  set `width:1920px;height:1080px` and a `background` on your outermost div. Do
  not rely on the host bg.
- **Self-contained only.** Inline `<style>` and inline `style=` attributes both
  work. External CSS files do not. **`<script> is inert` — it never runs.** So:
  no JS, no JS-driven layout, no canvas charts. All layout is static HTML/CSS.
- **CSS animations DO play** on preview and in the exported MP4. Keep them to ONE
  entrance per slide (see §6). No infinite/looping animation.
- **Fonts:** `@import` the Google Fonts line (below) at the top of your `<style>`,
  or assume Inter / Inter Tight / IBM Plex Serif are present. Use only those three.
- **Images:** data-URI (`<img src="data:image/png;base64,…">`) for self-contained
  slides, or a `/uploads/…` URL after `ramble_add_media`. Never hotlink the web.
- **No external network, no iframes, no video tags inside a slide.**

Boilerplate every slide opens with:

```html
<div style="position:relative;width:1920px;height:1080px;background:#FBFAF7;
  overflow:hidden;font-family:'Inter',system-ui,sans-serif;color:#1A1A1A;
  -webkit-font-smoothing:antialiased">
  <style>@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=Inter+Tight:wght@500;600;700;800&family=IBM+Plex+Serif:ital,wght@0,400;0,500;0,600;1,400&display=swap');</style>
  <!-- slide content -->
</div>
```

---

## 1. The one rule above all: one idea per slide

A Ramble plays under a voiceover to a *captive, obligated* audience (the wedge is
replacing a written pre-read). The viewer cannot re-skim; the slide must land in
the ~3–8 seconds it is on screen while you talk over it. So:

- **One idea per slide.** A headline, a stat, a definition, one feature. If you
  have two ideas, make two slides. The voiceover carries the connective tissue.
- **The slide reinforces the spoken line — it is not the script.** Don't transcribe
  the narration onto the slide. Show the *noun* the sentence is about (the number,
  the term, the diagram), not the sentence.
- **"Not everything is words."** Many moments need content-carrying slides
  (a feature description, a tier table, a comparison, an architecture). Reach past
  the big-word shout slides for those — see the catalog.

---

## 2. Tokens — the v10 design system (the aesthetic IS the product)

Neighbours: **iA Writer, Linear, Stripe, Apple keynote.** NOT Premiere/CapCut,
NOT TikTok. If a slide feels "energetic," it's wrong; aim for *quietly inevitable.*

```
/* Surfaces */
--paper:   #FFFFFF;   /* clean slide bg, content cards */
--bg:      #FBFAF7;   /* warm paper — the default slide background */
--card:    #FAFAFA;   /* nested panels on a paper slide */

/* Ink */
--ink:        #1A1A1A;   /* primary text */
--ink-dim:    #6B6B6B;   /* secondary / supporting text, captions */
--ink-faint:  #9A9A9A;   /* labels, kickers, axis text */

/* Rules */
--rule:      #E5E5E5;   /* hairlines, table borders, dividers */
--rule-soft: #EFEEEA;   /* barely-there separators */

/* Accent — ONE brand color. The blue is the whole palette's energy. */
--accent:      #3B5BDB;   /* the brand blue — emphasis, the ONE highlighted thing */
--accent-soft: rgba(59,91,219,0.08);  /* accent fills, highlighted table cell */

/* Secondary accents — STRICTLY for categorical encoding (e.g. distinguishing
   N services in an architecture diagram, or N series in a chart). NEVER for
   decoration, NEVER for body text. If you can avoid them, avoid them. */
--accent-2: #C97A3B;  /* ochre  (also = the face/presenter track color) */
--accent-3: #2E8B7A;  /* teal */
--accent-4: #8B5BC9;  /* purple */
```

**Color discipline (this is the whole brand):**
- A slide is paper-warm `--bg` + ink + **at most one** use of `--accent`.
- `--accent` marks *the single most important thing* on the slide — the winning
  column, the after-state, the one number that matters. If two things are blue,
  nothing is.
- Everything non-essential lives in grayscale (`--ink-dim` / `--ink-faint`). This
  is the Cole Nussbaumer move: gray everything, color the point.
- Secondary accents only appear when you are *encoding categories* (services in a
  diagram, series in a chart) and there is no other way to tell them apart.

---

## 3. Typography — two families, doing two jobs

```
Inter / Inter Tight  → chrome & display: headlines, stats, labels, kickers,
                       table text, UI-like text. Tight tracking on big sizes.
IBM Plex Serif       → reading & editorial: definitions, quotes, prose
                       descriptions, the "human voice" on a slide.
```

The serif/sans split is **load-bearing** — it's what makes Ramble read as a
writing tool, not a video tool. Use serif when the slide is *saying something in
sentences* (a definition's explanation, a quote, a feature's prose description).
Use sans for everything that is a *label, number, or name.*

**Hierarchy through size + weight, never through a third font or a second color.**
The biggest, heaviest element is the idea. Supporting text is smaller and dimmer.
Approximate display scale (px on the 1920×1080 canvas):

```
Hero number / one-word:  320–720   Inter 800, letter-spacing -0.05em
Slide headline:          88–200    Inter Tight 700, -0.03em
Section / feature name:  56–120    Inter Tight 700
Body / list item:        32–52     Inter 400–500  (serif if prose)
Kicker / label / axis:   22–28     Inter 600, UPPERCASE, letter-spacing 0.14em, dim
```

Rules:
- Headlines are 1–6 words. If it's a sentence, it belongs in the voiceover.
- ALL-CAPS only for kickers/labels (≤4 words) — never for body or headlines.
- Set tight line-height on display (`0.9–1.0`); generous on prose (`1.4–1.5`).
- Never set a prose/definition/quote in Inter. Never set a label/number in serif.

---

## 4. Layout & composition

- **Generous margins.** Keep a ~120px safe margin from every edge. Content never
  touches the frame. White space is not wasted — it's the calm.
- **Off-axis beats centered.** Centered everything reads corporate. Anchor the hero
  to a corner or one third; let negative space do the work. (Exception: a single
  section-divider word can sit dead-center.)
- **One focal point.** The eye should land in one place, then read out. Establish
  it with size contrast (the hero is 3–5× the next element).
- **Align to a grid.** Pick a left margin (e.g. 120px) and hang everything off it.
  Ragged left edges read as sloppy.
- **Don't fill the space.** A slide that's 60% empty and one idea beats a slide
  that's 100% full. Resist the urge to add.

---

## 5. Content-carrying slides (the "not everything is words" jobs)

These are the slides that make Ramble a *product-comms* tool, not a hype-reel
generator. They carry real information density without becoming cluttered:

- **Tables / comparisons:** hairline rules only (`--rule`), no fills except the
  ONE winning column in `--accent-soft`. Use ✓ / ✕ glyphs, not "Yes/No" words.
  Direct-label; no legends. Max ~4 columns, ~6 rows — beyond that, split the slide.
- **Tiers / pricing:** 2–3 columns; exactly one "recommended" gets the accent ring.
  Price is the hero of each column; features are a short bulleted list (≤5).
- **Feature spotlight:** kicker + name (sans) + a serif prose description, optional
  screenshot to the side. The description is the one place prose belongs.
- **Architecture / diagram:** boxes + arrows, C4-style. Every box is labeled; the
  flow direction is unambiguous (arrows one way). Give it a title. Highlight the
  one component the narration is about in `--accent`; the rest are gray outlines.
  Keep it to ≤7 boxes — if more, it's two diagrams.
- **Data / chart:** show the number directly when there are only 1–2 values
  (use a stat slide, not a chart). For a real comparison, bars with direct value
  labels, no gridlines, no legend, no 3D. Gray the bars, accent the one that matters.

The discipline that keeps these from getting busy: **gray the background, color the
point; hairlines not boxes; direct labels not legends; split before you cram.**

---

## 6. Motion — at most one entrance, then still

- **80% of slides need no animation.** When you add one, it's a single entrance:
  the hero `drop`s or `wipe`s in once, supporting text `slide-in`s slightly after.
- No looping, no bounce-on-bounce, no per-letter staggers, no parallax. One hit.
- Keep durations 0.4–0.6s, eased out. The slide must be fully settled and readable
  well before its span ends (slides can be on screen only ~3s).

Reusable keyframes (paste into the slide's `<style>` if used):

```css
@keyframes drop      {0%{opacity:0;transform:translateY(-32px)}100%{opacity:1;transform:none}}
@keyframes slide-in  {0%{opacity:0;transform:translateX(-40px)}100%{opacity:1;transform:none}}
@keyframes wipe      {0%{clip-path:inset(0 100% 0 0)}100%{clip-path:inset(0 0 0 0)}}
@keyframes bar-rise  {from{transform:scaleY(0)}to{transform:scaleY(1)}}
```

---

## 7. Anti-patterns (auto-reject)

- More than one `--accent` use, or accent on something non-essential.
- A headline that's a full sentence, or text transcribed from the voiceover.
- Gradients (except none — there are none here), drop shadows on text, glassmorphism,
  noise textures, decorative blobs, emoji-as-icon, stock-photo backgrounds.
- A font outside {Inter, Inter Tight, IBM Plex Serif}. A color outside the tokens.
- Prose set in sans; a label/number set in serif.
- Centered-everything corporate symmetry on a content slide.
- A table/diagram so dense it needs the viewer to pause. Split it.
- `<script>`, external CSS, hotlinked images, responsive units (vw/vh/%) for layout
  position — author in fixed px on the 1920 canvas.

---

## 8. The 10-second self-check before you attach a slide

1. **One idea?** Could the viewer state it in 4 words after a 3-second glance.
2. **Right job?** Did I pick the catalog job that matches this script moment, not
   just a big-word slide by default.
3. **One accent?** Exactly one thing is blue, and it's the most important thing.
4. **Hierarchy?** The hero is 3×+ the next element; nothing competes.
5. **Serif/sans right?** Prose in Plex Serif, labels/numbers in Inter.
6. **Breathing room?** ~120px margins, not touching edges, not 100% full.
7. **Renders?** Fixed 1920×1080 root with its own bg; no JS-dependence; one entrance.

If any answer is no, fix it before attaching. The floor is high on purpose.
