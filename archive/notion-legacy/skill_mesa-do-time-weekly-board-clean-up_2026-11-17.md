# 🧹 Mesa do Time — Weekly Board Clean-up (Skills Mapping row, exported and deleted 17 Nov 2026)

Properties: Status Archived · Type Scheduled Task · Access Open · Recurrency "Aposentada — era segundas, 07:23" · Trigger "Aposentada. Era horário: segundas às 07:23 (Europe/Madrid)." · Documentação: Crew Noticeboard page.
Mission: Keep the Crew Noticeboard readable: close expired FYI notes so the board only shows what still needs someone.
Use Cases: SUPERSEDED on 11 Nov 2026: expiry dates were removed from the Crew Noticeboard (rule is now unread limits: 3 days Critical, 5 Action Needed, 7 others). Replaced by the fortnightly Noticeboard Clean-up. The scheduled task was paused by Odara on 11 Nov 2026. Kept as history.

## What it does
Every Monday, Lore (Lori, The Keeper) checks the ⚓ Crew Noticeboard for notes with Tipo = FYI that are not ✅ Resolvido and whose Expira em date is today or earlier. Each one is set to ✅ Resolvido and gets a closing line appended to Resposta.

## Rules
- Owner: Lore. Approved by Odara on 11 Nov 2026.
- Validity: FYI notes last 14 days from the record date (Noite); the date goes in Expira em.
- Never deletes. Resolved notes leave the 📬 Abertos view but stay in the database.
- Does not touch: Handoff or Decisão notes, notes without a Tipo (older entries), or anything marked 🔴 Decisão da Odara.
- Silent: no push, no email, no messages; the run ends with a one-to-three line summary.

## Where it lived
- Protocol and live board: Mesa do Time page in 02 O Navio.
- Scheduled task: "🧹 Mesa do Time — limpeza semanal (Lore)", trigger trig_01PHhbemGXgAhGYeVA4aak3x, created on Claude (paused).
- First run: Monday 16 Nov 2026.
