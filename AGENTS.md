# AGENTS.md

<!--
Codex reads this file automatically before it starts work.
Keep shared behavior and workspace conventions in CLAUDE.md so the two
assistants do not develop separate, conflicting instruction sets.
-->

## Shared Instructions

Before doing any work in this repository:

1. Read `CLAUDE.md` and treat it as the shared source of truth for identity, behavior, workspace conventions, and context-loading rules.
2. Load the files listed under `CLAUDE.md`'s "Always load" section.
3. Load files from its "Load when relevant" sections when the current task matches their purpose.
4. Resolve all referenced paths relative to the repository root.

References to Claude in the shared instructions apply to Codex unless they describe a Claude-specific feature, command, or discovery mechanism.

The user's explicit instructions always override repository defaults.
