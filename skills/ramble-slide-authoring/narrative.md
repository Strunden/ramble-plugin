# narrative.md — How Ramble writes the script

This is the editorial law for the Ramble engine. `design.md` governs how a slide
**looks**; this governs how the narrative is **written** and **cut into beats**
before a single slide exists.

Read this before drafting any ramble. The output is a ~3-minute video that
replaces a written six-pager or a status meeting for a **captive, obligated
internal audience** (a PM solution review, an eng RFC, a designer mock
walkthrough). They have to watch — but they will also **argue back in their head**,
because the job is to move a decision forward, not to perform. So you write like a
smart colleague across a desk who has clearly thought about the objections: calm,
dense, restraint over energy. The neighbor register is Sandwich / Stripe / Linear.
Never sell. State.

**The script is the durable spine.** It is written first, as flowing speech, then
cut into beats. Slides are placed *into* the script, never the reverse.

### What a Ramble is NOT for
Send the doc or book the meeting instead when the job is: a live debate or
real-time horse-trading; a decision that needs back-and-forth before anyone can
commit; sensitive 1:1 or performance feedback; or a pure status update with **no
decision owed and no Turn** (see §1). A ramble is one author's case, watched alone,
that *teases up* a decision — not the room where it gets made.

---

## 0. The non-negotiables

Each law is stated once here and detailed in its section. Don't restate it
elsewhere — cross-reference.

1. **SAY ≠ SHOW.** Never put the spoken sentence on the slide. The voice carries
   the *why*; the slide carries the *what*. (§4 — the load-bearing rule.)
2. **A beat is a value-turn, not a paragraph.** Cut at a turn-word; continue
   through elaboration. (§2.)
3. **BUT / THEREFORE between every beat, never AND-THEN.** (§6.)
4. **Lead with the point, not an agenda.** Beat 1 is the recommendation, the fork,
   or the felt tension — never "today I'll walk you through." One folded
   one-line map of the movements is allowed; a greeting and a contents slide are
   not. (§1, §5.)
5. **Name the objection.** A captive internal audience disagrees in their head. The
   script must surface the most likely pushback and answer it on-screen, or mark it
   open. A video that can't be argued with in the margins loses to the doc. (§1.)
6. **Write for the ear, one breath per sentence.** ~150 wpm, contractions,
   read-aloud-tested. Default budget **~450–520 spoken words / ~8–12 beats** for a
   3-min ramble. Treat as a default, not a wall — see the length escape hatch in
   §3. (§5.)
7. **Density is ideas-per-minute, never effects-per-minute.** One new thing per
   beat. (§3.)

---

## 1. Choose the arc

Every ramble maps to the same spine. **A movement = an arc stage** (Problem /
Turn / Mechanism / Payoff); a beat is one value-turn inside a movement. Pick the
ICP variant; fall back to the default when none fits. **Plan top-down:** pick the
3–5 movements first, place value-turning beats inside each, *then* write the
transitions.

### The Sandwich Spine (universal default)
Use for any recommendation, change, or thing colleagues must act on. The beat
counts below sum to the ~8–12 budget.

- **The point** (1 beat) — the recommendation, *or the fork and your lean* if no
  single call is honest yet. One declarative sentence. Pick a cold-open move (§5).
- **The Gap** (1 beat) — the concrete, felt cost of the status quo. A number or a
  named instance, not "things are slow." Source the load-bearing number (§4).
- **The Turn** (1 beat) — "here's the shift." The single pivot the whole video
  stands on. *A ramble with no identifiable Turn is broken — see the abort rule.*
- **Mechanism** (2–5 beats) — the dense core: how it actually works, beats linked
  by BUT/THEREFORE. Most beats live here.
- **The objection** (1 beat) — name the strongest pushback and answer it, or mark
  it explicitly open. This is the beat that earns the decision.
- **Payoff** (1 beat) — what concretely changes for them.
- **The Ask** (1 beat) — the three-part close (below).

