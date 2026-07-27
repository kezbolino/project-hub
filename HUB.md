# 🗂️ Project Hub — kezbolino

**The single map of everything I'm building.** Any Claude — chat, Claude Code
in the browser, or Claude Code on my laptop — should read this FIRST to know
what projects exist, where they live, and what's outstanding. This file is the
source of truth; keep it updated.

**Last updated:** 2026-07-27

---

## How to use this

- Starting a session on any surface? Say **"read my project hub"** (and point
  Claude at this repo / URL). Ask for a one-screen overview, then pick a project.
- When something meaningful changes on a project, tell Claude **"update the
  hub"** so this stays current.
- One rule: **decisions and status live here, not in a chat window.** Chat
  windows are disposable; this file isn't.

---

## Projects

### 1. Chuckling Wings — "Wingman" (social-media app)
- **Repo:** `github.com/kezbolino/social-media-app` · branch `claude/new-session-wq4q6o`
- **Live:** https://kezbolino.github.io/social-media-app/ (GitHub Pages)
- **Local:** `~/Documents/Work/Street Food Post/` (folder + README call it "Street Food
  Post"; same codebase as this repo. Not git-tracked locally.)
- **What it is:** Offline PWA for a London street-food trader. Photo → Instagram-style
  editor (crop / filters / Stories-style text) → cheeky pre-written caption → share
  or auto-post. Plus a work calendar, post reminders, a 3-post generator, and a
  hashtag bank.
- **Status:** ✅ Working & deployed. Meta auto-posting is **built**, waiting on
  Meta API credentials (see `docs/META_SETUP.md`).
- **Open threads / ideas:**
  - Hashtag *discovery* via Instagram Graph API (`hashtag_search`) — wanted, not built.
  - Posting **queue / scheduling** (plan the week, auto-post on the day) — idea.
  - Carousel (multi-photo) posts — idea.
- **Key docs:** `README.md`, `docs/AUDIT.md`, `docs/META_SETUP.md`, `docs/PROJECT_LOG.md`

### 2. Instagram Caption Grabber (social media scraper)
- **Repo:** lives in `github.com/kezbolino/social-media-app` under
  `tools/ig-caption-scraper` (source of truth). No standalone repo.
- **Local:** `~/Documents/Work/Instagram Caption Grabber/` (moved out of Downloads
  2026-07-07; now standalone, not git-tracked locally).
- **What it is:** Node tool that grabs captions from a list of Instagram handles
  (`handles.txt`) → CSV, to feed into the Street Food Post caption bank. Runs via a
  double-click Mac app (`Instagram Grabber.app` → browser UI) or CLI
  (`IG_SESSIONID="<cookie>" node scrape.js handles.txt`). Needs Node.js + an IG
  `sessionid` cookie.
- **Status:** ✅ Working. Standalone tool, not deployed.
- **Open threads:** Not git-tracked in its new home — consider `git init` or folding
  back into the social-media-app repo so tweaks are versioned.

### 3. Distill (YouTube → best-practices knowledge base)
- **Repo:** `github.com/kezbolino/distill` (private) · branch `main`
- **Local:** `~/Documents/Work/Distill/`
- **What it is:** Local tool that turns hand-picked YouTubers into a private,
  searchable knowledge base of *best practices*. Paste a channel/videos → fetch
  transcripts → a model distils each into actionable notes → chat grounded only in
  your curated content → export a consolidated `best-practices.md` per topic. Key
  idea: the app-dev topic's export gets fed back to Claude as a reference when
  building your own apps (the "distil → apply" loop). Node + TypeScript, runs on
  `localhost:5170`, data is plain files under `data/`, git-backed for cross-machine.
- **Status:** ✅ v1 core working & pushed. Add video → distil → chat → export all
  verified end-to-end. **Model-agnostic**: everything routes through one
  `LLMProvider` interface; a keyless `mock` provider runs the whole app today.
- **Open threads / ideas** (from a Fable strategy pass):
  - Wire a real model provider (Claude / local / OpenAI) — mock is placeholder only.
  - Export topics as Claude **skill packs**, not just markdown (biggest-leverage feature).
  - **Watch mode** — auto-ingest new uploads, merge into the doc with a diff.
  - **Auto-discover similar channels** → review queue → grow the KB (the user's ask).
  - Consensus/contested ledger; more sources (podcasts/blogs/PDFs).
  - Monetisation: sell distilled "knowledge packs" (£19 on Gumroad), not SaaS.
- **Key docs:** `README.md`

### 4. BJJ Brain (jiu-jitsu knowledge system)
- **Repo:** `github.com/kezbolino/JJ-app` (private) · branch `main`
  ⚠️ Repo is named `JJ-app`, product is **BJJ Brain** — rename to `bjj-brain`
  recommended while it's still free to do (no code, no deploys, no links).
- **What it is:** A personal knowledge system for grapplers — "Obsidian for
  knowledge, Spotify Wrapped for progress, a coach that never forgets." Journal
  every class → auto-tag → everything connects into a knowledge graph. Layers on
  top: technique wiki pages, YouTube library, voice capture, coach principles,
  radar charts (confidence vs evidence), AI insights, knowledge-gap detection,
  monthly review and an annual "wrapped".
- **Status:** 🌱 Vision captured and **MVP scoped**. Nothing built, no stack chosen.
- **MVP (`docs/MVP.md`):** dashboard (classes attended · this week's focus ·
  what we're learning in class) + class journal + tagging + technique pages +
  YouTube links + search. Annual wrapped demoted to nice-to-have.
- **Key insight:** the "Evidence" radar was reframed from *competence* to
  **coverage asymmetry** — "you've written a lot about half guard sweeps, how's
  your half guard passing?" Reports imbalance rather than inferring skill, and
  collapses pentagon + knowledge gaps + recommendations into one engine.
  Needs **position × role** in the data model from day one.
- **Open threads / decisions:**
  - Where does "what we're learning in class" data come from? (Does the gym
    publish a syllabus/theme anywhere?) Decides if that panel is great or
    marginal.
  - Standalone app vs Obsidian vault + plugins — unanswered.
  - Personal tool vs product — one user today, doc written in product language.
  - Private repo vs mobile-first: no deployment path (Pages needs public).
  - Auto-tagging accuracy gates the graph; manual tagging fine for v1.
  - Capture friction is the whole product — voice capture deferred but is the
    highest-value addition after v1.
  - Reuse Distill's `LLMProvider` interface rather than reinventing it.
- **Key docs:** `docs/MVP.md` (start here), `docs/VISION.md`,
  `docs/OPEN-QUESTIONS.md`, `CLAUDE.md`

### 5. _next project_  ⟵ template — copy the block above
- **Repo:**
- **What it is:**
- **Status:**
- **Open threads:**

---

## Cross-project notes

- Anything that spans projects (shared accounts, a decision that affects several
  things, "don't forget X") goes here.
