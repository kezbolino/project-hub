# Seamless project overview — setup (10 minutes, once)

Goal: from **any** surface (claude.ai chat, Claude Code in the browser, Claude
Code on your laptop) you can say "read my project hub" and get a live overview
of every project and what's outstanding.

The trick: **one small public GitHub repo** is the shared brain. Everything
reads from it.

---

## Step 1 — make the hub repo (once)

1. On github.com → **New repository**.
2. Name it **`project-hub`**. Set it **Public** (it's just a list of project
   names + status — no code, no secrets — and public means every surface can
   read it with zero auth).
3. Tick "Add a README", create it.
4. Add a file called **`HUB.md`** and paste in the `HUB.md` from this kit
   (fill in the Instagram scraper + any other projects).

That's the backbone done.

---

## Step 2 — wire each surface

### 🖥️ Claude Code on your laptop (works across ALL your local projects)
Copy the `.claude/commands/hub.md` file from this kit to **`~/.claude/commands/hub.md`**
(the `~/.claude` folder is global — applies to every project on the machine).
Now, in any local project, just type **`/hub`** and Claude loads the overview.

Optional: add one line to **`~/.claude/CLAUDE.md`** (create it if missing):
> If I ask about "my projects", "the hub", or "what's where", read
> https://raw.githubusercontent.com/kezbolino/project-hub/main/HUB.md first.

### 🌐 Claude Code in the browser
When you start a session, **add the `project-hub` repo** to it (the same way you
add any repo), then say **"read the hub"**. Or just say "read
github.com/kezbolino/project-hub/blob/main/HUB.md".

### 💬 claude.ai chat
Two options, either works:
- **Connect GitHub** (Settings → Connectors → GitHub) once — then Claude can
  read the hub repo directly, on any chat.
- Or make a **Project** in claude.ai called "Hub" and drop `HUB.md` into its
  knowledge. Every chat in that Project starts already knowing the map.

---

## Step 3 — the habit that makes it work

- Start of a session anywhere: **"read my project hub."**
- When something changes: **"update the hub"** (on a surface that can push to
  the repo — i.e. Claude Code).
- Each individual project repo can carry a one-liner at the top of its README:
  *"Part of the Project Hub → github.com/kezbolino/project-hub"* so you always
  find your way back.

---

## Honest limits (so you're not surprised)

- This is **not automatic sync** — nothing today makes chat, Claude Code, and
  desktop share one live memory. The hub is a *manually-kept single source of
  truth*, which is the best available substitute.
- The `/hub` command only works in **Claude Code** (local + browser). The chat
  app can't run it — that's why chat uses the GitHub connector / Project route.
- Keep secrets (tokens, keys) **out** of the hub — it's public. It's an index,
  not a vault.
