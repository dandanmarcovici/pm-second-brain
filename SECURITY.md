# Security

This repository ships folder structure, file conventions, and Markdown instruction files. There is no code, no dependencies, and no build step, so the usual vulnerability surface (injection, unpatched packages, unsafe deserialization) doesn't apply here.

The real risk with a system like this is contextual, not technical.

**Personalizing a public fork.** The files in `_system/` and `work/knowledge/` are designed to hold your priorities, schedule, colleagues, and organizational knowledge once you fill them in. A fork of a public repo is public by default. Filling in real details on a public fork exposes them. Use a private repository, or a local copy with a private remote, for your actual second brain. See "Keep your context private" in the README.

**Untrusted content read as instructions.** If you connect this system to something that pulls in outside content automatically (a calendar, Jira, email, a scraped page), that content should always be treated as data to read, not as instructions to follow. `_system/security-guardrails.md` states this explicitly for the AI assistant. If you add a connector, keep that file loaded.

## Reporting an issue

If you find a way this template's structure could lead to real data exposure, or a gap in the guardrails above, open a GitHub issue. If it's sensitive enough that you'd rather not post it publicly, reach out to me directly through my [GitHub profile](https://github.com/dandanmarcovici).
