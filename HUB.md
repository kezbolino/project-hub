# 🗂️ Project Hub — kezbolino

**The single map of everything I'm building.** Any Claude — chat, Claude Code
in the browser, or Claude Code on my laptop — should read this FIRST to know
what projects exist, where they live, and what's outstanding. This file is the
source of truth; keep it updated.

**Last updated:** 2026-07-12

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

### 4. _next project_  ⟵ template — copy the block above
- **Repo:**
- **What it is:**
- **Status:**
- **Open threads:**

---

## Cross-project notes

- Anything that spans projects (shared accounts, a decision that affects several
  things, "don't forget X") goes here.
