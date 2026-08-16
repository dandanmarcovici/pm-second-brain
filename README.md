# pm-second-brain

A second-brain system built for PMs who use Claude Code as a daily working environment.

The problem it solves: Claude resets every conversation. If you work with it all day, you're either re-explaining context at the start of each session, or you design something so you don't have to. This is that something.

This is not a note-taking system or a PKM framework. It's a context architecture: folder structure, file conventions, and a `CLAUDE.md` file that feed the right information to the model at the right moment.

---

## How it works

Claude reads `CLAUDE.md` at the start of every session. That's where your behavioral rules live, your file conventions, your pointers to what's currently active.

The system has three layers:

**Your work, organized.** A folder map that distinguishes projects (a finish line) from areas (ongoing, no cadence) from processes (recurring) from ideas (not yet committed to). Clear enough for both you and the model to navigate without explanation.

**Your context, structured.** Every container gets a `context.md` (stable background), a `tasks.md` (NOW / NEXT / LATER), and a `log.md` (decisions and what changed). All three are created at setup, even if empty. Without the log, context.md absorbs the timeline and becomes unmaintainable.

**Your system, contextual.** A `_system/` folder holds files that shape how Claude reasons with you: your current focus, your weekly constraints, your cognitive guardrails. `CLAUDE.md` tells the model when each one is relevant, so they don't all load every session.

---

## Folder map

```
work/
  ideas/          ← untested ideas, not yet committed to
  projects/       ← time-bound work with a finish line
  areas/          ← ongoing responsibilities, no end date
  processes/      ← recurring activities (monthly, quarterly, annual)
  frameworks/     ← reusable reference models
  knowledge/      ← org, ecosystem, product reference
```

Classification rules and decision heuristics in `_system/workspace-structure.md`.

---

## The three core files

Every container (a project, an area, a process) gets the same three files. This is what actually gets used day to day; everything else supports it.

**`context.md`: the why.** Stable background: what this is, why it exists, who's involved, and a `Related` section pointing to the other files or containers that matter. That pointer list is doing more work than it looks like: once it's there, you don't have to tell Claude "read this file, and that one" at the start of every conversation. You name the container, and Claude uses judgment on which of the linked files to pull in. The alternative is re-stating your own file map out loud every session, which is exactly the problem this system exists to avoid.

**`tasks.md`: the daily driver.** Three buckets, nothing else:

```
## NOW
- what's active this week

## NEXT
- what's coming next week or next milestone

## LATER
- backlog, no time constraint
```

No checkboxes, status fields, or sub-sections. Rich context goes in `context.md` or `log.md`, not here.

**`log.md`: traceability over time.** Newest entry first, 1-3 sentences, decisions tagged `[DECISION]`. This is what actually answers "what's the state of this, and how did we get here" months later: context.md tells you what's true now, log.md tells you why it became true. Skipping it is the single most common way these systems degrade: without it, context.md quietly turns into a timeline and stops being a clean reference.

---

## The `docs/` folder

Anything supporting a container that isn't tasks/context/log goes here, but it isn't a flat pile. A working topic (a discussion, a proposal, a pricing model you're still shaping) starts as one live file directly in `docs/`. It's the messy version: back-and-forth, open items, notes to yourself, allowed to be unfinished.

Four subfolders handle everything else:

| Folder | What goes there |
|---|---|
| `docs/reports/` | The clean, world-facing version of a working file: a pre-read, a status update, whatever's synced out to Confluence, SharePoint, or shared as a doc/deck. Same or a closely related filename as its messy counterpart in `docs/`. Anything in here should always be current and safe to hand to someone outside the conversation. |
| `docs/meeting-agendas/` | Agendas prepped ahead of a session. |
| `docs/meeting-transcripts/` | Transcripts, pasted in manually, or pulled automatically if you have an MCP connector for your meeting tool (Granola, Loom, etc.). |
| `docs/archive/` | Anything obsolete or closed. Don't delete history: move it here. |

The reason this split exists: `docs/` is where thinking happens, `docs/reports/` is what leaves the building. Keeping the messy version alive and separate from the clean one means you're never scared to keep editing the working file, and never worried the report someone else is reading is stale or half-finished.

Format conventions for `docs/reports/`: `_system/pre-read-format.md`-style output templates aren't shipped in this repo. See [Extending the system](#extending-the-system) below.

---

## What's in `_system/`

| File | What it does |
|---|---|
| `workspace-structure.md` | Classification rules, file conventions, archiving |
| `focus-context.md` | Current primary focus and active projects |
| `time-context.md` | Weekly constraints, deadlines, available windows |
| `guardrails.md` | Behavioral rules for how Claude reasons with you |

These four are self-context: they describe *your* situation, and nobody else can write them for you. That's a deliberate scope limit: this repo ships the mechanism, not a library of frameworks.

---

## Extending the system

Output templates (a pre-read format, a meeting notes format, a PM playbook) are a different kind of file: they describe how Claude should produce something *for other people*, and they're reusable across users. Those live in a companion repo, [`claude-skills-for-pms`](https://github.com/dandanmarcovici/claude-skills-for-pms) (in progress).

To use them: clone that repo alongside this one, drop its files into your own `_system/` (or a `frameworks/` folder), and add one line to `CLAUDE.md`'s "Load when relevant" list per file. This is the same pattern already used for `guardrails.md` and `workspace-structure.md`. Nothing about this repo's mechanism changes; you're just adding more content it can route to.

---

## Automating `time-context.md`

`time-context.md` is currently maintained manually. If you have MCP access to your calendar, that's the first thing worth wiring up: a skill that reads next week's events and writes the file removes the manual overhead entirely.

If you don't have direct calendar MCP access (for example, Claude Code is sanctioned at your company but wired to your individual account, not integrated with company calendar/identity systems), a relay still works: point whatever automation tool *does* have a calendar connector (Rovo, Power Automate, Zapier) at your calendar, have it write your agenda out to a page, and have Claude fetch from that page instead of the calendar directly.

---

## Getting started

1. Clone the repo
2. Fill in `_system/focus-context.md` with your current priorities
3. Fill in `_system/time-context.md` with your real weekly constraints
4. Edit `CLAUDE.md` to reflect your name, role, and how you want Claude to work with you
5. Create your first container using the templates in `work/_templates/`

---

## Using with other AI assistants

Built for Claude Code. Works with any AI assistant that reads project files. Clone the repo and ask the model to read `CLAUDE.md` and `_system/workspace-structure.md`, then tell it which conventions apply to its environment.

---

## Background

Built by [Daniel Marcovici](https://www.linkedin.com/in/daniel-marcovici). Fourteen years in industrial robotic software, now PM at Hypertherm. Building with AI tools on the side.

This repo evolved from a year of actual use, not upfront design. The folder structure changed. The conventions got groomed over time. The templates here reflect what stayed.

---

## License

MIT. See [LICENSE](LICENSE). Use it, fork it, change it.
