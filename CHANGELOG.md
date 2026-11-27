# Changelog — structural sessions

Every structural change to Project Odyssey is logged here by the Builder session that made it (Operating Manual G21). Newest first. Decisions are also recorded in Notion's Session Log.

## 2026-11-27 · Hacker (Claude Code) · documentation audit
Odara asked for a last check that Notion is live documentation, not a dump. Approved as one batch ("lote ok").
- **06 O Hoje → Reconciliada:** the text matches the real state (Captain's Deck is the live window; Gibbs is Active, no GM custody; only the task Backlog and the Shopping List remain to migrate). Founding brief of 12 Nov moved to the Session Log. https://app.notion.com/p/416107b19b4981f4beeeecc87e51b8bd
- **Retreat plan** ("(Realinhar) Planejamento de Retiro") moved from inside 06 O Hoje to Lori, The Keeper, with a current status line. Consolidation of its content stays with Lori (Persona content). Not in this repository (G22).
- **02 O Navio:** "UNDER AUDIT" removed; G21 wording includes Hacker's elevated access; Communication section describes how work moves today (tickets, Captain's Deck, Slack, no automations running); readiness table updated. https://app.notion.com/p/40c107b19b498031b5e5f5fa01cc84b6
- **Crew Mapping:** Lori and Hacker Status set to Active.
- **Test leftovers:** fictional shared-check answers, replies and the mention test ticket exported to `archive/notion-legacy/shared-check-test-pages_2026-11-27.md` and moved to Trash. Lori's deck pages kept.
- **Finding:** "the untitled pages" around the Noticeboard are layout blocks of 02 O Navio, not pages. Lori's deck "Como a gente trabalha" (4 cards) lives only on a test page, so Mesa Rápida does not show it.
- **Still open:** 05 A Jornada (Diary and Memory Log, with Lori).
- Snapshot refreshed: `pages/02-o-navio.md`, `pages/06-o-hoje.md`. Session Log: https://app.notion.com/p/425107b19b498189b525d82f13acd917

