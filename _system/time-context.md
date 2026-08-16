# Weekly Time Constraints

<!--
This file is loaded every session.
It tells Claude what your week actually looks like — hard blocks, deadlines, and when you can do deep work.

Update at the start of each week, or when the calendar changes significantly.

Automation note: this is the obvious file to generate automatically if you have MCP access
to your calendar. A skill that reads next week's events and writes this file saves the
manual overhead entirely. Until then, fill it in by hand — imperfect is fine, empty is not.

If you don't have direct calendar MCP access (e.g. your Claude Code setup is sanctioned but
individual, not wired into company identity/calendar systems), a relay works too: point
whatever automation tool you do have a calendar connector in (Rovo, Power Automate, Zapier)
at your calendar, have it write your agenda to a page, then have Claude fetch from that page
instead of the calendar directly.
-->

## Weekly Scope

Scope: Week of YYYY-MM-DD to YYYY-MM-DD
Timezone: [Your timezone, e.g. GMT-3]

---

## Hard Constraints

<!--
Fixed calendar blocks that cannot move. Meetings, recurring commitments, etc.
Format: Day - HH:MM-HH:MM - Description
-->

- [Day] - [HH:MM-HH:MM] - [Meeting or block name]
- [Day] - [HH:MM-HH:MM] - [Meeting or block name]

---

## Deadlines

### This Week

- [Day] - [What's due]

### Future

- [YYYY-MM-DD] - [What's due]

---

## Focus Windows

<!--
When are you actually available for deep work this week?
Being explicit here lets Claude avoid suggesting work in slots that don't exist.
-->

- [Day] - [HH:MM-HH:MM]
- [Day] - [HH:MM-HH:MM]

---

## Current Baseline Schedule

<!--
Your typical day structure, independent of this week's specifics.
Fill once and update only when the routine changes.
-->

- [Time block] → [What it's for]
- [Time block] → [What it's for]
- [Time block] → [What it's for]

---

## Slot Allocation Rules

<!--
Optional but useful. Hard rules about what gets what time.
Prevents Claude from suggesting work in protected blocks.
-->

- [Time block] → reserved for [type of work]
- [Time block] → reserved for [type of work]
