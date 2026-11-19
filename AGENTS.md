# Builder instructions — Project Odyssey

You are working in a **Builder environment** (Claude Code or Codex) for Project Odyssey, Odara's personal Life Operating System. This is the only kind of place where Odyssey's **structure** changes. Chats (Claude chat, ChatGPT) never change structure.

## Source of truth
- **Notion is the source of truth.** Read it through the Notion connector before acting. This repository holds a backup snapshot, the legacy archive and the change log; it never overrides Notion.
- Start with the Odyssey Operating Manual: https://app.notion.com/p/3aa107b19b4981079aaecf1f72b1bb98 — especially G20 (live documentation, "Before adding anything new" checklist), G21 (permissions and where work happens) and G22 (safety, sensitive data).
- Your Crew role is Hacker, The Good (Builder): https://app.notion.com/p/3fe107b19b4980aaabbee3096706ac52
- Open work: Grab & Go (tasks with Type Structure are yours): https://app.notion.com/p/1ee7ad29377949e2af70cb3ca6c3faa6

## What counts as structure
Database schema (properties, options, relations, formulas), views, layouts and templates; creating, moving, deleting or archiving pages and databases; pillar pages and the Manual; the Crew, Skills and Source of Truth Mapping registries; automation and scheduled-task prompts; bulk changes (more than 5 records or more than one page). Content of a Persona's own page and Sources of Truth belongs to that Persona, in chat.

## How a structural session runs
1. **Reconcile first.** Find the existing home, read what links to it, decide the smallest change (G20 checklist). Agree the change with Odara before touching rules, scope or authority.
2. **Change Notion**, then read back what you changed.
3. **Close the session in this repository:**
   - refresh `notion-snapshot/` (pages and `schema/`) for what you touched;
   - add a `CHANGELOG.md` entry: date, what changed, why, links to the Notion homes;
   - commit with a clear message.
4. **Record the decision** in Notion: one line in the Session Log if a decision was made; update the Grab & Go task's "What was done".

## Always
- Talk to Odara in Portuguese (pt-BR); write documentation and commits in English.
- Never delete in Notion without Odara's explicit confirmation; export to `archive/` first. Legacy is never linked from live pages.
- Sensitive data (diary, health, finance) does not enter this repository without Odara's specific approval (G22).
- External actions (sending, booking, spending) need her explicit go-ahead (G23).
- If Notion and this repository disagree, Notion wins; say so.
