# Slide catalog — the key-slide taxonomy for a SaaS product-comms ramble

This is the map: **script moment → slide job → exemplar file.** Each job is a
distinct *thing a strong PM solution-review / eng RFC / designer walkthrough
needs to do.* For each: its job, when to reach for it, the 1–2 rules that make it
excellent vs mediocre, and the exemplar to start from.

The agent's loop: read the next chunk of script, find the row whose **"reach for it
when"** matches, open that exemplar, adapt. Don't default to big-word slides — a
product-comms ramble is mostly content-carrying slides (the bottom half of this
table).

| # | Job | Exemplar file | Reach for it when… |
|---|-----|---------------|--------------------|
| 1  | Title / cover            | `title.html`             | The ramble opens — name the thing + one-line frame. |
| 2  | Section divider          | `section-divider.html`   | You move to a new chapter ("Now, the architecture"). |
| 3  | Agenda / roadmap         | `agenda.html`            | Early: "here's what we'll cover" (3–5 items). |
| 4  | Big stat                 | `big-stat.html`          | One number IS the point ("40% slower", "3 teams"). |
| 5  | Definition               | `definition.html`        | You introduce a term the audience must hold. |
| 6  | Feature spotlight        | `feature-spotlight.html` | You explain ONE feature in depth (name + why). |
| 7  | Feature grid             | `feature-grid.html`      | You list 2–4 capabilities at a glance. |
| 8  | Comparison / vs          | `comparison-table.html`  | You weigh options across criteria (build vs buy). |
| 9  | Tiers / pricing          | `tiers.html`             | You explain plans/packaging (2–3 tiers). |
| 10 | Before / after           | `before-after.html`      | You contrast old-way vs new-way (the reframe). |
| 11 | Architecture / diagram   | `architecture.html`      | You show how the system fits together (RFC core). |
| 12 | Quote / testimonial      | `quote.html`             | A user/stakeholder voice carries more than your words. |
| 13 | Screenshot frame         | `screenshot-frame.html`  | The UI itself is the evidence (mock walkthrough). |
| 14 | Takeaway / recap         | `takeaway.html`          | You land the decision / the ask / the one thing. |

Plus the built-in non-HTML layouts (`word-bomb`, `mega-quote`, `point`,
`fill-the-frame`, `numbered`, `chart-bar`) remain available for pure-emphasis
beats where a structured content slide would be overkill.

---

## The jobs in detail

### 1 · Title / cover — `title.html`
**Job:** Set the frame in one breath: what this ramble is about + the lens.
**Reach when:** First slide. Also a per-chapter cover for long rambles.
**Excellent vs mediocre:**
- Big editorial title (Inter Tight), a short serif sub-line, lots of air. One accent
  rule or one accent word — not a logo wall, not a date/author footer dump.
- Mediocre = a centered "Q3 Product Review" with a gradient. Make it feel like the
  cover of a thing worth watching: restraint, not a template.

### 2 · Section divider — `section-divider.html`
**Job:** A clean breath between chapters so the viewer re-orients.
**Reach when:** The narration turns to a new topic.
**Rule:** One or two words, lots of space, optional small kicker ("02 · Architecture").
Italic accent works here. Don't put content on a divider — it's a pause, not a slide.

### 3 · Agenda / roadmap — `agenda.html`
**Job:** Promise the shape of the next few minutes (the captive audience wants a map).
**Reach when:** Just after the title.
**Rule:** 3–5 items, numbered, left-hung off one margin, equal weight. The current
item can be in `--accent`; the rest in ink. No icons, no dates. Hierarchy is the
ordinals, big and dim; the labels read as a list, not a grid.

### 4 · Big stat — `big-stat.html`
**Job:** Make one number unforgettable.
**Reach when:** A single figure carries the beat ("we ship **40%** slower").
**Rule:** The number fills the slide (320–720px), `--accent`, off-axis. A small
UPPERCASE label in the opposite corner gives it meaning. *Exactly one number.* If
you have two numbers to compare, that's a chart or a before/after, not this.

### 5 · Definition — `definition.html`
**Job:** Install a term in the audience's head before you use it.
**Reach when:** You introduce jargon, a coined name, or a precise concept.
**Rule:** Term big in sans; an italic serif qualifier ("noun · in our system");
an accent hairline; then the explanation **in IBM Plex Serif** (this is where prose
serif shines). The serif is what makes it feel authoritative rather than a bullet.

