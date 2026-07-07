# 🗂️ Project Hub — kezbolino

**The single map of everything I'm building.** Any Claude — chat, Claude Code
in the browser, or Claude Code on my laptop — should read this FIRST to know
what projects exist, where they live, and what's outstanding. This file is the
source of truth; keep it updated.

**Last updated:** 2026-07-07

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

### 3. _next project_  ⟵ template — copy the block above
- **Repo:**
- **What it is:**
- **Status:**
- **Open threads:**

---

## Cross-project notes

- Anything that spans projects (shared accounts, a decision that affects several
  things, "don't forget X") goes here.
