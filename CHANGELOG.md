# Changelog — structural sessions

Every structural change to Project Odyssey is logged here by the Builder session that made it (Operating Manual G21). Newest first. Decisions are also recorded in Notion's Session Log.

## 2026-11-20 · Hacker (Claude Code)
Skills phase, step 1 (agreed with Odara in session). Goal: turn Skills Mapping into the base for daily automations and integrations.
- **Diagnosis:** 29 rows (11 Active, 9 On Draft, 3 Paused, 6 Archived). Nothing runs on its own (all 3 time-based items paused); Bom Dia, the hub for 8 skills, paused since 12/11; "Active" rarely means tested; only 2 rows link to the Crew; no row recorded which connectors it needs (Google Calendar connected but unused).
- **Odara's decisions:** organise capabilities as Rhythms (scheduled) / Commands (spoken triggers) / Bridges (integrations); build order Deadlines → People → Messages → Food; alerts arrive by phone push + Google Calendar; Bom Dia returns first as a light version; automation autonomy stays undecided for now (proposal: start "read and notify only").
- **Skills Mapping schema:** new properties `Integrations` (multi-select: Notion, Gmail, Google Calendar, Push, Chrome, Web) and `Last real run` (date). Filled for all 29 rows; dates only where evidence exists (Gmail Sweep 2026-07-28, Bom Dia 2026-10-17 from its Registro de Runs). Empty date = never proven.
- **New row** `Teste de push (Odyssey)` (Scheduled Task, Active): one-shot push test on 2026-11-21 09:00 Europe/Madrid, no connectors, reads and writes nothing. Archive after the test.
- **Finding:** in this organisation, scheduled tasks created from Claude Code cannot store connectors, so the real morning alert (which reads Notion) must be created another way (claude.ai routines screen or an alternative).
- Notion: [Skills Mapping](https://app.notion.com/p/3fe107b19b4980d788f3dfea3689fbb5) · [Teste de push row](https://app.notion.com/p/41e107b19b498161a13ce632f813e18b)

## 2026-11-19 · Hacker (Claude Code)
- **Builder = environment, not chat (decided by Odara).** Personas keep autonomy over their own main page and Source of Truth content in chat; structure changes only in Claude Code or Codex, after reconciliation, and is versioned here. Written into: Operating Manual (glossary: Builder, Structure; G21 "Where work happens" and permission table), 02 O Navio (AI START HERE step 3, Builders), 04 AI Crew & Skills (Builders card, Shared SoT Operating Contract), Hacker's page.
- **Crew Mapping:** new property `Environment` (Chat / Claude Code / Codex); Hacker = Claude Code, everyone else = Chat.
- **AI Project Instructions v1.2:** chats are told they never change structure; Claude chat's default role is a general collaborator.
- **02 O Navio GitHub card** now describes the live backup workflow (updated after the snapshot was taken; the next snapshot will include it).
- **Repository restructured:** old Sep 2026 mirror moved to `archive/notion-mirror-2026-09-01/`; legacy package from the November audit added to `archive/`; first `notion-snapshot/`; Builder instructions in `AGENTS.md` / `CLAUDE.md`.

## 2026-11-17 · Hacker (Claude Code)
Documentation audit (pillars 01–04), recorded in `archive/audit/2026-11-17-documentation-audit.md`:
- Legacy pages exported and removed from Notion; Mayor role absorbed by Hacker.
- **Grab & Go redesigned:** English statuses, Needs Odara, Impact, Why it matters, Mode, Type, briefings, views per audience.
- **Crew Noticeboard redesigned:** From / To / Read by relations to Crew Mapping, 📬 inbox per member, Odara field, English fields, 7 dead fields dropped, condensed protocol.
- **AI Project Instructions** page created (v1.0–v1.1) in 04 AI Crew & Skills; Operating Manual G20 gained the "Before adding anything new" checklist.

## 2026-09-01
First manual mirror of Codex, Playbook, GM Charter and Governance (now in `archive/notion-mirror-2026-09-01/`).