## 2026-11-27 · Hacker (Claude Code)
Captain's Deck MVP, ticket deep links, and the tickets v2 groundwork.
- **Captain's Deck (home dashboard), approved by Odara:** https://claude.ai/artifact/QrhEpSQEGxgaM4voXoWUqf. Widgets on a snap grid (12/8/4 columns) that Odara drags, resizes, minimizes and removes; each screen size keeps its own layout, synced in the artifact's private per-user store. Reads Notion views (Tickets, Backlog Tasks and Quests, Crew Tree, Noticeboard Open, Source of Truth Mapping, Skills, Session Log, Architecture Overview) and Google Calendar (personal, Prazos, Rotinas, Tarefas, Travel). Home page section changed from "coming soon" to live; Grab & Go "Design the Captain's Deck MVP on the home page" closed with Proof.
- **Captain's Deck, leader view (same day):** "Próxima ação" ranks what needs Odara (overdue rigid tasks, notes for her, high-impact card decks, checkout, tasks due today) with one primary action; "Riscos e prazos" (overdue, 🔺 Prazos in 7 days, waiting on third parties, blocked tickets, stale notes); "Saúde do projeto" (audit %, flow, stale, closed without proof, skills proven in real use); count badges on widget headers; Focus mode; preferences for theme, density, TV mode (screen kept awake) and refresh interval, synced across devices.
- **Crew chat ("Salas da tripulação") in the Captain's Deck:** rooms, direct rooms per Persona, new rooms with chosen members, read-only # noticeboard room; an @mention wakes the Persona, who answers via Claude using her Crew Mapping page (tagged "via Claude"); one hop of Persona-to-Persona mentions, max 3 replies per message; emoji avatars until Lori designs real ones. Messages live in the deck's private database. Grab & Go "Explore a live Crew chat (Discord pilot)" moved to In Progress with this as its first version.
- **Crew chat, Slack-style:** `@` suggests people (members first, outsiders are invited when mentioned) with their area; `#` suggests rooms and renders room links.
- **Personas act from the chat (direction A, approved by Odara):** read tools (Odyssey lists, Notion pages) always; write tools only on Odara's explicit ask in her own message (G21 level 2): Backlog task, Grab & Go ticket (optionally with cards), Noticeboard note, Session Log decision. Chained Persona replies can only read. Each action appears in the room as an AÇÃO line with the link. Noticeboard announcement to Gibbs and Lori.
- **Archive a room:** on Odara's click and an inline confirmation, a Persona summarises the room; summary and transcript go to the Session Log, then the room's messages are cleared (no automatic deletion).
- **Crew runner (direction B, approved by Odara):** scheduled task "Odyssey Crew: respostas do Deck", hourly at :17 from 9:00 to 22:00 Madrid, fresh session each run, push notification on. Answers @mentions left unanswered for 10+ minutes; same action rules as the Deck; pushes only when a Persona needs Odara's approval. Created without connector grants: Notion must be added to it in claude.ai for the Personas to read their pages and act.
- **Lori:** Grab & Go ticket to design the Crew avatars.
- **Mesa Rápida (iPad):** https://claude.ai/artifact/LVemhsTyXAAQpwx8TvV1Lz . Reads every Ready ticket with a Check deck (Gibbs, Lori, Hacker) and regroups the cards into 8 categories (career, money, home, travel, retreat, visual and style, shopping, Odyssey); swipe or tap; answers saved into each ticket's answers block in the panel's format; a finished ticket gets Answered on and moves to In Progress; an "Ajuste" button sends Odara's voice or text note to Hacker through the Noticeboard. Linked from the Deck's tickets widget.
- **Slack workspace (later the same day):** Odara connected a new Slack workspace and prefers Slack as the conversation layer. Channels created: #ponte, #retiro, #viagens, #carreira-e-dinheiro, #casa-e-vida, #noticeboard, each with an intro message. Personas will post under Odara's name with an emoji prefix until a bot per Persona exists. The crew runner was switched to Sonnet and then paused by Odara while she decides the next step.
- **Tickets panel:** `#checkout` opens the checkout directly; the cards lane now holds the deck itself (no separate screen); `#t-` plus a page id opens that ticket directly, used by the deck's quick choice.
- **Mesa do Capitão v2:** Lori's experience brief received as a Grab & Go ticket; navigable prototype with fictional data and a behaviour contract written into the ticket (https://claude.ai/artifact/3HerzoFD4tXLpf8RaD5YDa). Production waits for Odara's go-ahead.
- **Lori review request** posted on the Noticeboard; Lori answered with the v2 brief.
- **House tidy-up (26/11):** four finished Grab & Go rows closed with Proof (shared Check test, Lori wake-up, Gibbs prompt, Grab & Go placement); two stale Noticeboard notes resolved. The rest became a ticket with 8 cards for Odara ("Arrumar a casa"), not executed yet.
- **New tickets from Gibbs and Lori (27/11):** eight decks covering career, ERE, money, housing, legacy clean-up, shopping list and Lori's Crew check, to close the documentation audit.
- Session Log: https://app.notion.com/p/425107b19b4981ca80a1fd362054a690

