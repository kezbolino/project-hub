# CLAUDE.md — project-hub

Project memory for this repo. Read `HUB.md` first; this file covers how to work
*on* the hub itself.

## What this repo is

An **index, not a codebase.** No build, no tests, no dependencies — just
markdown. Its job is to be the one place any Claude session (chat, Claude Code
web, Claude Code local) reads to learn what kezbolino is building and what's
outstanding.

| File | Role |
|---|---|
| `HUB.md` | Source of truth. Project list, status, open threads. |
| `SETUP.md` | How the hub is wired into each surface. Rarely changes. |
| `docs/research/` | Durable research notes, indexed from HUB.md. |
| `README.md` | Stub. |

## Rules

- **This repo is public.** No tokens, keys, cookies, or credentials — ever.
  It's an index, not a vault. Local filesystem paths are already in `HUB.md` and
  are considered fine; secrets are not.
- **`HUB.md` is the source of truth**, and everything else must be reachable from
  it. A file nobody links to is invisible — when adding to `docs/`, add a pointer
  under *Cross-project notes* in the same commit.
- **Bump "Last updated"** in `HUB.md` on any substantive change.
- Projects follow the numbered block format in `HUB.md`; block 4 is the template.
  Copy it rather than inventing a shape.
- Code lives in the project repos, not here.

## Projects indexed (as of 2026-07-28)

1. **Chuckling Wings / "Wingman"** — `kezbolino/social-media-app`. Offline PWA for
   a London street-food trader. Deployed to GitHub Pages. Meta auto-posting built,
   blocked on API credentials. Note: the local folder is called "Street Food Post"
   — same codebase, different name. Don't treat them as two projects.
2. **Instagram Caption Grabber** — lives *inside* the social-media-app repo at
   `tools/ig-caption-scraper`; no standalone repo, and the local copy isn't
   git-tracked. Node scraper, handles → captions → CSV.
3. **Distill** — `kezbolino/distill` (private). YouTube → private best-practices
   knowledge base. Node + TypeScript, `localhost:5170`, plain files under `data/`.
   Model-agnostic via one `LLMProvider` interface; a keyless `mock` provider runs
   the whole app, so nothing today needs an API key.

## Gotchas

- **Wingman has two names.** "Chuckling Wings", "Wingman", and "Street Food Post"
  all refer to the same thing.
- **The Grabber has no repo of its own.** Edits belong in `social-media-app`;
  the standalone local folder drifts silently because it isn't versioned.
- **Distill's `mock` provider is a placeholder**, not a working model. "v1 works
  end-to-end" means the plumbing works, not that real distillation is wired up.
- **Session scope is per-repo.** Claude Code web sessions started on `project-hub`
  can't read `distill` or `social-media-app` unless those repos are added to the
  session. Work targeted at them may have to land here and be moved by hand.

## Session log

### 2026-07-28
- Analysed a Mobbin MCP video transcript (supplied in chat) and wrote
  `docs/research/mobbin-grounded-design.md`.
- **Decision:** research notes get their own `docs/research/` directory here,
  indexed from `HUB.md`, rather than being pasted into `HUB.md` itself — the hub
  stays a one-screen map.
- The note was written here only because `distill` wasn't in session scope. Its
  natural home is Distill's `data/`; move it when a session has both repos.
- Open follow-up from the note, in leverage order: Distill export citations with
  video timestamps → skill-pack/MCP export → consensus ledger.
