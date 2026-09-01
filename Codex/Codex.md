# Codex

> This page is the reference layer of Odyssey — the source of truth for **what things are** (not how the game plays them, that's the [Playbook](../Playbook/Playbook.md)).
>
> **Mirror of Notion.** Source of truth is still Notion: https://app.notion.com/p/3aa107b19b498052beaace4ac48408d2 — this file is a manual backup, synced whenever a structural change happens in the "Building Odyssey" chat. If Notion is down, use this file, but flag to Odara that it may be slightly stale (check `page_last_edited_at` noted below vs. today).
>
> Last synced from Notion: 2026-09-01 (page last edited 2026-08-22T11:30:00Z)

## 📖 Bestiary — The Parts of the Game

| Entry | Definition |
|---|---|
| **Task** | The raw, singular unit of anything actionable — the one thing Odyssey will have an endless supply of. Comes from her or from the GM. Every Task gets triaged into either an Obligation or a Quest. |
| **Triage** | The still-to-be-designed workflow that decides whether a Task becomes an Obligation or a Quest. |
| **Obligation** | A Task that can't be postponed — it's what keeps life organized. Not necessarily fun. Tracked with a Category, Recurrence, Due Date, and Status. |
| **Category** | A life area an Obligation belongs to (Home, Health, Life in Spain, etc.) — Categories represent areas of life, not task types or mechanics. Quests typically don't need one. An Obligation can live in more than one Category at once. |
| **Quest** | A Task (or a GM invention) that isn't a need — designed to be enjoyable rather than necessary. Splits into two flavors: Main Quest and Side Quest. |
| **Main Quest** | A Quest tied to a long-term life direction — medium/long-term aspirations rather than a single afternoon. Plays out as an ongoing arc across many check-ins. |
| **Side Quest** | A small, spontaneous Quest — explore a new neighborhood, try a new restaurant, that kind of thing. Fills the Wildcard slot at each check-in. |
| **Gesto de Bondade Aleatória** | Side Quest subtype: spontaneous generosity expecting nothing back. No fixed cadence, never becomes an Obligation. Ties to "Encontrar um ritmo de vida com mais entusiasmo" Main Quest. |
| **Desafio de Espanhol do Dia** | Side Quest subtype, daily: one word/expression or real-life situation in Spanish, challenge is to use it THAT DAY. Active/social, not passive study. |
| **Desenho Guiado** | Side Quest subtype: GM gives search-word themes, she draws freely inspired by them, photo goes to Memory Log. Occasional, no fixed recurrence. |
| **Wildcard** | The mechanic that pulls one Side Quest into every check-in, independent of what Obligations are due. |
| **Boss** | A big or dreaded Obligation, postponed for weeks. Framed with extra weight/support when it surfaces. |
| **Project** | A group of related Obligations/Quests with dependencies, potentially spanning multiple Categories. Temporary, no own Category (open question on tracking). |
| **Check-in** | A trigger moment when the Quest Engine runs: fixed (morning, end of day, weekend) or ad hoc. |
| **Mood** | An optional signal she provides herself — not an automatic system roll. |
| **Status** | Six values: **A Fazer** (pending), **Em Andamento** (in progress), **Feito (Ciclo)** (light/cycle done — recurring items), **Done** (permanent — one-time items only), **Em Pausa** (deliberately paused), **Aguardando Terceiros** (blocked on someone/something outside her control). |
| **Última vez feito** | Date an Obligation was last completed — what the Cadence Queue checks against Recurrence, not Status alone. |
| **Rigidez** | **Rígido** or **Flexível**. Rígido = real externally-imposed date, no give — a wall. Flexível = recurrence for rhythm, not a rule — Próximo Deadline is the *center of a window*. Only escalates if slipped ~2x the normal interval, and even then framed as care, never as overdue. |
| **Memory Log** | Archive of proof (photos, posts, reflections) from completed Quests — Odyssey's real progression system, replacing XP. Only Quests, never Obligations. |

## ✅ Completion Protocol — marking something Feito

**Any chat**, not just Building Odyssey, that marks a recurring Obligation/Quest as complete must do all three steps together, every time:

1. Set **Última vez feito** = today
2. Calculate the new **Próximo Deadline** from Recorrência (Semanal = +7 days, Mensal = +1 month, etc.)
3. Set Status to **Feito (Ciclo)** — not "A Fazer" and not "Done". Light, cycle-based completion.

**Auto-revival rule:** whenever any check-in reads the Backlog and finds a recurring item in "Feito (Ciclo)" whose Próximo Deadline has arrived/passed, it flips Status back to **A Fazer** automatically — no one has to remember to do it manually.

**Pontual (one-time) items:** once done, Status goes straight to **Done** — permanent, no cycle, no revival. Skip steps 1–2.

## 🔀 How a Task Becomes Something

Every Task starts as a single raw line. Triage sends it down one of two paths:

- **Task → Obligation** — needs an action point, a Recurrence, and a Category.
- **Task → Quest** → **Main Quest** or **Side Quest** — no Recurrence/Category required to exist.

## 📋 Task Backlog

The real backlog lives as a Notion database (single source of data):
https://app.notion.com/p/c72071d037784ba5b6308c82a5a36d07
(`data-source-url`: `collection://a4f2dc93-71ae-44c6-8049-b2cd8f752220`)

## 🗂️ Task Categories

| Category | Description |
|---|---|
| 🏠 Home | House maintenance: cleaning, tidying, upkeep, shopping, domestic obligations |
| 💪 Health | Physical health, nutrition, exercise, medication, appointments, sleep, wellbeing |
| 💅 Personal Care | Grooming, hygiene, skincare, hair, nails, self-care |
| 💰 Finance | Bills, budget, investments, taxes, cards, subscriptions, net worth |
| 📂 Admin | Documents, planning, digital organization, emails, bureaucracy |
| 💼 Work & Study | Work, studies, courses, professional development, career |
| 🤝 Social | Friends, family, relationships, messages, events, networking |
| 🇪🇸 Life in Spain | Integration: documents, bureaucracy, language, housing, adaptation |
| 🎮 Leisure | Games, movies, shows, books, hobbies, entertainment |
| ✈️ Travel | Trips, planning, bookings, documentation |
| ✨ Auto Cuidado | Emotional self-care, journaling, reflection — distinct from Personal Care (grooming/physical) |

**Category governance rules:**

1. Categories represent life areas, not task types/mechanics — a task can belong to more than one.
2. Task groups (with dependencies) can exist within one category or span several.
3. Any change touching categories must be tracked in the [Governance & Guardrails](../Governance/Governance.md) Decision Log.
4. Claude and ChatGPT both have direct access and are the dominant rule source for changing this list.
5. Living list — reviewed every six months or as needed.

## 🧩 Projects *(placeholder — not yet designed)*

Projects are temporary and don't get their own Category. How a Project gets tagged/tracked in the backlog is an open question.

## 🧱 Architecture Decision: Where the Data Lives

- **Notion (database above)** = single source of truth for live data (backlog, progress, status)
- **GitHub repo** (this repo) = markdown backup/mirror of the documentation + logic, so the project survives a Notion MCP outage
- Notion remains primary; this repo is the fallback, manually synced after structural changes in Building Odyssey
