# Odyssey — Documentation Backup

This repo is a **manual markdown mirror** of the Project Odyssey documentation, which normally lives in Notion.

## Why this exists

On 2026-08-31, Notion publicly acknowledged an issue causing some Notion AI MCP tool calls to fail. This broke Claude's ability to write to Notion mid-session, which stalled work on the project. This repo exists so that:

1. **If Notion is fully down**, the docs/rules here can be read directly, and any chat (Claude or otherwise) can keep functioning off this content until Notion recovers.
2. **Any chat/scheduled task in the project** should still try the Notion link **first**. Only if that link errors or is unreachable should it fall back to checking the matching file in this repo. If **neither** Notion nor this repo has usable content, the chat should surface the error to Odara rather than inventing content.

## ⚠️ Notion is still the source of truth

This repo is a **backup**, not a replacement. It gets updated manually, after structural changes are made in the "Building Odyssey" Notion chat — it is not live-synced automatically (Claude has no standing background process; syncing happens only when explicitly done during or after a session).

If a file here looks out of date compared to what a chat remembers, **trust Notion first** — this file may simply not have been re-synced yet.

## Structure

Mirrors the Notion page hierarchy:

```
/Codex/                — reference layer (what things are)
/Playbook/              — mechanics + GM Charter (how the game plays / how the GM behaves)
/Governance/             — decision log, guardrails
/Skills/                 — individual routine chat prompts (Bom Dia Claude, Meal Routine, etc.)
```

## Last full sync

**2026-09-01** — Codex, Playbook, GM Charter mirrored. Governance and Skills folders still pending — to be added in a follow-up sync.
