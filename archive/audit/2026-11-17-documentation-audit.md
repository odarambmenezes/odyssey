# Odyssey — Documentation Audit (Hacker, The Good)

**Period:** 17 Nov 2026 · **Auditor:** Hacker, The Good (Claude Code) · **Approver:** Odara
**Scope:** Notion documentation, pillars 01–04, Manual, registries (Crew Mapping, Skills Mapping, Source of Truth Mapping, Grab & Go) and real scheduled tasks. Pillars 05 A Jornada and 06 O Hoje are excluded (in progress with Chatty).
**Status:** Open. Closes only when all six pillars are reconciled (Odara, 17 Nov).

> This file lives outside Notion on purpose: it is a historical record, not live documentation. Notion holds only what is current.

---

## 1. Decisions taken by Odara (17 Nov)

| # | Decision |
|---|---|
| D1 | The Mayor role was absorbed by Hacker, The Good: lead of infrastructure and structural construction. Every live mention of Mayor now points to Hacker. |
| D2 | Chatty, The Designer is the Art Director (experience, visual, narrative). |
| D3 | Radar de Shows scheduled task paused until the Skills phase. |
| D4 | Bom Dia Claude set to Paused in Skills Mapping (rebuild in progress). |
| D5 | The two deleted Grab & Go tasks ("Conferir mapeamento Crew/SoT", "Padronizar instruções das personas") count as done by this audit; their dependencies were removed. |
| D6 | Personas: content and SoT are reviewed one by one with Odara, but the structure must be consistent and follow the Crew Mapping template, adapted to each Persona's purpose. |
| D7 | Cap, Jaume, Clau, Lola, Beastmaster and Yaikes moved to **Active** (structurally ready to be woken for content review). |
| D8 | Legacy documentation is marked [ARCHIVE], exported outside Notion (local package now, GitHub later) and then removed from Notion. "Reconciliation needed" is to be emptied and deleted. |
| D9 | Audit closes with the six pillars together. |
| D10 | GitHub is owned by Hacker; work there starts after documentation is ready. |
| D11 | Resumé is not archived: she is a Pet responding to Gibbs (like Ratz to Lori) and Odyssey's main agent for professional life. |
| D13 | Decision Log = the existing Session Log (05 A Jornada) for active-project decisions; legacy decisions go to the offline archive and are never linked from live pages. |
| D14 | Page conventions written into Manual G20; G21 comment considered finalized (resolve manually — connector needs Notion Business); G16 comment stays open until GitHub is live. |
| D12 | Lori's page is rebuilt on the Crew Mapping template following Hacker's recommendation; details confirmed when Odara wakes her. Name: Lori, The Keeper (Lore is an alias). |

## 2. Changes executed in Notion

**Marked [ARCHIVE] (legacy, still in Notion until export):** Odyssey Organization & Capability Ownership · Schedule Task Governance v1 · The Catalan Corsair (legacy persona page) · City Radar & Local Lens (old Barcelona Discovery design) · Game Design (HOLD kept) · Odyssey - AI Notice Board (database).

**Live pages corrected (no longer pointing to legacy or Mayor):** 02 O Navio (Builders, authority, reference dock) · 04 AI Crew & Skills (hierarchy = Reporting Line / Chain of Command; Scheduled Tasks live in Skills Mapping) · Operating Manual glossary · Crew Noticeboard · Create a New Persona · Chatty, The Designer · Jaume (handoff) · Bom Dia Claude ("Playbook" removed) · Skills, Workflows and Automations (container note; old overview under [ARCHIVE] heading) · Hacker, The Good (role, status, handoffs).

