# Notion snapshot

Point-in-time copy of Project Odyssey's core documentation, taken by a Builder session. **Notion is the source of truth; this may be older.**

- `pages/` — the home page, the Operating Manual, the six pillar pages, the Crew Noticeboard protocol and the AI Project Instructions, in Notion-flavoured Markdown as read through the Notion connector. The header of each page shows when it was read.
- `pages/skills/` — Skills Mapping pages touched by a Builder session (specs only, never email or personal content).
- `schema/` — the structure of the core databases (properties, options, groups, page layout). Option IDs are removed so diffs show real changes only. Rows are not included.

## Not included (G22)
Diário Pessoal, health and finance content, and Persona main pages (some hold personal detail). Odara decides if and when they join.

## Drift check
Compare `schema/` with the previous commit. A structural change without a matching `CHANGELOG.md` entry was made outside a Builder environment and must be reviewed.
