# Grounded design: what the Mobbin MCP video actually teaches

**Type:** research note
**Date:** 2026-07-28
**Source:** Mobbin MCP product video — auto-generated transcript supplied by kezbolino.
No canonical URL captured. *(See "Provenance" at the bottom — the missing URL is
itself an example of the problem this note argues about.)*
**Applies to:** Distill (primary), Wingman, Instagram Caption Grabber

---

## TL;DR

An agent with no domain corpus regresses to the mean of its training data —
plausible-looking, contextless output. Given a curated, citable corpus of real
shipped work, it inherits domain constraints it could not have invented.

The video sells Mobbin MCP, but the **method is provider-agnostic and free**:
split research and build into separate sessions with a durable, cited artifact
between them.

Highest-leverage takeaway for us: **Distill is the same architecture as Mobbin
MCP.** The video doubles as a spec for what Distill is missing.

---

## Transcript caveats

The transcript is auto-captioned and garbles several proper nouns:

| As transcribed | Actually |
|---|---|
| "Mavin MCP" (×5, back half) | Mobbin MCP |
| "paper MCP" | Paper — a design tool with an MCP server |
| "an app like One" | One — fintech app, cited as a design reference |
| "Curve" | Curve — fintech card app, the build target in the demo |

None of it changes the substance.

---

## What the video shows

### The hook

Claude drafts two onboarding flows for a fintech app. One is generic. The other
accounts for identity checks and compliance requirements. Same model, same
prompt — the second had Mobbin MCP connected: ~600,000 screens, flows, and
animations from shipped apps and websites.

The claim: the difference is **grounding**, not capability.

### The workflow

**1. Research session** — browser Claude + Mobbin MCP.

> Research how top apps design their onboarding and account opening flows across
> fintech or banking apps. Find the most relevant screens and user flows, compare
> patterns across products, and identify what the best apps do differently.
> Create a visual report showing the top examples, common patterns, and the best
> practices that top companies converge on.

**2. The artifact** — a report of common patterns, trade-offs, and blind spots.
Every reference is clickable back to Mobbin, where you can study similar screens
or the end-to-end flow.

**3. Build session** — a *fresh* Claude desktop session + Paper MCP, working
against a design-system file. Two attachments: **the research report** and **a
short doc describing what to build**.

> Using Paper MCP in this file, propose an onboarding flow for Curve and build it.
> Flag anywhere that you're intentionally deviating from a pattern you found.

### The moment that matters

The PRD asked: *where does the safe-offers nudge belong without feeling
manipulative?* Claude pushed back on the brief and placed it on the homepage
immediately after onboarding — citing the app One, where the setup bonus sits on
the homepage.

That is the whole pitch in one beat: not compliance, but an **argued** design
decision **with a source**.

### Stated anti-pattern

> "We don't recommend one-shotting a design right away. Research first, then use
> Mobbin MCP to solve specific design problems."

Reinforced with a Figma comparison — a cold agent asked to design map and filter
views produced broken UI; the same agent with research first produced coherent
output with cited sources.

### Other demonstrated uses

- Head-to-head competitor comparison (DoorDash vs Uber Eats: checkout, tipping,
  order summary)
- Fast lookups — "10 empty states from productivity apps"
- Copy suggestions citing their inspiration
- Cross-industry remixing
- Edge-case coverage

### Their own stated limit

> "What Mobbin MCP can't do is help us decide what to prioritize, what to keep,
> and what to cut. That part's still our call."

Worth quoting back at ourselves. Grounding removes the *generic* failure mode.
It does not remove judgement.

---

## The transferable method

Three sessions, one durable artifact between each:

1. **Research** — read-only, no code. Output: `docs/research/<feature>.md` with
   citations. Committed.
2. **Brief** — a short PRD stating what to build **and the open questions**. The
   open question is what triggered the useful pushback in the demo.
3. **Build** — fresh session. Attach 1 and 2. Require deviation flags.

Two structural moves do the work:

- **Separating research from build across sessions** makes the research reusable,
  reviewable, and portable instead of trapped in a chat window.
- **"Flag intentional deviations"** turns the agent from an oracle into something
  auditable.

This is the HUB philosophy applied to design work: *decisions live in files, not
chat windows.*

---

## Application: Distill

**Distill and Mobbin MCP are the same architecture.** Curated corpus → structured
extraction → fed back into the build loop. HUB.md already calls this the
"distil → apply" loop. So the video is both external validation and a gap list.

In leverage order:

### 1. Source citations with timestamps — highest value

Mobbin cites every claim and each citation is clickable back to the source screen.
Our exports are flat `best-practices.md`. If a claim is wrong, or worth going
deeper on, there is no path back.

Every distilled claim should carry provenance: channel, video title, timestamp —
emitted as a deep link (`youtube.com/watch?v=<id>&t=<seconds>s`). Without this an
export is unverifiable, which is precisely the failure mode the video sells
against.

Small change. Unlocks everything below.

### 2. Skill packs over markdown

Already flagged in HUB.md as the biggest-leverage feature. The video explains
*why*: the win isn't the document, it's that the agent can **query the corpus at
build time**.

