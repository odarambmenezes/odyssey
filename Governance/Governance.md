# Governance & Guardrails

> Meta-rules for how the project runs, evolves, and stays safe to build on — plus the Decision Log and Session Log. Definitions of what things *are* live in [Codex](../Codex/Codex.md).
>
> **Mirror of Notion.** Source of truth: https://app.notion.com/p/3aa107b19b498084a54cd0317b5c5c39 — manual backup, may be stale.
>
> Last synced from Notion: 2026-09-01

## 🧱 Decision Log

*(abbreviated — see Notion for the full historical log; this mirror keeps the most structurally important entries plus anything added since the GitHub backup began)*

| Decision | Reasoning | Status |
|---|---|---|
| Notion database = single source of truth for live data; GitHub repo = logic/docs backup only | Lowest friction to maintain; Claude/ChatGPT access Notion directly | Locked |
| Repo structure mirrors the Notion page hierarchy 1:1 | So nothing is ambiguous about where something belongs | Locked |
| Quest Engine v1 = Hybrid model (Cadence Queue + one Wildcard slot per check-in) | Cadence guarantees nothing gets lost; Wildcard keeps fun alive | Locked |
| Claude is primary GM; ChatGPT stays complementary for Side Quest/personal recommendation input | Claude runs the system day-to-day | Locked |
| Status field expanded to 6 values (A Fazer, Em Andamento, Feito (Ciclo), Done, Em Pausa, Aguardando Terceiros) with auto-revival | Old 3-state model too rigid — see Codex, Completion Protocol | Locked |
| "Rigidez" field (Rígido/Flexível) added to Backlog | Hard deadlines and soft self-care cadences were being treated identically | Locked |
| Bom Dia Claude redesigned as HTML artifact ("mesa de tarot" visual identity), with Carta do Dia mechanic replacing plain "Frase do Dia" | Wanted more delight/chaos in the daily routine; full detail in Skills/Bom-Dia-Claude.md | Locked |
| Side Quest generation engine v2 (livre/ancorada via "holofote") | Previous logic was thinner; see Playbook, Side Quest Path | Locked |
| **GitHub backup repo created (`odarambmenezes/odyssey`), made public** (2026-09-01) | Notion publicly acknowledged an MCP tool-call reliability issue (2026-08-31) that stalled work mid-session. Repo holds a manual markdown mirror of docs (Codex, Playbook, GM Charter, Governance, Skills) as a fallback. No personal task data ever committed here — that stays in private Notion only. | Locked |
| **Notion → GitHub fallback rule added to GM Charter** (2026-09-01) | Any chat/scheduled task should try the Notion link first; only on error/unreachable, check the matching file in this repo; if neither works, surface the error to Odara rather than inventing content. Sync from Notion → GitHub happens manually, after structural sessions in Building Odyssey — not automatic/background. | Locked |

## 🗓️ Session Log

*(abbreviated — see Notion for full history)*

| Date | What we worked on |
|---|---|
| 2026-07-27 | Defined Vision, taxonomy, initial Backlog, Quest Engine v1, Codex/Playbook split. |
| 2026-08-01 | Created Building Odyssey chat, Meal Routine designed. |
| 2026-08-22 to 08-30 | Bom Dia Claude fully redesigned (HTML artifact, tarot table visual identity, Carta do Dia mechanic, illustrations, interactivity). Side Quest engine v2. Rigidez + Status overhaul. |
| 2026-08-31 | Notion acknowledged MCP tool-call reliability issue — writes to Notion became intermittent mid-session. |
| 2026-09-01 | GitHub backup repo (`odarambmenezes/odyssey`) set up via Claude Code (OAuth device-flow, no token handled in chat). First sync: Codex, Playbook, GM Charter, README. Fallback rule drafted for GM Charter. |

## 🤖 AI Governance

- Claude is the primary GM running Odyssey day-to-day.
- ChatGPT remains a complementary input for Side Quests/personal recommendations.
- Claude defers to what's documented in Codex/Backlog over its own assumptions.
- Any AI-proposed structural change gets logged in the Decision Log before being treated as final.

## 🅿️ Parking Lot (Ideas to Revisit Later)

- **Too many separate keywords/routine names** — no design yet, needs calm dedicated thought.
- **Automating the GitHub sync further** — currently manual (download zip → drag into Claude Code clone → commit/push). No GitHub connector available in claude.ai as of 2026-09-01; revisit if one becomes available in the connector directory.
- **`about-me.md`** (found already in the repo, pre-dating this sync) — arguably belongs in Notion as source of truth with this repo as its mirror too, matching the pattern for everything else. Not yet actioned — flagged 2026-09-01.

## 🔄 Review Cadence

Living system — reviewed together at least every six months, or sooner if something visibly breaks.

## 🧭 Scope Boundaries

- Odyssey is a **personal, single-player system**.
- The GitHub repo holds logic, prompts, and documentation only — **no personal task data ever gets committed**; that stays in the private Notion database.
- Odyssey optimizes for her reduced cognitive load and enjoyment.

## 🧱 Change Protocol

1. **Structural changes only happen in the Building Odyssey chat.**
2. Propose the change in conversation.
3. Log the decision + reasoning in the Decision Log above.
4. Update whichever page(s) the change actually affects.
5. If the change touches the live database schema, confirm before applying.
6. **(New, 2026-09-01)** If the change is structural/durable (not a one-off data fix), also regenerate the matching file(s) in this GitHub repo before considering the session's work "done" — keeps the backup from drifting too far out of sync.

## 🔐 Data & Privacy

- The Task Backlog (real obligations, routines, personal details) lives only in her private Notion workspace.
- The GitHub repo is documentation + code only, safe to be public.

## 🔀 Notion ↔ GitHub Fallback Rule *(new, 2026-09-01)*

For any chat or scheduled task that needs to read Odyssey documentation:

1. **Try the Notion link first.** It's still the source of truth and is usually more current.
2. **If the Notion link errors or is unreachable**, check this repo for the matching file (see the folder structure in the root [README](../README.md)).
3. **If neither Notion nor this repo has usable/current content**, do not invent or guess — surface the error clearly to Odara and ask how she'd like to proceed.
4. This repo is **not** live-synced — it only updates when a session in Building Odyssey explicitly regenerates and pushes the changed files. A file here may lag behind Notion; when in doubt and Notion *is* reachable, Notion wins.
