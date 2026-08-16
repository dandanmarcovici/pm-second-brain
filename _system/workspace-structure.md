# Workspace Structure

Reference for how the work/ folder is organized and how to maintain it consistently.

---

## Folder Map

```
work/
  ideas/          ← ideas being evaluated or killed before becoming projects
  projects/       ← time-bound delivery work with a finish line (gets archived when done)
  areas/          ← ongoing strategic responsibilities with no end date and no cadence
  processes/      ← recurring, cyclical activities with no end date (monthly/quarterly/annual)
  frameworks/     ← reusable reference models
  knowledge/      ← org reference: people, products, ecosystem
```

---

## Bucket Classification Rules

| Question | Answer | Goes in |
|----------|--------|---------|
| Does it have a finish line? | Yes | projects/ |
| Does it run on a recurring cadence forever? | Yes | processes/ |
| Is it an ongoing strategic responsibility (no end date, no schedule)? | Yes | areas/ |
| Is it a reusable reference model? | Yes | frameworks/ |
| Is it an untested idea not yet committed to? | Yes | ideas/ |
| Does a project deliver a process? | Yes | projects/ first, then graduate to processes/ when defined |

---

## Container Decision Rule

**Before creating a new project or process folder, ask:**
*"Does this need its own tasks.md?"*

- If **no** → create a doc inside an existing project/process
- If **yes** → create the container

Every container brings overhead: context.md + tasks.md + log.md + docs/. Don't create one unless the work genuinely needs independent task tracking. Three related docs inside an existing project beats three separate projects.

---

## File Conventions

### context.md (required in every container)

**Purpose:** Stable background: why this exists, what it is, who's involved, key references.

**What belongs here:**
- Objective and scope
- Key people and roles
- Tool or platform decisions (with rationale)
- Pointers to related processes/projects
- Success criteria

**What does NOT belong here:**
- Timeline of what happened → goes in log.md
- Individual decisions with rationale → goes in log.md
- Current state that changes week to week → goes in log.md

If context.md is growing past ~60 lines, it's absorbing things that belong in the log.

---

### tasks.md (required in every container)

**Purpose:** What needs to happen, in priority order.

**Format (strict):**
```
## NOW
- task (add date if time-constrained this week)

---

## NEXT
- task (add date if deadline is next week or known)

---

## LATER
- task (backlog, no time constraint)
```

**Rules:**
- NOW = active this week or has a deadline this week
- NEXT = coming up next week or next milestone
- LATER = backlog, no time constraint
- No checkboxes, no sub-sections, no status tracking
- Rich context belongs in context.md or log.md, not tasks.md

---

### log.md (required in every container)

**Purpose:** Chronological record of what happened, what was decided, and why. Answers: *"What's the state of this, and how did we get here?"*

**Format:** Newest entry first. Date-stamped. 1-3 sentences per entry. Tag decisions with `[DECISION]` for searchability.

```markdown
## 2026-05-07
Description of what happened and what changed.

## 2026-04-14 [DECISION]
What was decided and the key rationale behind it.
```

**Create at setup, even if empty.** Without a log, context.md absorbs the timeline and becomes unmaintainable. Converting later is painful: the context grows first and the log never gets created. An empty log costs nothing; a missing log costs you later.

---

### docs/ folder

**Purpose:** Supporting documents. Not tasks, not background.

**Rules:**
- Active reference files go directly in docs/
- Historical files go in docs/archive/
- Avoid nesting more than one level deep inside docs/

**Common subfolders:**
- `archive/`: historical docs, superseded versions
- `meeting-agendas/`: meeting agendas
- `meeting-transcripts/`: meeting transcripts, pasted in or pulled via an MCP connector (e.g. Granola, Loom)
- `reports/`: the world-facing version of a working doc

**The `docs/` vs `docs/reports/` distinction:** a working topic starts as a single live file directly in `docs/`: the messy version, open for back-and-forth, open items, notes to yourself. Once it's ready to go outside (a pre-read, a status update, a synced Confluence/SharePoint page), the clean version goes in `docs/reports/`, usually under the same or a closely related filename. The messy file keeps evolving; the report is what gets shared and kept current. Anything found in `reports/` should always be the clean, current, front-facing copy.

---

## Archiving

When a project is complete or no longer active:
1. Add an ARCHIVED banner at the top of context.md and tasks.md
2. Do not delete: it's history
3. Remove from any index or update entry to say ARCHIVED
4. Content that will be referenced going forward moves to the relevant active project/process