### 6 · Feature spotlight — `feature-spotlight.html`
**Job:** Explain a single feature: what it is and why it matters.
**Reach when:** You spend real narration on one capability.
**Rule:** Kicker (the area) + name (sans, big) + a serif prose blurb, with an
optional screenshot to one side. One feature only — if you're covering several
quickly, that's the grid. The prose explains *the benefit*, not the mechanics.

### 7 · Feature grid — `feature-grid.html`
**Job:** Show 2–4 capabilities at a glance — breadth, not depth.
**Reach when:** "It also does X, Y, and Z."
**Rule:** Equal columns, each = a small accent-outlined chip + a name + one tight
line. Parallel structure (every item phrased the same way). Never more than 4 — at
5+ it's unreadable at 3 seconds; split it. No paragraphs in a grid cell.

### 8 · Comparison / vs — `comparison-table.html`
**Job:** Weigh options across criteria so the choice is visible.
**Reach when:** Build-vs-buy, us-vs-them, option A vs B vs C.
**Rule:** Hairline matrix, criteria down the left, options across the top. **Tint
exactly one column** (`--accent-soft`) — the winner — and the eye goes straight to
the recommendation. ✓/✕ glyphs (accent ✓, gray ✕), never "Yes/No". ≤4 cols, ≤6 rows.

### 9 · Tiers / pricing — `tiers.html`
**Job:** Make packaging legible — what you get at each level.
**Reach when:** You explain plans, editions, or scope tiers.
**Rule:** 2–3 columns; **exactly one** "recommended" with the accent ring + pill.
Price is each column's hero; ≤5 features as a dotted list below. Don't make all
three look equally loud — guide the eye to the recommended one.

### 10 · Before / after — `before-after.html`
**Job:** Sell the reframe — the old way struck through, the new way ascendant.
**Reach when:** "Today you do X (painful); with this, it's Y."
**Rule:** Before is dim with an accent strikethrough; after is `--accent` and
oversized. The size jump (after ≫ before) IS the argument. Two states, no more.

### 11 · Architecture / diagram — `architecture.html`
**Job:** Show how the system fits together (the heart of an eng RFC).
**Reach when:** You describe components, data flow, or a proposed change.
**Rule:** C4-style boxes + arrows. Every box labeled; arrows show one clear flow
direction; give it a title. **Highlight in `--accent` the one box the narration is
about**; everything else is a gray outline. ≤7 boxes — more = two diagrams. This is
the slide most likely to get busy; ruthlessly gray the supporting cast.

### 12 · Quote / testimonial — `quote.html`
**Job:** Borrow authority from a real voice (user, exec, the data).
**Reach when:** Someone else's words land harder than yours.
**Rule:** The quote in **IBM Plex Serif** (human voice), an oversized accent quote
mark, a small UPPERCASE attribution. Trim the quote to its sharpest clause; don't
paste a paragraph. One quote per slide.

### 13 · Screenshot frame — `screenshot-frame.html`
**Job:** Let the UI be the evidence (designer walkthrough, demo proof).
**Reach when:** "Here's what it actually looks like."
**Rule:** The screenshot sits in a clean browser/app frame on the paper bg, with a
short caption or one accent callout pointing at the thing that matters. Don't fill
the slide edge-to-edge with the image — the margin and the single callout are what
turn a screenshot into a *point*. (Image via /uploads URL or data-URI.)

### 14 · Takeaway / recap — `takeaway.html`
**Job:** Land the one thing — the decision, the ask, the memory.
**Reach when:** End of a chapter or the whole ramble.
**Rule:** One sentence, large, mostly ink with the operative phrase in `--accent`.
Optionally a tiny "the ask:" kicker. This is the slide the viewer should still see
when they close their eyes — so it's the calmest, most deliberate one. One idea.

---

## How this maps onto the existing renderer

The built-in named layouts (`mega-stat`, `vs-split`, `definition`, `feature-grid`,
`tiers`, `comparison-table`, `section-divider`, `before-after`, etc. in
`lib/visual-gen/renderers/slide-html.js`) cover many of these jobs heuristically.
The **HTML exemplars here are the high-quality, v10-on-brand twins** the agent
reaches for when it wants control — same jobs, hand-authored to the design system,
adapted per script moment. When an exemplar exists for a job, prefer it; the
built-in layout is the fallback for quick auto-generation.