**Registries:** Crew Mapping Reporting Line lost unused options "Claude Mayor" and "ChatGPT" · Hacker and Chatty Responsibilities filled · Resumé briefly set to Archived, then **reverted by Odara's decision (D11)**: Pet of Gibbs, Screening, main agent for professional life; her page and Gibbs's page corrected · six Personas set to Active (D7) · Lori's page reconciled into the template (D12); previous content exported to `notion-legacy/lori-the-keeper_before-reconciliation_2026-11-17.md` · Grab & Go: 7 dependency fixes, 5 tasks to To Do, IA responsável Mayor → Hacker on 2 tasks.

**Systems:** Radar de Shows scheduled task disabled (it was the only enabled task; 20 connectors attached).

**Persona structural cleanup (logic-based, content untouched):** removed obsolete "DRAFT FOR REVIEW" banners on Active Personas (Lola, Yaikes, Beastmaster); replaced the obsolete "Notice Board follow-up" line with the live Noticeboard protocol (Lola, Yaikes, Beastmaster, Calê, Bardim, Chatty); removed "Preservation: appended" banners (Jaume, Calê, Bardim, Chatty); removed Clau's stale note about the missing Gibbs option. Audit notes and validation checklists were **kept** as input for each Persona's content session.

**Legacy removal (D8, executed 17 Nov):** the remaining [ARCHIVE] pages in 02 and 04 (Organization & Capability Ownership + Schedule Task Governance v1, Capability Model, 7 old Skill pages, Night Shift pilot + log, duplicate AI Chats roster) were moved into "To be trashed"; Odara exported it natively (Markdown & CSV, subpages, files) into `notion-legacy/to-be-trashed_export_2026-11-17/`; export checked complete (all pages, 3 databases as CSV, images present); live pages pointing into it fixed (02 O Navio, Gibbs, Jaume, Barcelona & Catalonia Discovery); then, with Odara's explicit confirmation, **"To be trashed" was moved to Notion's Trash** (restorable).

**Reconciliation needed (closed 17 Nov):** snapshot saved in `notion-legacy/reconciliation-needed_snapshot_2026-11-13.md`; every pending item routed (see table below); live links fixed in 04, 05, Hacker page and Create a New Persona; page moved to Notion's Trash. Manual updated: Session Log is the official decision record (D13); page conventions added to G20 (D14).

| Pending item | Destination |
|---|---|
| Decision Log | Session Log = official record of active-project decisions (D13) |
| Page template / naming convention | Manual G20 "Page conventions" (D14) |
| G12 proactive diary logging | Lori's session (Odara, 17 Nov) |
| Game Design paths (Main Quest cadence, Mood vs Rígido items, Memory Log) | Grab & Go "Inventariar skills e workflows" |
| Legacy Persona Skill ideas | Section 05 of Cap, Clau, Calê, Beastmaster (proposed, not built) |
| Wildcard, Persona Recognition Test | Existing Grab & Go tasks |
| Future Horizons duplicates and dated header | Chatty (05 A Jornada) |
| C-Staff / Crew Tree vocabulary | Replaced by Reporting Line / Chain of Command |
| Old notices, Session Log design notes, historic snapshots | Offline archive |

**Grab & Go redesign (17 Nov, delegated to Hacker by Odara):** previous state exported first (`notion-legacy/grab-and-go_before-redesign_2026-11-17/`: all 65 rows with properties + the two rewritten task bodies). New schema: Status (Idea, Ready | In Progress, Blocked | Done, Dropped — English, per Odara), Assignee (→ Crew Mapping), Needs Odara (You do / You decide / No), Impact, Why it matters, Mode (Quick on phone / Desk session / Persona chat), Type, Pillar, Effort, Blocked by / Blocks, Deadline. Old columns dropped (Autonomia, Categoria, IA responsável, Ordem, Owner, Prioridade, Sprint, Pronto quando, Próximo passo, Resource Principal, Resultado). Triage: 28 active tasks rewritten with a page briefing (Context · Done when · Instructions & insights · Links · What was done); 31 closed (Done, or Dropped with the merge reason in "Why it matters"). Views: 🎯 Ready for Odara (phone gallery by Mode), 🛠️ Hacker, 🎨 Chatty, 🎭 Personas, ⛔ Waiting, ✅ Done, 📋 All open, 🔗 Dependencies, 🗃️ Everything. Resolves the "5 pilares" / "Lore" finding below.