A `best-practices.md` is a snapshot you paste in. An MCP server over `data/` is a
library card:

- `search_practices(topic, query)`
- `get_source(video_id, timestamp)`
- `compare_sources(claim)`

That is the difference between what we have and what the video demos.

### 3. Comparison as a first-class query

The strongest outputs in the video are all comparative — "compare patterns across
products", "what do the best apps do *differently*", "DoorDash vs Uber Eats".

HUB.md lists "consensus/contested ledger" as an idea. Promote it. *"Four of six
sources agree on X; source B explicitly disagrees, here's the reasoning"* beats a
flattened merge. Flattening disagreement **is** the blind spot the video claims
to surface.

### 4. Export a briefing pack, not just a doc

The build step attaches two artifacts. Distill should emit both: the practices doc
**plus** a PRD stub with a pre-filled *open questions* section.

### 5. Deviation-flagging baked into every export

Two lines at the end of each export:

> When building from this, cite which practice you're applying, and flag any
> intentional deviation with a reason.

Trivial to add; it's the mechanism behind the pushback moment.

### Reframe

Mobbin is design screens. Distill is *whatever corpus you curate*. Distill's real
product isn't "YouTube summariser" — it's **turn any curated source set into
agent-queryable reference**.

This materially strengthens the £19 Gumroad knowledge-pack idea: an MCP-ready
skill pack is a differentiated product, a PDF isn't. The video is evidence the
demand exists.

---

## Application: Wingman (Chuckling Wings)

### Mobbin MCP would earn its keep here now

The open threads — posting queue/scheduling, carousel posts, hashtag discovery —
are all heavily-solved UI problems with hundreds of shipped references. Before
building the queue, run the research step:

> Compare how Later, Buffer, Hootsuite, and Planoly handle post scheduling —
> calendar vs queue vs list, the compose → schedule → confirm flow, empty and
> error states.

### The grounding lesson maps to a real gap

The video's point is that fintech onboarding carries compliance constraints a
generic flow misses. Wingman's equivalent is the **Meta Graph API**:

- two-step container → publish model
- ~25 posts / 24h rate limit
- no native scheduling — schedule locally, publish on the day
- business/creator account requirement
- token expiry and refresh

These should shape the queue UI **before** it's designed, exactly as KYC shapes
account opening. We're waiting on credentials anyway (`docs/META_SETUP.md`) —
good moment to pressure-test the design against real limits rather than
discovering them at integration.

> Verify these limits against current Meta docs before designing — they change,
> and the figures above are from memory, not a fetched source.

### Edge and empty states

The video hits this twice. Wingman is an **offline** PWA, so offline *is* the
edge case:

- Calendar with zero posts — what does it say?
- A scheduled publish window passes while the device is offline — then what?
- A failed auto-post — what does the trader see, and how do they retry mid-service?

Reference corpora are unusually good at exactly this class of problem.

---

## Application: Instagram Caption Grabber

### It's already a corpus builder

Handles → CSV → caption bank is structurally the same as Mobbin's screen library,
just for copy. The video's lesson: value comes from **structure, provenance, and
queryability**, not volume.

Add per-caption metadata — handle, date, post type, engagement where available —
and the bank becomes queryable (*"show me 10 openers from London street-food
traders"*) rather than a list to shuffle from.

### It's Distill's pattern in a second domain

Grabber : captions :: Distill : transcripts. Both are *curate → extract →
structure → serve to an agent*.

HUB.md already flags that the Grabber isn't git-tracked and might fold back in.
This is a stronger argument: the endgame is probably the Grabber as a **Distill
source adapter**, not a separate tool.

---

## Skepticism

- **It's an ad.** The Figma comparison (broken UI cold vs clean UI grounded) is a
  vendor-chosen, uncontrolled demo. An unknown share of the delta comes from the
  two-stage process and better prompting, not the corpus.
- **The method needs no vendor.** It works with any grounding source — our own
  Distill exports, teardowns we write ourselves, a folder of screenshots. Mobbin
  makes it convenient, not possible.
- **Cost.** Mobbin MCP requires a paid Mobbin plan. For one deployed PWA with a
  short feature backlog that's a marginal call. Trial it around the scheduling-queue
  build specifically and judge on evidence.
- **Their caveat is the real one.** Grounding removes "generic". It doesn't decide
  what to prioritise, keep, or cut.

---

## Next actions

1. **Distill** — add source citations with timestamps to exports. Small, unlocks
   the rest.
2. **Wingman** — adopt the research → PRD → build split on the posting queue.
   Free; tests the method on real work.
3. **Distill** — export as skill pack / MCP server rather than markdown.
4. **Mobbin** — trial during the queue build, then decide.

---

## Provenance

This note is derived from a transcript pasted into a chat session. There is no
captured URL, no timestamps, and no way to verify a quote without re-finding the
video.

That is exactly the failure this note argues against, left visible on purpose. If
this gets moved into Distill's `data/`, it should be re-ingested properly with a
source URL and per-claim timestamps — and it makes a decent first test case for
the citation format proposed in §1.
