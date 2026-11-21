# Changelog — structural sessions

Every structural change to Project Odyssey is logged here by the Builder session that made it (Operating Manual G21). Newest first. Decisions are also recorded in Notion's Session Log.

## 2026-11-21 (later) · Hacker (Claude Code)
Gmail Sweep v2.1, after Odara's own chat pilot with ChatGPT and two Noticeboard notes to Hacker.
- **Gmail Sweep updated in place to v2.1:** Review (read-only) and Cleanup modes with natural triggers; Cleanup runs to the end with one report; status labels (🔥 Action Needed stays in the inbox, ⏳ Waiting stays during the pilot); `🧾 Comprovantes` registered as a protected category; DiR Tuset / Santander added to the protected list. https://app.notion.com/p/3fe107b19b4980a7a771d69a0746f355
- **Retention decided by Odara:** pilot = archive only, the sweep never trashes; review on 2026-12-21. Target rule to test then: archive + 60-day manual review by default, straight to Trash only for an approved list (Gmail's 30-day Trash is the margin). Not active.
- **Chat pilot findings (label counts only):** inbox 295 → 30 threads, Trash about +118 threads, all approved by Odara in that chat. 23 Eventos / Profissional threads were archived without the retention label; backfill waits for her OK. Trash contents cannot be listed through this connector.
- **Noticeboard:** answered "Review Gmail Sweep skill proposal against the existing v2 pilot" (verdict: adapt) and "Decide the skill proposal review process" (proposal: Skill review request through existing Noticeboard → Grab & Go path); both 🗣️ To Discuss.
- **Deferred by Odara:** moving rules/specs to a GitHub-first PR workflow. Documentation stays as it is until the audit closes.
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