**Crew Noticeboard redesign (17 Nov, approved by Odara):** previous state exported first (`notion-legacy/crew-noticeboard_before-redesign_2026-11-17/`: all 15 notes with every property + the old protocol page). De / Para / Lido por (text options with legacy names: Mayor, Night Shift, Keymaster, Lorekeeper…) replaced by **From / To / Read by** relations to Crew Mapping; To is two-way, so each Crew member has a **📬 Noticeboard inbox** on its Crew Mapping page. New **Odara** field (From her / For her). Renamed to English: Priority, Source, Outcome, Posted on. Dropped 7 hidden legacy fields (Contexto, Por que importa, Ação sugerida, Retorno esperado, Tipo, Urgência, Expira em; their content was already in each note's body). Views reconfigured (📬 Open, 🗣️ With Odara, 🔥 Needs attention, 👥 By recipient, 📊 Board, 📦 Closed, 🗃️ All, plus three redundant tabs Odara may delete by hand: 🆕 New by arrival, 💬 Sent Back, 🧹 Lori queue). Triage: Málaga note resolved (trip done); two Mayor notes moved to Hacker as 🗣️ To Discuss for Odara; "Todos" notes re-addressed to the Personas actually concerned. Protocol page condensed and updated; skills Leave a Note, Hand Off to Persona and Noticeboard Clean-up updated (the manual list-sync step is gone). Grab & Go: new Idea "Explore a live Crew chat (Discord pilot)".

**AI Project Instructions v1.0 (17 Nov):** one short, versioned text for the Claude and ChatGPT projects that only points to Notion; official copy on the "AI Project Instructions" page (04 AI Crew & Skills, section 06). Old Claude GM instructions saved in `notion-legacy/ai-project-instructions_before-v1_2026-11-17/`. Manual G20 gained a "Before adding anything new" checklist (Odara's request, after the page was first created without integration). Decisions logged in the Session Log.

## 3. Findings still open

| Area | Finding | Next |
|---|---|---|
| Life (G22) | Long Term Contract, Empadronamiento (22 Oct) and DKV clinician (30 Oct) are overdue Rígido items in the Backlog. | Odara — outside the audit. |
| Personas | Lori: reconciled 17 Nov (D12). Open with Odara: chat link, Personal Diary page vs Diário Pessoal database, Memory Log storage, G12 scope. | Lori session. |
| Personas | Calê, Bardim: draft structure, no portrait attached, blank SoT. Gibbs: bespoke structure, Screening. Marty, The Cook, Ratz: Screening. | Persona sessions. |
| Personas | Corpo & Vitalidade holds live Calê health content under Skills W&A; Health & Wellness Profile SoT is blank. | Calê session. |
| Personas | Legacy Corsair page holds dated event lists not migrated to Barcelona & Catalonia Discovery. | Jaume session. |
| Skills | Capabilities only registered in archived rosters: Radar de Shows, Radar de Lares, Calendar Check, The Ticket. | Skills phase. |
| Skills | All scheduled tasks carry 10–23 connectors; Manutenção Diária runs in UTC; registry text ≠ prompts. | Skills phase. |
| Pages | "🇪🇸 Project Plan: Odara in Barcelona" lives outside Project Odyssey. | After export. |
| Infra | Notion connector writes as Odara (AI edits indistinguishable); Free plan = 7 days page history; GitHub backup untested. | GitHub phase. |

## 4. Not verified

Pillars 05 and 06 (out of scope) · Session Log · Crew Noticeboard rows · ChatGPT project instructions and ChatGPT scheduled tasks · GitHub repository · end-to-end Skill tests.
