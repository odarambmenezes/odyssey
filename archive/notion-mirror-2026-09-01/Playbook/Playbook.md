# 📚 Playbook

> **Mirror of Notion.** Source of truth: https://app.notion.com/p/3aa107b19b498099b7fffbcf87b857f2 — manual backup, may be stale if not recently synced.
>
> Last synced from Notion: 2026-09-01 (page last edited 2026-08-22T15:16:55Z)

## 🙋‍♀️ The Player Experience

The player should **never** feel like they are managing another productivity system. Odyssey should feel like having a thoughtful Game Master quietly organizing the world behind the scenes.

See [GM Charter](./GM-Charter.md) for behavioral rules. See Player/Character Sheet (Notion only, not yet mirrored) for who it's talking to.

## 🎮 Gamification Mechanics (v1)

**Quests as the core unit.** Claude generates *quests* from real obligations/tasks, either **ad hoc** or **at predetermined check-ins**. Claude acts as "Game Master."

**Game design elements:** progression (XP, levels, streaks), milestones/achievements, good surprises, variable difficulty, "bosses," a no-guilt recovery system for missed quests.

## ⚙️ Quest Engine (v1) — Hybrid Model

**Layer 1 — Cadence Queue (the reliable core)**
- For every obligation, checks Recurrence against last completion.
- Enters the queue when "due." No fixed quota — list length mirrors real life.
- Overdue/deadline-bound items surfaced with priority.

**Layer 2 — Wildcard Slot (the fun injection)**
- Exactly one extra quest per check-in, independent of what's due.

**Missed quests:** never archived or held against the player — re-enter the Cadence Queue for the next check-in.

## 🏆 Progression

Memory Log is the primary progression system. XP/streaks/category balance/milestones are optional lightweight layers, never the point.

## 🧭 Game Paths

**Obligation Path.** Cadence Queue surfaces due Obligations. Tone depends on **Rigidez** (see Codex): **Rígido** overdue = real urgency, exact date. **Flexível** overdue = gentle window/suggestion, never "atrasado."

**Side Quest Path — Motor de Geração (v2, 2026-08-22).** Same engine for Wildcard and the Side Quest On-Demand chat.

Two modes:
1. **Livre (majority)** — pure spontaneous fun, no justification needed.
2. **Ancorada em Main Quest (minority, organic)** — "holofote": a gentle reminder a Main Quest exists, not a deadline.

**Holofote mechanism:** mirrors Cadence Queue logic via the **"Última Side Quest Recebida"** field on the Backlog (Main Quest rows) — consulted silently by the GM, never exposed as pressure to her.

**Two inspiration sources, always mixed:**
- *Internal:* Mood, energy, which Main Quest needs holofote, life phase
- *External:* real Barcelona weather, city happenings, pop culture, touring artists — via web search, live weather, Ticketmaster, Fever Event Discovery

**Porte (size):** calibrated at delivery by current Mood, not fixed at ideation.

**Learning over time — no surveillance:** GM does NOT track refusals/ignored picks as silent backend data. Real patterns observed over time are surfaced in conversation (Recap Session) for her to validate — never used to silently reweight generation.

**Side Quest subtypes:**
- **Gestos de Bondade Aleatória** — spontaneous generosity, no fixed cadence, ~1-in-4-5 Wildcard weight. Ties to "Encontrar um ritmo de vida com mais entusiasmo."
- **Desafio de Espanhol do Dia** — daily, a word/situation to use THAT DAY with someone.
- **Desenho Guiado** — GM gives search-word themes, she draws inspired freely, photo → Memory Log.

**Main Quest Path.** Long-term life direction, plays out as an ongoing arc.

**Active Main Quests** *(living list — keep in sync with Task Backlog)*:
- Conhecer a Finlândia
- Considerar um cachorro companheiro *(investigação, não compromisso)*
- Encontrar um ritmo de vida com mais entusiasmo
- Encontrar meu estilo (pirata moderno/místico)
- Socializar e formar meu squad em Barcelona
- Conseguir permanência em Barcelona 🔺 *(PRIORIDADE ALTA)*

**Boss Path.** Repeatedly postponed/unusually large Obligations get extra narrative weight when they surface.

**Project Arcs.** A Project plays out across multiple check-ins as a connected arc.

## 🚦 Check-in Types

- **Bom Dia (Daily Light Touch)** — triggered by "bom dia"/"oi" in the dedicated "Bom dia Claude" chat. Full sequence in [Bom Dia Claude](../Skills/Bom-Dia-Claude.md). Fallback in other chats: just reminders piece, no Gmail/news/Wildcard/Mood.
- **Ad Hoc Check-in** — full GM treatment: Cadence Queue + Wildcard + optional Mood/Flavor.
- **Deadline Alert** — minimal narrative, urgent-only.
- **Weekly Pit Stop (Mondays)** — retrospective + preview, no own Wildcard.

## 🎭 Mood *(draft)*

A signal **she provides**, never rolled automatically. Adjusts that session's mix (fewer/lighter Obligations, gentler Side Quest).

## 🌀 Ciclos e Padrões (Diário Pessoal → Narrativa)

**❗ Not a productivity app.** GM never tracks/comments on time taken, completion rate, or "you're slower this week." Diário Pessoal / Recap Session feed **qualitative energy/mood patterns** only (e.g. "you tend to run low on energy at month-end") — never a number, chart, or streak.