### The Ask (every arc ends here, with cold-open-level rigor)
Three sentences, no recap, no CTA flourish:
1. Restate the one idea in a **fresh** sentence (not the opener verbatim).
2. Name the **specific decision owed and by when**.
3. Point to the **mechanism where it happens** — the thread, the doc, the meeting —
   so the next action is real. ("Drop your objection on the consistency tradeoff in
   the RFC thread by Thursday.")

Per ICP the decision differs: **PM** = commit / no-commit. **Eng RFC** = which
tradeoff to pressure-test. **Designer** = which direction to pick.

### PM Solution Review — *confident, decision-oriented*
1. The point: "We should ship X." / if exploratory, "The fork is A vs B — I lean A."
2. The problem, costed: one sourced metric ("activation dropped to 18% after the
   redesign — from the funnel dashboard").
3. The unexpected beat (~⅓ in): the non-obvious root cause — the lean-in moment.
4. 2–3 solution pillars, each a **contrast pair**: current limitation answered by
   the proposed change, on sibling slide layouts so the swing is visible.
5. The objection: what we give up, or who this annoys — named, then answered.
6. The Ask: the commit decision and by when.

### Eng Architectural RFC — *measured, tradeoff-honest, first-person-plural*
1. The point: the recommended approach, or the tradeoff you most want pressured.
2. **Pre-training beat** (mandatory if 3+ named components): a labeled inventory
   slide naming the parts *before* any beat reasons about their interaction.
   Naming the parts here is allowed even though it exceeds the new-term cap (§2) —
   the cap is on terms the argument *redefines*, not on a parts list.
3. The problem, made concrete and sourced: "p95 hits 1.2s at 500 concurrent users —
   p95 from Datadog" — never "scalability issues."
4. Mechanism: 2–4 value-turning beats, BUT/THEREFORE-linked, progressive-build
   diagram (one slide may persist — see §2).
5. The objection / open question: name the tradeoff you're unsure on and ask for
   that specific pushback. Distinct from the Ask — this marks what is *not* decided.
6. The Ask: the specific feedback wanted, where, by when.

### Designer Mock Walkthrough — *warm, sensory, present-tense*
1. The point: the direction in one sentence, *or* the fork between directions.
2. The user's current friction: a concrete moment of pain, shown not told.
3. The reframe: the single principle the direction is built on — the Turn.
4. Walk the mocks: **one beat per meaningful screen-state CHANGE** (not per
   screen), each tied back to the friction it resolves.
5. The unexpected detail: the one move they didn't see coming that makes it click.
6. The Ask: which direction to commit to, where to leave the call.

---

## 2. Chunk into beats (the value-turn rule)

A **BEAT** is the smallest unit that **turns a value** — it moves the viewer from a
before-state to a different after-state (don't-know → know, assume-X → actually-Y,
problem → implication, option-A → its-tradeoff). That's the concept. The
**operational cut rule is mechanical:**

> **Cut a new beat at every TURN word** — "but," "so," "which means," "the problem
> is," "instead," "here's the catch." **Continue the same beat** through "and,"
> elaboration, and supporting examples.

This replaces "one slide per paragraph" entirely — the boundary falls on the
idea-shift, not the punctuation.

### Beat = slide mapping
- One beat = one idea = one breath-group of VO. **Default one slide per beat.**
- **A slide may persist across 2–3 beats** when the beats are progressive reveals
  of one object (an architecture diagram built part-by-part, a list filling in).
  Reveal the new part on its beat; never cut a fresh slide mid-diagram.
- **One beat never needs two full slides** — if it does, the idea wasn't atomic;
  split the beat.

### Heuristics
- **Collapse parallel lists.** 3+ sibling items with no causal order → ONE beat
  with an explicit count ("three things changed"), never N strobing slides.
  Reserve separate beats only for items that BUT/THEREFORE each other.
- **Pre-train before you reason.** A term the argument *redefines or leans on* gets
  its own naming beat before the beat that uses it. Cap the **redefined** terms at
  ~2 per ramble; a parts inventory (above) is exempt. More than that → narrow scope.
- **Rest beat after every 3–4 dense beats** — a low-density restatement or
  section-turn ("So that's the problem. Here's the fix."). The system-paced viewer
  can't hit pause; build the breath in for them. *(This is the one place the rest
  rule lives.)*
- **Glance test.** If a viewer can't grasp the slide in ~3 seconds (more than one
  short headline plus a few labels, or two competing focal points), the beat is too
  big — split it.
