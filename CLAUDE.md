# CLAUDE.md — project-hub

## What this repo is

An **index, not a codebase.** It is the single map of everything kezbolino is
building. There is no application code here, no build step, no dependencies,
no tests.

Files:
- `HUB.md` — the source of truth. Every project, where it lives, its status,
  and its open threads.
- `SETUP.md` — how to wire the hub into each Claude surface (laptop Claude
  Code, browser Claude Code, claude.ai chat).
- `README.md` — stub.
- `CLAUDE.md` — this file.

## Rules

- **This repo is public.** No tokens, keys, or credentials — ever. It's an
  index, not a vault (`SETUP.md`).
- **Do not build apps in here.** Each project gets its own repo; this repo
  only records that it exists. `HUB.md` has a `### 4. _next project_`
  template block to copy when registering a new one.
- Decisions and status live in `HUB.md`, not in chat windows.
- When a project changes meaningfully, update `HUB.md` — including the
  **Last updated** date near the top.

## Working on this repo

Nothing to run or install. Edits are plain markdown; commit and push.

## Gotchas

- The `/hub` slash command described in `SETUP.md` only works in Claude Code
  (local + browser). claude.ai chat uses the GitHub connector or a claude.ai
  Project instead.
- The hub is **manually kept** — there is no automatic sync between surfaces.
  Staleness is the main failure mode, so update it as part of finishing work
  on any project.
- Two projects in `HUB.md` have naming/location mismatches worth remembering:
  Wingman's local folder is called "Street Food Post" (same codebase as
  `social-media-app`), and the Instagram Caption Grabber lives inside the
  `social-media-app` repo under `tools/ig-caption-scraper` rather than in a
  repo of its own.

## Session log

- 2026-07-27 — Added this file. No changes to `HUB.md`; confirmed the repo is
  the registry for new apps, not the place to build them.
