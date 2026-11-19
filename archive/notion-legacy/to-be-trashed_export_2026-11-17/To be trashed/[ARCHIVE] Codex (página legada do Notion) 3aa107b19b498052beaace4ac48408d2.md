# [ARCHIVE] Codex (página legada do Notion)

<aside>
ℹ️

*This page is the reference layer of Odyssey — the source of truth for what things are (not how the game plays them, that's the [Playbook](https://app.notion.com/p/3aa107b19b498099b7fffbcf87b857f2?pvs=21)).*  

</aside>

## 📖 Bestiary — The Parts of the Game

Before we jump into how it works, let's revisit the pieces of our game. Every terminolagy that we are using ont he game should be reflected here for reference.

| Entry | Definition |
| --- | --- |
| **Task** | The raw, singular unit of anything actionable — the one thing Odyssey will have an endless supply of. Comes from her or from the GM. Every Task gets triaged into either an Obligation or a Quest. |
| **Triage** | The still-to-be-designed workflow that decides whether a Task becomes an Obligation or a Quest. |
| **Obligation** | A Task that can't be postponed — it's what keeps life organized. Not necessarily fun. Tracked with a Category, Recurrence, Due Date, and Status. |
| **Category** | A life area an Obligation belongs to (Home, Health, Life in Spain, etc.) — Categories represent areas of life, not task types or mechanics. Quests typically don't need one. An Obligation can live in more than one Category at once. Full list below. |
| **Quest** | A Task (or a GM invention) that isn't a need — designed to be enjoyable rather than necessary. Splits into two flavors: Main Quest and Side Quest. |
| **Main Quest** | A Quest tied to a long-term life direction — medium/long-term aspirations rather than a single afternoon (e.g. "find a hobby off-screen," "go to Finland someday"). Plays out as an ongoing arc across many check-ins. |
| **Side Quest** | A small, spontaneous Quest — explore a new neighborhood, try a new restaurant, that kind of thing. This is what fills the Wildcard slot at each check-in. |
| **Gesto de Bondade Aleatória** | A Side Quest subtype: spontaneous generosity expecting nothing back — a heartfelt message to a stranger whose content moved her (e.g. someone on Instagram), visiting a nursing home, donating food, that kind of thing. No fixed cadence ("de vez em quando"), never becomes an Obligation. Ties naturally to the "Encontrar um ritmo de vida com mais entusiasmo" Main Quest — see Playbook, Side Quest Path. |
| **Desafio de Espanhol do Dia** | A Side Quest subtype, daily: the GM brings one word/expression or a real-life situation in Spanish, and the challenge is to actually use it THAT DAY with someone — not passive study, an active gamified prompt. Ties to language integration in Spain. See Playbook, Side Quest Path. |
| **Desenho Guiado** | A Side Quest subtype: the GM gives a handful of search words/themes (one per part of a drawing — e.g. "asas de borboleta", "textura de nuvem"), she looks each up on Google Images for inspiration, and freely draws her own version combining them. Ends with a photo of the finished piece, logged to the Memory Log. Occasional, no fixed recurrence. See Playbook, Side Quest Path. |
| **Wildcard** | The mechanic that pulls one Side Quest into every check-in, independent of what Obligations are due. Guarantees fun survives even on heavy, obligation-only days. |
| **Boss** | A big or dreaded Obligation, the kind that gets postponed for weeks. Framed with extra weight when it surfaces as a Quest instead of blending into the regular queue. |
| **Project** | A group of related Obligations/Quests with dependencies between them, potentially spanning multiple Categories. Projects are temporary and don't get their own Category — how they're tagged/tracked is still an open question (see Projects section below). |
| **Check-in** | A trigger moment when the Quest Engine runs and builds the list: fixed (morning, end of day, weekend) or ad hoc (something new enters the backlog). |
| **Mood** | An optional signal she provides herself (e.g. "I'm feeling tired today") that lets the GM tailor which Obligations/Quests surface for that check-in. Not an automatic system roll — she chooses when to invoke it. |
| **Status** | Where an Obligation/Quest currently stands. Six values, each meaning something different: **A Fazer** (pending this cycle), **Em Andamento** (actively being worked on), **Feito (Ciclo)** (light/cycle-based done — for recurring items, marks this occurrence complete without closing the item forever), **Done** (definitive, permanent — only for Pontual/one-time items), **Em Pausa** (deliberately paused, will be revisited — her choice), **Aguardando Terceiros** (blocked on someone/something outside her control). A missed one returns to the queue rather than getting marked "Failed." |
| **Última vez feito** | The date an Obligation was last completed. This is what the Cadence Queue actually checks against Recurrence to know if something is due again — not Status alone. Marking something "Feito (Ciclo)"/"Done" without updating this date breaks the recurrence math. |
| **Rigidez** | **Rígido** or **Flexível**. Rígido = a real, externally-imposed date with no give (bank due dates, legal/visa deadlines, a confirmed appointment) — Próximo Deadline is a wall, surfaced with real urgency once passed. Flexível = a recurrence that exists to create rhythm, not a hard rule — self-care, home upkeep, health habits. For Flexível items, Próximo Deadline is the **center of a window**, not a wall: calculated the same way (Última vez feito + Recorrência), but the GM stays quiet until close to that date, then mentions it casually ("por volta de", never "vencido"). Only escalates to a warmer nudge if it's slipped past roughly **2x the normal Recorrência interval** — and even then, framed as care/curiosity ("faz um tempinho, tudo bem por aí?"), never as an overdue flag. |
| **Memory Log** | The archive of proof (photos, posts, messages, reflections) from completed Quests — Odyssey's real progression system, in place of numeric XP. Only applies to Quests, never Obligations. See the Playbook's Memory Log page. |

## ✅ Completion Protocol — marking something Feito

**Any chat**, not just Building Odyssey, that marks a recurring Obligation/Quest as complete must do all three steps together, every time — never just one:

1. Set **Última vez feito** = today
2. Calculate the new **Próximo Deadline** from Recorrência (e.g. Semanal = +7 days, Mensal = +1 month)
3. Set Status to **Feito (Ciclo)** — not "A Fazer" and not "Done". This is the light, cycle-based completion state.

**Auto-revival rule:** whenever any check-in reads the Backlog (Bom Dia, Ad Hoc, Weekly Pit Stop) and finds a recurring item sitting in "Feito (Ciclo)" whose Próximo Deadline has arrived or passed, it flips Status back to **A Fazer** automatically as part of that same read — that's what makes the item resurface as pending again, without anyone having to remember to do it manually.

**Pontual (one-time) items** are different: once done, Status goes straight to **Done** — permanent, no cycle, no revival. Skip steps 1-2 (no recurrence to calculate against).

This rule lives here (not just on the Bom Dia Claude page) because it applies universally, to every routine chat that touches the Backlog.

## 🔀 How a Task Becomes Something

Every Task starts as a single raw line — "Answer my emails," "Plan a trip to Finland," "Have a nice Sunday shopping spree." From there, Triage sends it down one of two paths:

- **Task → Obligation** — needs an action point, a Recurrence, and a Category. This is the "needs to be done" branch.
- **Task → Quest** → **Main Quest** (long-term life direction) or **Side Quest** (spontaneous, one-off fun) — no Recurrence/Category required to exist.

Projects, Check-ins, and Mood aren't things a Task "becomes" — they're structures/mechanics around it (see Bestiary above).

## 📋 Task Backlog

The real backlog (34 initially mapped obligations) lives as a Notion database — the single source of data that Claude and Claude Code will read/write, with a "By Category" view already set up.

## 🗂️ Task Categories

| Category | Description |
| --- | --- |
| 🏠 Home | House maintenance: cleaning, tidying, upkeep, shopping, domestic obligations |
| 💪 Health | Physical health, nutrition, exercise, medication, appointments, sleep, wellbeing |
| 💅 Personal Care | Grooming, hygiene, skincare, hair, nails, self-care |
| 💰 Finance | Bills, budget, investments, taxes, cards, subscriptions, net worth |
| 📂 Admin | Documents, planning, digital organization, emails, bureaucracy, personal improvements |
| 💼 Work & Study | Work, studies, courses, professional development, career |
| 🤝 Social | Friends, family, relationships, messages, events, networking |
| 🇪🇸 Life in Spain | Integration: documents, bureaucracy, language, housing, adaptation |
| 🎮 Leisure | Games, movies, shows, books, hobbies, entertainment |
| ✈️ Travel | Trips, planning, bookings, documentation, temporary travel experiences |
| ✨ Auto Cuidado | Emotional self-care, journaling, reflection — distinct from Personal Care (which is grooming/physical) |

**Category governance rules:**

1. Categories represent life areas, not task types or mechanics — a task can be attached to more than one category, and they should complement each other and form a network, not isolated buckets
2. Task groups (with dependencies) can exist within one category or span several
3. Any change touching the categories must be tracked in the [Governance & Guardrails](%5BARCHIVE%5D%20Governance%20&%20Guardrails%203aa107b19b498084a54cd0317b5c5c39.md) Decision Log
4. Claude and ChatGPT both have direct access to this list and are the dominant rule source for changing/implementing/editing what's already in place
5. This is a **living** list — reviewed together every six months or as needed, nothing is final; Categories evolve much slower than tasks

## 🧩 Projects *(placeholder — not yet designed)*

Projects are temporary and no longer get their own Category (see Decision Log — "New Projects" was removed for mixing task-type with life-area). How a Project actually gets tagged/tracked in the backlog is now an open question.

When designed, this section should define: what makes a Project distinct from a Task, what fields it needs (name, related Categories, status), and how it's tracked without a dedicated Category.

## 🧱 Architecture Decision: Where the Data Lives

- **Notion (database above)** = single source of truth for live data (backlog, progress, status)
- **GitHub repo** = logic/code (quest engine, prompts, automations) built by Claude Code
- Why: lowest friction to maintain (already editing in Notion), and Claude/ChatGPT both access Notion directly without needing a sync