- **Allocate to difficulty, not evenly.** Mechanism gets the most beats; Problem
  and Payoff get 1 each. Never spread the easy parts thin and cram the hard one.

### Granularity
- **~8–12 beats across ~480 words ≈ 40–55 words / beat (~3 short sentences, one
  breath-group each).** Under ~25 words is usually a fragment — merge up. Over ~60
  the slide goes stale — split, or persist the slide with a reveal.
- A **comparison/tradeoff** is ONE beat with both options on one slide — the eye
  must weigh them together, not across a cut.

---

## 3. Density and length

The viewer has two channels — eyes and ears — each with tiny working memory, and
they **cannot pause** to rebuild context. So the segmenting a self-paced reader
does for themselves must be **pre-absorbed by your chunking.**

- **One new thing per beat.** A term-introduction beat does not also advance the
  argument; the argument resumes next beat.
- **Uniform density beats spiky.** Pre-train terms a beat early, cut decorative
  motion and filler, rest after every 3–4 dense beats (§2).
- **Density comes from precision, not volume.** "Slow" → "forty minutes per run."

### Sustain one thesis
Default to **ONE spine idea** the whole way — every beat is evidence for it. Only
branch to parallel pillars when they're genuinely independent; then cap at **3**,
name them by count up front ("three costs"), and return each to the spine. Juggling
unlabeled threads is the silent killer of alignment.