## 2026-11-26 · Hacker (Claude Code)
Hacker's elevated access, Grab & Go as the ticket system, and the tickets panel pilot v1 ("Mesa do Capitão", provisional name).
- **Manual G21:** Hacker has elevated access (Odara, live): he changes Notion structure directly when she asks or within an approved task, without routing it through Gibbs; Gibbs also changes structure from his chat. Glossary, "Who changes what" and the permissions table updated. Language rule: English is the operational base, pt-BR mixed in when it fits. Snapshot synced.
- **Grab & Go becomes the ticket system:** description widened (project tasks plus alignment requests for Odara); new relation "Requested by" (Crew Mapping); new view 🎫 Tickets (Needs Odara = You decide / You do, not Dropped, sorted by Impact). The Crew Noticeboard keeps messages and FYI only; anything that needs Odara's answer becomes a ticket.
- **Product proposal** from four UX research passes, approved by Odara as pilot v1 with one change: a single checkout report, always to Hacker, who acts on his items and posts a Noticeboard note for any other Persona. https://claude.ai/artifact/8kKx6EfmE8K3Ge3qVQ1dRW
- **Grab & Go schema:** new properties Cards (number of Check cards), Answered on, Delivered on, Proof. Done needs Proof.
- **Tickets panel v4** at the same link: lanes 🃏 com cartas / 🫵 para você fazer / 👀 com a tripulação / ⛔ / 💡 / ✅; "Resolver 5 agora" with a finish screen and a "mutirão" for everything with cards; "Agora não" and 4-second undo on every card; recommended option and consequence line; stale and "sem prova" flags; checkout that builds one report for Hacker and sets Delivered on. https://claude.ai/artifact/3JAv7SUbpTZDeTTHQeSCQg
- **Check Interativo skill:** lanes, card rule for all Personas, Cards property, checkout and Hacker's handling rule. Snapshot added: `notion-snapshot/pages/skills/check-interativo.md`.
- Open: triage of about 40 old rows in the 🎫 Tickets view (bulk change, needs Odara's go-ahead); Odara runs a first round; phase 2 adds the weekly metrics summary and Hacker reading answers directly from Notion.
- Session Log: https://app.notion.com/p/424107b19b4981f3b0f6e44c5c035112 · https://app.notion.com/p/424107b19b498113b161cc7c435ca857 · https://app.notion.com/p/424107b19b4981dd84cfd924a9ad097a

## 2026-11-25 · Hacker (Claude Code)
Cross-chat consolidation. Odara closed most open chats; each left a numbered handoff on the Crew Noticeboard (HANDOFF 01–15, two notes numbered 12, and two titled HANDOFF CLAUDE 02). All 17 were read together, checked against live Notion, Calendar, Gmail and Hotmail, and turned into yes/no decisions that Odara answered live.
- **Operating model:** two main chats. Gibbs gets his own Claude chat as operational lead; Lori works in ChatGPT, or wherever a task runs best. Hacker stays the Builder in Claude Code, invoked by Gibbs or Odara (this corrects an earlier wording the same day that had Gibbs absorbing the Builder role). Crew Mapping is formalized at the retreat (no Persona page changed). Grab & Go: write Gibbs' wake-up prompt with Odara.
- **Life Backlog (records, G22-light):** the passport task is set to Aguardando Terceiros (electoral clearance 24/11, e-Consular sent 24/11, no consulate reply yet, deadline 14/03/2027); its duplicate stays closed as history. The psychologist task was closed and consolidated into Pagar contas mensais (due on the 5th, notified with the other bills). Cap's "Reconciliar Perfil de Viagem" was marked Done.
- **Calendar:** the 26/11 passport event, created by a closing chat for an already-resolved step, now checks the consulate's reply instead.
- **Skills Mapping:** Cap's Journey registered as On Draft (Restricted, used by Cap): https://app.notion.com/p/423107b19b4981f6b602e0ead0b60d2f
- **Sweep (Gmail + Agenda):** Chatty's output contract confirmed as final; heading 🫵 Needs Me; full inline drafts only when the next move is Odara's. Snapshot refreshed (it had drifted since 22/11 through other sessions' edits: task calendars, Hotmail, unread rule, output contract).
- **05 A Jornada:** Archive toggle removed; Session Log named as the decision record (the "Decision Log not verified" text is gone). **06 O Hoje:** Grab & Go placement recorded as decided (stays in 02 O Navio).
- **Future Horizons:** business ideas index (Empresa de Layoff, Urban Transit Lounge, Escambo, VR for phobias, hospitality); header updated. HANDOFF 12 said Escambo had never been saved; it had been, since 02/11.
- Parked: Volta pra Base iPad dashboard (same surface as the Captain's Deck), Lola's hair, Jaume's SoT test, Cap's voice fixes, Radar de Shows artifact sync, the resolve-is-fun UX principle. Shopping List waits for Gibbs.
- **Bills:** all November bills paid (Odara); the table now reads November. New Grab & Go task for Gibbs: specific payment reminders and a receipts system across Gmail and Hotmail.
- **Calendar rule:** reminders and task blocks are free and never early (from about 13:00). Passport check moved to 26/11 13:00; 15-minute block to answer the psychologist on WhatsApp (new Backlog task).
- **ChatGPT automations** for the passport retired by Odara (she removes them in ChatGPT); the Sweep covers consulate replies.
- **Trip History template** confirmed final.
- **Wake-up prompts:** Gibbs (Claude chat, prompt v2 in English, no fixed language rule) and Lori (ChatGPT, written by Odara with ChatGPT). Lori also becomes the experience director, taking over Chatty's narrative, art and UX direction. Both prompts are kept in their Grab & Go tasks: https://app.notion.com/p/423107b19b4981da9c30f6c9e07b52c1 · https://app.notion.com/p/423107b19b4981d09354d0525bd3a4b3
- **All 17 handoff notes** marked Resolved, pointing to one consolidated memory page (the Session Log entry below).
- Session Log: https://app.notion.com/p/423107b19b4981d5be90ec82d88edb3e

## 2026-11-22 (later) · Hacker (Claude Code)
Odara answered the 21 Nov scan questions. Content only (Sources of Truth and Persona-domain pages, not in the snapshot, G22) plus record updates:
- **Islands** clarified by Odara: pillars of her life built from core memories (Inside Out), not Personas; list and names come from the retreat. Grab & Go task corrected and set to Blocked: https://app.notion.com/p/41f107b19b49810788c4cc1c390f3b6b
- **Health:** Odara is in the Fortis ERE; hospital insurance waits for the retreat and the ERE terms. Backlog coverage item → Em Pausa / Flexível. Last check-up: Brazil, around Apr–May 2026. Noticeboard note to Calê to design check-ins (weight, photo, more health data): https://app.notion.com/p/420107b19b4981669205c5f5ad2ae706
- **ERE context** added to the Professional Profile (Gibbs) and Financial Reports (Marty); Tenant Profile corrected (housing alerts already filtered out of the inbox).
- **Entertainment Hub:** taste is eclectic and mood-driven; Spotify reading approved.
- **Trip History:** Sevilha e Málaga companions → "Solo (met people there)".
- **Session Log numbering:** the 21 Nov (night) entry was renumbered #7, since a parallel session used #5 and #6. This session: #8 https://app.notion.com/p/420107b19b4981dcb681ffee9059346d

## 2026-11-22 (afternoon) · Hacker (Claude Code)
Backlog fresh start and retreat squad, approved by Odara batch by batch.
- **Life Backlog cleaned (bulk):** 63 open items with 33 overdue became 29 open with 0 overdue. Stale September/October items and the CNH reference closed; duplicate passport and choir items merged ("Mapear aulas de música"); 11 routines restarted from 22/11; 7 medical appointments, all 7 Main Quests and the long-term rental contract paused (Calê, retreat); health-coverage decision closed to be redone with Calê. The status `Done` was used for obsolete items because the Backlog has no "dropped" status. https://app.notion.com/p/c72071d037784ba5b6308c82a5a36d07
- **Passport task** set In Progress with the state read from Gmail (electoral clearance pending).
- **Cap's 10 items:** 1 closed (already registered), 1 kept as Odara's own planning, 1 to Grab & Go (Side Quest format), 6 handed to Cap on the Noticeboard; a cross-Persona "street mode" rule proposed in Grab & Go.
- **Calendar:** blocks created for 23/11 (DKV appointment, creating the Prazos and Rotinas calendars, TSE certificate). The connector cannot create calendars; Odara creates them, then routines move from the Backlog to the calendar.
- **Retreat squad (Odara, Lori, Gibbs):** pack posted on the Noticeboard listing what exists and nine decisions the project needs back. https://app.notion.com/p/420107b19b498101ae6ae2af1633c635
- Session Log #7.

## 2026-11-22 · Hacker (Claude Code)
Gmail Sweep becomes Sweep (Gmail + Agenda), after Chatty's experience proposal on the Noticeboard and Odara's approval of three decisions.
- **Same Skills Mapping row, renamed and extended to v3:** reads Google Calendar (primary, Pessoal, Travel in full; Fortis busy only; Família and Brazil holidays when relevant); dashboard My Day / What's New / Needs Me / Waiting / Cleanup; voice-first decisions; resolution reconciliation; events passed to Bardim only on her word, as one rolling note. Integrations now Gmail + Google Calendar. `Last real run` stores date + time of the last completed sweep. https://app.notion.com/p/3fe107b19b4980a7a771d69a0746f355
- **Live references renamed:** Bom Dia Claude page, the Bom Dia quick-action row, Monthly Digital Declutter. Historical pages keep the old name. Snapshot file renamed to `notion-snapshot/pages/skills/sweep-gmail-agenda.md` (personal email address redacted).
- **First Review run:** 4 calendars and 27 new emails read, 0 Gmail changes.
- **Housing alerts:** found already routed to `Spain Housing 2026` and out of the inbox by an existing Gmail filter; documented in the skill, nothing changed in Gmail.
- **Noticeboard:** proposal note resolved; its separate investigation request (chats skipping the Noticeboard checks) moved to Grab & Go: https://app.notion.com/p/420107b19b4981aab2a6c4205e47dd95
- Session Log #5: https://app.notion.com/p/420107b19b4981fdae63d10d28088a89
- **Odara's Voice calibrated (approved by Odara):** seven rules from her feedback on a birthday draft (per-contact nicknames, diacritics as register in casual tiers, continuation lowercase, carioca dialect, connotation blocklist, relational callback slot, affectionate teasing) and a first person card, kept inside the voice profile until a friendship space exists. The old hygiene rule treating omitted accents as typos was replaced. Birthday table updated with the missing date. Not snapshotted: the voice profile holds personal details of third parties (G22). https://app.notion.com/p/3fe107b19b498044b5edfba6128ba15a · Session Log #6: https://app.notion.com/p/420107b19b4981949425e007aa748b74
- **Grab & Go idea:** friendship space with one card per close person: https://app.notion.com/p/420107b19b4981368ea6fa82a94a09af

## 2026-11-21 (night) · Hacker (Claude Code, parallel session)
Autonomous scan while Odara was away, at her request. Content of Sources of Truth and Persona pages is not in the snapshot (G22); only what changed is listed here.
- **Trip History:** new text property `Companions` (who went on the trip). "Sevilha e Málaga" set to Post Mortem Needed, Companions Solo, with a post-mortem section for Cap.
- **Calê's page** aligned to TEMPLATE > PERSONA (hero brief, summon phrase, 01–08); the October audit notes were kept in a toggle in 08.
- **Health & Wellness Profile** v0.1: plan DKV Famedic Plus (outpatient only, company policy), care map pointing to the Backlog, light tracking proposal. Hospital coverage gap flagged; new Backlog item "Decidir cobertura de saúde: lacuna hospitalar e pós-Fortis".
- **Entertainment Hub:** taste map v0.1, inferred from Radar de Shows and ticket emails.
- **Tenant Profile:** housing search paused until the retreat (Odara's decision); Grab & Go "Moradia (Clau)" set to Blocked.
- **Grab & Go:** "Wake up Calê" → Ready; "Align Calê, Bardim and Gibbs pages" → In Progress; new Idea "Design the Islands (Inside Out style) for O Hoje" (Chatty + Hacker).
- No schema snapshot refresh for Trip History: it is not among the core databases in `notion-snapshot/schema/`.

## 2026-11-21 (evening) · Hacker (Claude Code)
- **Send lock removed, label tools pre-approved (asked by Odara):** `.claude/settings.json` no longer denies Gmail send / reply / forward, and now allows the Gmail label and unlabel tools (labelling and archiving) without a prompt in Builder sessions. Sending, Trash and new labels still follow G23 and the Gmail Sweep skill. The file never affected Claude chat or ChatGPT.

## 2026-11-21 (later) · Hacker (Claude Code)
Gmail Sweep v2.1, after Odara's own chat pilot with ChatGPT and two Noticeboard notes to Hacker.
- **Gmail Sweep updated in place to v2.1:** Review (read-only) and Cleanup modes with natural triggers; Cleanup runs to the end with one report; status labels (🔥 Action Needed stays in the inbox, ⏳ Waiting stays during the pilot); `🧾 Comprovantes` registered as a protected category; DiR Tuset / Santander added to the protected list. https://app.notion.com/p/3fe107b19b4980a7a771d69a0746f355
- **Retention decided by Odara:** pilot = archive only, the sweep never trashes; review on 2026-12-21. Target rule to test then: archive + 60-day manual review by default, straight to Trash only for an approved list (Gmail's 30-day Trash is the margin). Not active.
- **Chat pilot findings (label counts only):** inbox 295 → 30 threads, Trash about +118 threads, all approved by Odara in that chat. 23 Eventos / Profissional threads were archived without the retention label; backfill waits for her OK. Trash contents cannot be listed through this connector.
- **Noticeboard:** answered "Review Gmail Sweep skill proposal against the existing v2 pilot" (verdict: adapt) and "Decide the skill proposal review process" (proposal: Skill review request through existing Noticeboard → Grab & Go path); both 🗣️ To Discuss.
- **Deferred by Odara:** moving rules/specs to a GitHub-first PR workflow. Documentation stays as it is until the audit closes.
- **Retention backfill (approved by Odara):** of 20 Eventos / Profissional threads without retention, 3 newsletters got `Pré-Arquivo/30 dias`; 17 were transactional or employment mail mislabelled in the chat pilot and got no retention (relabelling left for the 2026-12-21 review).
- **Relabelling (approved by Odara):** 16 of those threads lost the wrong category; 5 bookings / tickets / purchase confirmations moved to `🧾 Comprovantes`. Inbox and Trash untouched.
- **New Gmail label `💼 Carreira`** (approved by Odara): applied to the 8 job-application and work-account threads; registered in Gmail Sweep as a protected category.
- **Send lock (asked by Odara):** `.claude/settings.json` denies the Gmail send, reply and forward tools in every Builder session, so nothing can be sent to third parties even in Auto mode. Drafts, labels and archiving are unaffected. Lives on the working branch until merged to `main`.
- Grab & Go pilot task deadline set to 2026-12-21: https://app.notion.com/p/41f107b19b49819d884bdbb5915a6c63

## 2026-11-21 · Hacker (Claude Code)
Gmail Sweep v2 pilot, Monthly Digital Declutter draft, G21 proposal (Designer handoff approved by Odara).
- **Gmail Sweep rewritten in place as v2** (English): inbox triage + cleanup, protected classes, independent retention and category labels, 60-day pilot safeguard, no automatic deletion, on demand only (no schedule). Properties updated (Mission, Trigger, Use Cases, Recurrency, Referencia Interna, Last real run). Notion: https://app.notion.com/p/3fe107b19b4980a7a771d69a0746f355
- **Bom Dia quick-action row** (Registro de Ações Rápidas) now points to the canonical skill instead of its own "blocks of 2-4" text. Bom Dia Steps relation unchanged. https://app.notion.com/p/3cf107b19b498149a587f93b3d37ad7c
- **Gmail labels created** (none existed before): `Pré-Arquivo` › `Pré-Arquivo/30 dias`, `Pinterest`, `Eventos`, `Profissional`. Existing labels untouched. No filters created.
- **Pilot sample:** 6 threads (3 Pinterest, 2 Fever marketing, 1 Zapier) labelled category + retention and removed from the inbox; ticket/purchase confirmations and uncertain threads left in the inbox. Nothing deleted, nothing sent. Counts-only record in the Grab & Go task.
- **Monthly Digital Declutter** registered in Skills Mapping as On Draft, not activated, not scheduled. https://app.notion.com/p/41f107b19b4981ef8709fe715fbea608
- **G21 amendment proposed, not applied** (chat Personas may register On Draft skill-idea rows). Wording in Grab & Go: https://app.notion.com/p/41f107b19b49819d884bdbb5915a6c63
- Session Log #4: https://app.notion.com/p/41f107b19b49818cb48fdeeff71c5580
- **Drift found:** Skills Mapping had gained `Integrations` and `Last real run` after the 2026-11-19 snapshot with no changelog entry. Not made in this session; snapshot refreshed to match Notion.

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