### The throughline
Plant **one concrete anchor** — a phrase, a number, a named instance — in the cold
open. Restate it verbatim at each movement boundary and in the Ask, so 8–12 beats
feel like one argument, not a list. Allow **one mid-video callback**: plant a vivid
noun/number early, pay it off later ("remember the forty minutes? here's where they
go"). One plant, one payoff; two callbacks max. *A ramble with no throughline is a
list, not a narrative — flag it.*

### Length escape hatch
The ~3-min / ~480-word budget is a default, not a wall. A dense RFC may honestly
need 4–5 min. When the argument won't fit, **in this priority order:** (1) cut a
whole pillar, not detail from every beat; (2) demote a beat to a slide-only aside;
(3) split into two rambles at a movement boundary. **Never speak faster and never
thin the tradeoff/objection detail** that alignment actually hinges on — those are
the last things to cut, not the first.

---

## 4. SAY vs SHOW (the load-bearing rule)

Split every beat into **SAY** (voiceover — the durable spine) and **SHOW** (slide),
and never let them narrate the same words. Graphics + narration + the *same
sentence* on screen teaches **worse** than graphics + narration alone: both streams
transit working memory and compete. **Dumping the VO line onto the slide is the
single most common way an engine ruins a video — it halves capacity for zero gain.**

### The split — and the gate
- The **slide carries WHAT / HOW-MUCH** — the nameable, the countable: a noun
  phrase, a number, a label, a before/after.
- The **VO carries WHY / SO-WHAT** — the reasoning, the consequence, the transition.
- **The gate (apply every beat): the slide is a noun phrase, number, label, or
  before/after — never a clause with a verb.** Slide keeps the noun; VO keeps the
  verb.

> VO: "We cut p95 latency from 800 milliseconds to under 200."
> Slide: `p95: 800ms → <200ms` — **not the sentence.**

### The VO must be self-sufficient
A listener who never saw the slide still gets the full idea from the VO alone. The
slide **completes the picture; it never completes the sentence.**

### Permitted redundancy (surface these even while the VO says them)
1. Proper nouns — product / feature / component names.
2. A novel or technical term the **first** time it appears (idempotency key, CRDT,
   p99) — seeing it spelled while hearing it anchors it.
3. Exact numbers, metrics, dates, dollar figures.
4. Short labels on a diagram.
5. **When the slide IS the data** (a chart, screenshot, table): the chart body is a
   permitted exception, but its **title/takeaway** still obeys the gate — a label,
   not the spoken sentence. Never read a table aloud (see numbers, below).

**Never surface:** full clauses, the "why," explanatory sentences, transitions.

### Provenance
Every number on a slide is a claim a colleague will challenge. For at least the
**load-bearing metric**, make the source legible — on the slide or in the VO
("p95 from Datadog," "from last week's incident"). Unsourced numbers kill trust
faster in a review than in a keynote.

### Numbers in speech
- **One hero number per beat.** Never read a table or two figures in one sentence.
- **Pair a raw figure with its meaning:** "forty minutes — a full coffee break —
  every deploy."
- **Direction + magnitude before precision:** "latency dropped by three-quarters —
  from 800 down to 200." Round in speech; the exact figure lives on the slide.
- **End the beat on the SO-WHAT, never the bare figure:** "…two hundred
  milliseconds. Fast enough that nobody notices it anymore."

### Lockstep
The slide's reveal lands on the **first spoken word that names the thing shown** —
and per `design.md`, the cue is the bold+accent word itself, not a glyph. Never
reveal element N+1 while the VO is still on N. For a payoff beat — a number, a name,
a punchline — anchor the reveal to the **payoff word**, not the beat's first word,
or the audience reads ahead and the line dies. ("And the new cold-start time is —
[reveal] — under two hundred milliseconds.")

---

## 5. Write the VO for one take

The script is a performance score for ONE human take. The read-aloud test is the
only real test — if a line trips the tongue or runs out of air, split it.

- **One idea per sentence.** Hard ceiling 20 words, target 8–15. One subordinate
  clause max. If you joined a second idea with "and / which / because," split it —
  and that split is a candidate beat boundary.
- **Always contract:** it's, we're, you'll, don't, that's, here's. Uncontracted
  formal prose is the #1 tell of reading-not-talking and the main cause of one-take
  fumbles.
- **Concrete over abstract, always.** Replace every abstraction with a number,
  named system, or real instance.
- **Second person for the audience's pain** ("you've shipped the doc, nobody reads
  it"); **first-person-plural for shared decisions** ("we'd be trading X for Y").
- **Front-load the subject; signpost the turn.** Framing comes *before* content
  ("The tradeoff is this —", "Two things broke —"). The ear can't look back. Never
  open a beat on a pronoun whose referent was on the previous slide.
- **Vary cadence.** Medium setup / medium development / short button. End each beat
  on a 2–5 word button line that states the point and cues the slide's headline.
  Never three same-length sentences in a row.
- **End on the explicit Ask** (§1), plainly. Never trail off, never a CTA flourish,
  never a long multi-clause recap — close on a short button.

### Cold-open move (pick one; don't default to the same opener every time)
- **The direct call** — "We should move queue processing off the request path."
  (PM commit, confident RFC.)
- **The costed tension** — "Activation is at 18%, and here's why." (PM problem-led.)
- **The concrete instance** — "Last Tuesday a customer waited forty minutes for a
  deploy." (any ICP; strongest lean-in.)
- **The fork** — "We can go event-driven or stay synchronous. I lean event-driven —
  here's the case." (exploratory RFC, designer direction-choice.)

No greeting, no "as you know." A single folded one-line map of the movements is
permitted ("Three things: the cost, the fix, the tradeoff") — it's navigation for a
captive audience, not throat-clearing. A contents *slide* is not.

**Ban:** semicolons, parentheticals, "i.e./e.g.," three-adjective stacks,
exclamation marks; the hype lexicon (revolutionary, game-changing, seamless,
unlock, supercharge, effortlessly); the register words therefore/thus/moreover/
utilize/leverage(v)/in order to — use so/also/use/to. **No slide-referential
language** ("as you can see," "this slide shows") — the VO must stand as audio even
if the slide vanished.

---

## 6. Transitions

### The governing law (every seam)
**BUT / THEREFORE, never AND-THEN.** After drafting the beat order, label every
adjacent seam as **BUT** (reversal/tension/caveat) or **THEREFORE** (consequence),
and write the one-clause spoken hinge that opens the next beat. Any seam that only
takes "and / also / next / another thing" is a **defect** — reorder for causality or
merge the beats.

### The toolkit (six moves; pick the seam's type)
- **Consequence chain (THEREFORE).** End a beat on a cost; open the next on the
  consequence with "so / which means / which is why."
  *"…that adds a full second per request. So we moved it off the request path."*
- **Contrast pivot (BUT).** Swing from what-is to what-could-be with "but /
  instead / here's the change," and give the two slides **sibling layouts** so the
  swing is visible. Exactly **one oscillation per pillar** — more reads as padding.
  *"Today it's fourteen manual steps. But here's what one click does instead."*
- **Question-as-bridge.** End a beat on the implicit question the next answers. Used
  sparingly, typically at a movement boundary.
  *"So why was it slow? — Three round-trips."*
- **Given-new handoff.** End on the key noun the next beat picks up; open the next
  naming that same noun, so the ear hears continuity across the cut. This is also
  how a **pre-training** beat hands its new term to the beat that reasons with it.
  *"…and that's the latency problem. / The latency problem has one cause —"*
- **Throughline restatement.** At a movement boundary, repeat the anchor phrase or
  number verbatim (§3) so the seams stitch into one argument.
- **Callback close.** The Ask beat echoes a concrete noun or number from the
  opening gap, closing the loop so the 3 minutes feel earned.
  *"That doc nobody read? This is what replaces it. So — do we ship it?"*

---

## 7. The output contract

Every finished beat is an object with these fields. If any is missing or fails its
gate, the beat is not done.

- **SAY** — the spoken line(s), 1–3 short sentences, contracted, read-aloud-tested.
- **SHOW** — the slide spec: a noun phrase / number / label / before-after.
  Passes the §4 gate (no verb-clause).
- **SEAM** — the label of the transition *into* this beat: `BUT` or `THEREFORE`
  (the first beat is exempt), plus the spoken hinge.
- **REVEAL-ANCHOR** — the word in SAY on which the slide / next element appears
  (the payoff word for payoff beats). *(Maps to the MCP slide anchor phrase.)*
- **TURN** — the before-state → after-state this beat delivers (one phrase). If you
  can't name it, the beat isn't a beat — merge or cut it.

### Abort / repair rules
- **No identifiable Turn in the whole source** (a pure status update, no decision
  owed): do not force a fake thesis. Flag it and recommend the doc/meeting instead
  (see "What a Ramble is NOT for").
- **No single honest recommendation:** use the **fork** open — present options and
  your lean. Don't fabricate a confident thesis the author doesn't hold; colleagues
  distrust it.
- **No throughline:** the draft is a list, not a narrative — add an anchor (§3)
  before shipping.
- **Won't fit the budget:** apply the §3 escape hatch in order — cut a pillar
  first, never thin the objection/tradeoff detail.

---

## 8. Worked examples

### A — The redundant slide (SAY vs SHOW)
**Weak.** VO: "We cut p95 latency from 800 milliseconds down to under 200
milliseconds." Slide: "We cut p95 latency from 800ms down to under 200ms."
The slide is the transcript — zero gain, half the capacity.
**Strong.** VO: "We cut p95 latency from 800 milliseconds to under 200." Slide:
`p95: 800ms → <200ms`. Slide keeps the numbers (permitted); VO keeps the verb;
reveal anchors to "200."

### B — Mechanical chunking (value-turn)
**Weak** — three slides: "The queue runs on the request path." / "It's written in
Python." / "It uses a single worker." Three slides, zero value-turns — all the same
before/after. A list read aloud.
**Strong** — one beat, one turn: "Right now the queue runs on the request path —
one Python worker, in line with every request. So every job blocks the user." One
slide (`queue ON request path`), one turn: *assume background → actually it blocks
the user.* The "so" earns the next beat.

### C — AND-THEN seam (transitions)
**Weak.** "…so that's the caching layer. And another thing we added is read
replicas." A list; the beats are reorderable; the transition is missing.
**Strong.** "…so the cache absorbs the reads. But writes still hit one box. That's
the ceiling read replicas lift." A THEREFORE→BUT chain — the cache's limit *causes*
the need for replicas.

### D — Reading-not-talking VO (one take)
**Weak.** "It is important to note that the current architecture, which processes
jobs synchronously, therefore introduces significant latency under load." 29 words,
no contraction, nested clause — unsayable in one breath.
**Strong.** "Today, jobs run synchronously. Under load, that's where the latency
comes from. One box, doing everything." Three short sentences, one idea each, ends
on a button that cues the headline.

### E — Agenda open (lead with the point)
**Weak.** "Hi everyone — today I'm going to walk you through our proposed Q3
architecture changes and the tradeoffs involved." Throat-clearing.
**Strong.** "We should move queue processing off the request path. Here's the
case." Beat 1 is the recommendation; every beat after reads as evidence.

### F — End-to-end RFC (one ~10-beat ramble assembled)
Shows how the arc, beats, SAY/SHOW, seams, and objection hang together. Anchor
(throughline): **"forty minutes."**

1. **Point** · SEAM none · SAY: "We should move queue processing off the request
   path." · SHOW: `Move the queue off the request path` · ANCHOR: "off."
2. **Gap** · THEREFORE · SAY: "Right now every deploy waits on the queue — about
   forty minutes, a full coffee break, every single time." · SHOW: `deploy wait:
   ~40 min` *(source: CI dashboard)* · ANCHOR: "forty."
3. **Turn** · BUT · SAY: "But almost none of that work needs to be in line with the
   request. It's just sitting there because that's how it was first built." · SHOW:
   `in-line ≠ required` · ANCHOR: "needs."
4. **Pre-train** · THEREFORE · SAY: "So we add one thing — an idempotency key. It's
   what lets us retry a job safely." · SHOW: `idempotency key` · ANCHOR: "key."
5. **Mechanism** · THEREFORE · SAY: "With that key, the queue moves to a background
   worker. The request returns the moment the job's accepted." · SHOW: diagram,
   reveal worker · ANCHOR: "background."
6. **Mechanism** · THEREFORE · SAY: "Which means the user stops waiting on work
   they never cared about." · SHOW: diagram, reveal returned-request · ANCHOR:
   "stops."
7. **Objection** · BUT · SAY: "The catch is consistency — a backgrounded job can
   land out of order. That's the part I most want pushback on." · SHOW: `tradeoff:
   ordering` · ANCHOR: "consistency."
8. **Payoff** · THEREFORE · SAY: "Remember the forty minutes? They drop to under
   two. Fast enough that nobody plans their day around a deploy." · SHOW: `~40 min →
   <2 min` · ANCHOR: "two."
9. **Ask** · THEREFORE · SAY: "So — I'm asking you to pressure-test the ordering
   tradeoff. Drop your take in the RFC thread by Thursday." · SHOW: `Decide:
   ordering tradeoff · RFC thread · Thu` · ANCHOR: "Thursday."

Nine beats, ~190 words shown; a real one fills the Mechanism to ~480. Note the
throughline ("forty minutes") planted in beat 2, called back in beat 8; the
objection is its own beat, not folded into the Ask; the Ask names the decision, the
when, and the place.
