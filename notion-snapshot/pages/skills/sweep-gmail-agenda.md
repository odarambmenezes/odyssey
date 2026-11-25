<!-- Read through the Notion connector on 2026-11-25T21:40Z (Builder session, output contract confirmed). Canonical spec lives in Notion. Formerly gmail-sweep.md. Personal email addresses redacted. -->
<page url="https://app.notion.com/p/3fe107b19b4980a7a771d69a0746f355">
<ancestor-path>
<parent-data-source url="collection://3fe107b1-9b49-80fe-8401-000b3da753cf" name="Skills Mapping"/>
</ancestor-path>
<properties>
{"Access":"Sensitive","Integrations":["Gmail","Google Calendar","Outlook"],"Mission":"One daily look at email and calendar: what Odara has today, what is new, what needs her, what she is waiting on, and a safe archive-only cleanup of low-value mail. Protects sensitive and transactional mail. Never sends, never deletes automatically.","Name":"Sweep (Gmail + Agenda)","Part of":["https://app.notion.com/p/415107b19b4981c89304d079c61d31f1"],"Recurrency":"On demand (also offered in Bom Dia). No schedule.","Referencia Interna":"22/11/2026 v3 (Builder): renamed from Gmail Sweep; reads Google Calendar (primary, Pessoal, Travel in full; Fortis busy only). Last real run stores date + time of the last completed sweep (What's New). Pilot: archive only, review 21/12/2026. No filters, no schedule. Pilot record in the Grab & Go task. 23/11/2026: Hotmail added as a second mailbox with its own rules (section Hotmail).","Status":"Active","Trigger":"Review (read-only): \"roda o Sweep\", \"vamos ver meu Gmail\", \"vamos ver minha agenda\", and the Bom Dia quick action. Cleanup: \"gmail sweep\", \"limpa meu Gmail\", \"organiza minha Inbox\". Hotmail only when named: \"limpa meu Hotmail\", \"roda o Sweep no Hotmail\". Ambiguous → Review. A direct calendar instruction does only that.","Type":"Skill","Use Cases":"Runs the Obligations Checar Emails and Responder Amigos / Famílias. Dashboard My Day / What's New / Needs Me / Waiting / Cleanup; drafts replies in Odara's Voice when asked; archives newsletters into Pré-Arquivo/30 dias; up to 3 events, passed to Bardim only on her word.","Last real run":"2026-11-24T12:25:00Z"}
</properties>
<content>
<callout icon="📬" color="purple_bg">
<b>SKILL · Sweep (Gmail + Agenda) · v3 pilot</b>

One daily look at email and calendar: what Odara has today, what is new, what needs her, what she is waiting on, and a safe cleanup of low-value mail. Decision-first and voice-friendly. Runs on demand and as a quick action offered in Bom Dia. Formerly "Gmail Sweep".
</callout>

**Used by:** any agent. No owner, but Access Sensitive: it reads her inbox and calendar.

**Trigger:** **Review** (read-only): "roda o Sweep", "vamos ver meu Gmail", "vamos ver minha agenda", and the Bom Dia quick action. **Cleanup**: "gmail sweep", "limpa meu Gmail", "organiza minha Inbox". Ambiguous → Review. A direct calendar instruction ("bloqueia uma hora amanhã") is not a sweep: do only that.

**Status:** Active · pilot since 21/11/2026, review on 21/12/2026. Archive only: the sweep does not trash. No schedule, no Gmail filter, no automatic deletion, never sends.

| Overview | |
| --- | --- |
| Type | Skill |
| Part of | Bom Dia Claude (quick action: offered, not executed). In the Bom Dia rebuild, its Agenda step should reuse this skill's My Day instead of a second calendar read. |
| Access | **Sensitive (G22)**: reads her inbox and calendar |
| Recurrency | On demand. A scheduled run needs a separate approval. |
| Sources of truth | Gmail for messages. Google Calendar for confirmed events and time blocks. Existing tasks: Task Backlog `collection://a4f2dc93-71ae-44c6-8049-b2cd8f752220`. Travel events: Regras do Odyssey Travel Calendar. Reply tone: Odara's Voice. |
| Connectors | Gmail ✅ (read, labels, archive, drafts) · Google Calendar ✅ (read; create only on direct request) · Outlook / Hotmail ✅ (read, move to folder, trash; connected 23/11/2026, see the Hotmail section) · WhatsApp ❌ (test pending in Grab & Go) |
| Delivery | The five-section command panel: Calendar (Today / This Week) · Gmail metrics · Cleanup · Needs Me · Radar. Meaningful visual symbols follow Odyssey Visual Language v1. Drafts are proposed inline when useful; Gmail drafts are saved only on explicit request, never sent. |
| Last test | 22/11/2026: Review run, Gmail + Calendar (see the pilot task in Grab & Go). |

## Calendars read

| Calendar | How |
| --- | --- |
| Primary ([redacted]) · Odara (Pessoal) · Odyssey Travel Calendar | In full. |
| 🪶 Tarefas · 🔺 Prazos · 🔁 Rotinas (main account, created 24/11/2026) | In full. See "Task calendars" below. |
| Odara Menezes [Fortis] | Busy blocks only, no titles or details. |
| Família · Holidays in Brazil | Only when relevant to today or a decision. |

## Task calendars

Since 24/11/2026 tasks also live in Google Calendar, in three calendars of the main account that Odara can switch on and off. **Gibbs owns them** (review at the retreat). The Backlog stays the record of done / not done; the calendar says when she plans to do it.

| Calendar | What goes in | Form | Window |
| --- | --- | --- | --- |
| 🪶 Tarefas | Flexible tasks from the Backlog with a suggested slot | Timed block, 15–60 min, Backlog link in the description | Next 7 days only, refilled weekly |
| 🔺 Prazos | Hard dates: renewals, government deadlines, bills | All-day, free, reminder days before | Current month + the few big hard dates ahead |
| 🔁 Rotinas | Recurring Backlog routines | All-day recurring, free, no reminder; monthly ones spread two per weekend | Recurring |

- **Reminders and task blocks are flexible:** mark them free so other things can go on top, and never place them early in the morning (from about 13:00 on, unless Odara picks a time). Odara, 25/11/2026.
- Appointments with other people stay in the primary calendar; personal fixed appointments and birthdays stay in Odara (Pessoal).
- **Done = ✅ at the start of the title.** When Odara says a calendar task or routine is done, add "✅ " to that event (for a recurring routine, only that occurrence) and update the Backlog row (Marca como feito). Never delete a done event.
- A flexible task whose time passed without ✅ is **not** lost: the sweep lists it under Needs Me ("ficou para trás") with a new slot to propose.

## Notes to self (🤌🏻 Eu comiga mesma! +Odyssey)

Odara captures ideas at night by email. Address: [redacted]+odyssey (Gmail plus addressing; same inbox). Her Gmail filter labels these `🤌🏻 Eu comiga mesma! +Odyssey` (she creates the filter). Optional subject tags: `#tarefa`, `#ideia`, `#retiro`, `#hacker`, `#compra`.

- Each run reads `label:🤌🏻 Eu comiga mesma! +Odyssey` plus `from:me to:me in:inbox` since Last real run.
- Output block **🗒️ Suas notas**, right after the day's priorities: one line per note with a proposed home (Backlog / 🪶 Tarefas block, Grab & Go, a Persona's Noticeboard) and a reply code (N1, N2…).
- On her code: register it, then archive the note. Never route without her code.

## The dashboard

**Output contract · approved by Odara, 23/11/2026; confirmed final 25/11/2026**

Produce an **operational command panel**, never a generic chronological digest. Use exactly the five main sections below, in this order. No empty noise: omit empty rows, irrelevant notes, needless caveats and filler. If no new decisions exist, say so in one brief line under Needs Me. Keep substance in a small number of high-signal items, and make the result easy to scan on mobile. The visual code is semantic, not decoration.

### Odyssey Visual Language v1 (shared vocabulary)

| Symbol | Fixed meaning | Applies to |
| --- | --- | --- |
| 📌 | Fixed event / non-flexible time | Calendar |
| 🪶 | Flexible block / can be rescheduled | Calendar |
| 🔺 | High priority | Any section |
| 👀 | Pending with others / awaiting an external response | Gmail, calendar, task radar |
| 🫵 | Action needed from Odara | Decisions and tasks |
| ⛔ | Blocked by a dependency | Any section |
| 🆕 | New item or discovery | Email and radar |

Use one symbol for one meaning; combine only when useful (for example 🪶🔺🫵). Do not use 🔒 for fixed time, 🔥 as the visual priority symbol, ⏳ for pending, or ✨ for new discoveries in the rendered dashboard: those represent different or legacy conventions. Existing Gmail labels (including 🔥 Action Needed and ⏳ Waiting) are **not renamed**: map their meaning to visual markers in the output. Show the legend compactly when helpful, not a long explanation every run.

### 1. 📅 Calendar

**Calendar — Today:** make the section heading a clickable link to Odara's preferred Google Calendar **week view**, even when showing only today's events: `[Calendar — Today](https://calendar.google.com/calendar/u/0/r/week?utm_source=chatgpt.com)`. Show a compact table with `Time | Event | Flexibility | Comments`. Full calendar titles only on permitted calendars; Fortis remains busy/free only. Use 📌 for a genuinely fixed appointment, 🪶 for a movable work block, and 🔺 for independently important items; mark inferred flexibility clearly when uncertain. Comments are empty by default: fill only when verified preparation, dependencies, an actual conflict, or a concise recommendation changes Odara's action. A time block is not proof a task was completed. Do not silently drop real busy blocks if they affect the day's availability.

**Calendar — This Week:** make the section heading a clickable link to the exact same preferred Google Calendar week view: `[Calendar — This Week](https://calendar.google.com/calendar/u/0/r/week?utm_source=chatgpt.com)`. Give only a few short bullets for hard dates, critical commitments, meaningful conflicts, preparations, or the next day when relevant. Check all permitted calendars; no week-long event dump. Mention a fixed event whose subject is not accessible as a busy block, never speculate about its title.

### 2. 📬 Gmail

**Strict layout: one compact inline dashboard, never a two-column "Indicator / Result" table, never six stacked mini-tables or a verbose metrics report.**

Example layout (illustrative counts only):

`📥 Inbox **28 / 35** · 👀 Pending **28** · 🆕 New **22** · 🫵 Action Needed **15**`

Exactly these four indicators, in this order. If the rendering width requires a break, keep the same inline, short format rather than creating a tall table. No separate Unread, Waiting, New Threads or Pending-real indicator. **Do not print methodology, timestamp baseline, technical distinctions or explanatory footnotes under the metrics.** Compute accurately behind the scenes:

- **Inbox:** unread / total Inbox messages, as a concise slash-separated pair.
- **Pending:** actual unresolved matters when verified; never equate unread with pending. If not reliably measurable, display `—` without commentary.
- **🆕 New:** message count since the previous completed sweep's Last real run; include read and auto-archived mail. Keep thread deduplication internal unless the user needs it for a decision.
- **🫵 Action Needed:** current existing Gmail Action Needed label count (threads), mapped to the visual code without modifying the label.

In this section, visual brevity takes precedence over displaying all available statistics. Detailed diagnosis belongs in Needs Me only if it is actionable.

### 3. 🧹 Cleanup

**Strict layout: short bullet points, never a table.** This is an activity log of actual work, not a catalogue of all possible cleanup. Put completed operations first, with counts and concise sender / category examples only when useful.

Example format (illustrative, not a claim of execution):

- `**Archived 5 newsletters:** Pinterest (2), Fever (2), professional newsletter (1).`
- `**Labeled 3:** Pinterest → category + Pré-Arquivo/30 dias.`
- `**Moved to Trash 0:** not authorized in this pilot.`
- `**Recommended, not done:** review one older transport alert.`

Do **not** mechanically create bullets for every action type with a zero count. If Review mode made no changes, use a **single short bullet**: `**No changes — Review mode.**` Add at most one or two high-value recommendations, also in bullets. Separate actual execution from recommendations, but avoid extra subtables, audit commentary and elaborate safety narratives in the output.

Only recommend or perform cleanup inside the currently authorized Review/Cleanup scope. Never imply a security alert, receipt, legal message or financial record was archived without checking it is safe and permitted; no blanket 30-day archive for unresolved security notices. The pilot remains **archive only**; no Trash without specific approval.

### 4. 🫵 Needs Me

Lead with the **number of truly new conversations needing Odara's decision** (or `No new decisions`). Cover only verified decisions and genuine follow-ups, prioritizing legal status in Spain and other hard consequences. Each item has:

- **Clickable title linking directly to the real Gmail thread** (obtain provider thread ID; never invent a URL), optionally 🆕 / 🔺 / 🫵.
- One- or two-sentence context grounded in the actual thread, not just a snippet if the answer depends on nuance.
- **Recommendation**: answer / wait / investigate / resolve / bring to another Persona, with a practical reason.
- **DRAFT** in full, inline, only when the next move is Odara's; none when the next move belongs to someone else (waiting items go to Radar, without a draft). Show a ready-to-use proposal in Odara's Voice. Do not pretend the draft was saved in Gmail. Saving a Gmail draft follows the existing explicit-request rule; sending always requires separate consent.

Distinguish an item merely labeled Action Needed from an item truly needing Odara now. Avoid reintroducing resolved conversations; consult recent thread history and existing tasks before suggesting duplicate work. Ask at most one specific, decision-enabling question when needed.

### 5. 👀 Radar

Short bullets for genuine external waits, blocked dependencies (⛔), approaching important hard dates, and at most three relevant discoveries (🆕). An event discovery includes the real event name, date/time and a one-line reason; recommend Bardim handoff only where useful and **send no Noticeboard note without Odara's instruction**. Do not duplicate the full Needs Me section or reproduce a newsletter.

**Global rendering rules:** Prioritize signal over uniform fullness. Blank Comments cells are fine; do not add "—" everywhere for decoration. No empty section padding. Never claim that a proposed operation or draft actually happened. Confirm verified changes and sources; protected content stays inside the authorized connector. The output is one coherent dashboard, not a collection of progress reports.

## Label architecture

Retention and category are independent. A thread can have **at most one retention label** and **one or more category labels**.

| Kind | Gmail label | Meaning |
| --- | --- | --- |
| Retention | `Pré-Arquivo/30 dias` (nested under `Pré-Arquivo`) | Temporary information, out of the inbox, still searchable. Clock starts at the email's received date. Nothing is deleted by age during the pilot (see Retention policy). |
| Category | `Pinterest` | Pinterest recommendation and inspiration emails. Kept for future visual/design work. No need to read each one. |
| Category | `Eventos` | Promotional newsletters from Fever, Ticketmaster and other event providers. |
| Category | `Profissional` | Professional newsletters, AI updates, career content. |
| Category (protected) | `🧾 Comprovantes` | Receipts, tickets and proof of payment. Never retention, never Trash. |
| Category (protected) | `💼 Carreira` | Job applications, employers, work accounts, career documents. Never retention, never Trash. Career *newsletters* go to Profissional. |
| Status | `🔥 Action Needed` | She must act. Stays in the inbox. |
| Status | `⏳ Waiting` | Waiting on someone else. Stays in the inbox during the pilot. |

- New retention periods are siblings under `Pré-Arquivo/`. New labels need Odara's yes.
- Existing labels (RADAR, Newsletters, Spain Housing 2026, Compras, ✈️ Spain, etc.) are left as they are; never removed or renamed during a sweep.
- Housing alerts (Idealista, Habitaclia, Fotocasa) already arrive labelled `Spain Housing 2026` and out of the inbox through an existing Gmail filter set up by Odara (verified 22/11/2026). The sweep counts them in What's New, gives no retention label and does not touch the filter. Messages from landlords or agencies are housing correspondence and stay protected.
- Never add a retention label to a thread that needs action, and never treat a thread as disposable just because the sender is promotional.

**Protected: never temporary-retained, archived by the sweep, or deleted.** Immigration, visa, residence, consular · employment, termination, legal · banking, billing, important financial records · healthcare · housing agreements and administrative documents · tickets, reservations, receipts, purchase confirmations, event changes, cancellations, refunds · anything that needs a reply or decision · anything whose importance is uncertain · explicit exclusions until Odara releases them: **DiR Tuset / Santander**. **Uncertain stays in the inbox.** Never infer that a bill was paid, an account secured or a government notice resolved.

## Hotmail (Brazil life archive)

Hotmail is a second mailbox with its own rules, set by Odara on 23/11/2026. What it holds and who may read it: Hotmail — Brazil Life Archive (Notion). A Hotmail sweep runs only when she asks for it ("limpa meu Hotmail", "roda o Sweep no Hotmail"); the Gmail sweep does not touch Hotmail.

| Class | Hotmail rule |
| --- | --- |
| Promotions, newsletters, job alerts | Trash, and the sender goes on an unsubscribe list for Odara (she unsubscribes herself, G23). |
| LinkedIn | Trash for now; Gibbs follows LinkedIn from early 2027. |
| Delivery, food and ride receipts under 50 € / R$ 100, other day-to-day receipts | Trash. |
| Significant purchases worth a future check | Folder `Recibos`. |
| Evidence for an open dispute | A named folder (today `Santander - Negocia`) until it closes. |
| Notices she already knows, with no action for anyone | Trash. No Archive: she chose not to use Outlook's Archive folder. |
| Needs an action from her | Stays in the inbox. |

Trash is allowed in Hotmail, unlike the Gmail pilot, but only for these classes and only in a sweep she started; the first batch of each new sender type is shown to her before it goes. The protected list applies to Hotmail as well: when in doubt, it stays in the inbox and she is asked.

## Steps

1. **Pick the mode.** Review reads Gmail and Calendar, builds the five-section output-contract dashboard and changes nothing. Cleanup does the same plus step 7. Once Odara starts a Cleanup, finish without asking "continue?".
2. **Read the calendar** for My Day (calendars table above).
3. **Read Gmail:** inbox, plus everything received since Last real run.
4. **Protect first.** Anything on the protected list stays in the inbox, whatever the sender.
5. **Classify:** action needed · waiting · reply needed · receipt · career · informational · Pinterest · Eventos · Profissional · uncertain.
6. **Reconcile before proposing.** Look in the Task Backlog for an existing item; propose, don't create, unless she asks. Email opportunities are suggestions, not events: check the calendar for duplicates and conflicts before proposing one. If Odara says something is resolved, stop treating it as pending: remove 🔥 Action Needed and archive it (Cleanup), and check the related task; never assume later mail from that sender is resolved.
7. **Clean up (Cleanup mode only).** Eligible threads get one category label + `Pré-Arquivo/30 dias` and leave the inbox. Receipts get 🧾 Comprovantes, career mail 💼 Carreira. Unread means only new mail Odara has not seen yet (Odara, 24/11/2026). Mark archived threads as read, and also any thread already shown to her in a sweep report (Needs Me, Radar / ⏳ Waiting, 🔥 Action Needed): waiting items stay in the inbox or label, read. **No Trash during the pilot** unless she asks for a specific batch.
8. **Drafts.** If she dictates or asks for a reply, save a Gmail draft using Odara's Voice and say "usei seu Perfil de Voz". **Never send.**
9. **Events.** Show at most 3 genuinely relevant events. Only when she says so ("manda pro Bard"): add them to one open Noticeboard note To Bardim (update it if it exists), with source reference and rationale, no email content. Radar de Shows stays independent. No ticket purchase, no calendar booking.
10. **Finish.** One reconciled five-section dashboard per the Output contract: verified changes, real decisions, waiting items and notes actually posted. No empty noise and no invented actions. Set **Last real run** to now (date + time) only after successful completion. During the pilot, append a counts-only line to the pilot record.

## Retention policy

**Pilot (now, until the review on 21/12/2026):** archive only. Eligible mail gets its category + `Pré-Arquivo/30 dias` and leaves the inbox. The sweep never trashes and nothing is deleted by age. Trash only when Odara asks for a specific batch. Keep an auditable record (counts and thread references, not content).

**Target rule (to be tested at the review, not active):** two lanes.

1. **Archive and review:** the default. Mail stays archived with the retention label; after 60 days Odara reviews it by hand before anything is deleted, as an importance filter.
2. **Straight to Trash:** only for categories or senders Odara puts on an approved list. Gmail deletes Trash for good after 30 days, which is the safety margin. Never protected classes.

At the review, Odara decides the Trash list and the retention period (the label name follows the decision). Changing the policy never deletes already-labelled mail retroactively.

## Approvals and limits

- **Inside a sweep she started:** read Gmail and the calendars above, classify, check tasks. In Cleanup: apply approved labels and archive eligible, non-protected threads. Save a draft she dictated. Update Last real run. Create one calendar event she asked for directly (G21 level 2).
- **Needs her yes:** Trash or delete anything (each batch). New labels, filters or rules. Marking as read in bulk. Creating Backlog tasks. Posting to Bardim. Proposing a calendar event found in email. Changing the retention period. A scheduled run.
- **Never:** send, forward or reply. Automatic deletion. Editing or deleting existing calendar events without a direct request. Summarize a thread that was not actually read. Copy email content into the Crew Noticeboard or any shared page (G22). Fortis event details.

## When it fails

If Gmail or Calendar does not answer, or an action needs in-app approval that was not given: say so in one line, show the other source anyway, and continue. Never invent a summary or an event. Scheduled runs have failed before with error 400.

## What it does NOT do

- Send anything. Ever.
- WhatsApp or Instagram (WhatsApp Business read-only test is a Grab & Go task).
- Create Gmail filters or automatic rules.
- Run on a schedule.
- Close Backlog Obligations on its own (that is the skill Marca como feito).
- Replace Radar de Shows or book events.

## Acceptance tests

- [x] Labels exist once each, retention nested under `Pré-Arquivo` (21/11/2026).
- [x] Newsletter sample: category + retention, out of the inbox, still searchable (21/11/2026).
- [x] Tickets, purchase confirmations and uncertain threads stay in the inbox untouched (21/11/2026).
- [x] First Cleanup run: protected list untouched, nothing trashed, nothing sent (21/11/2026).
- [x] Review run reads Gmail + Calendar and changes nothing (22/11/2026: 4 calendars, 27 new emails, 0 Gmail changes).
- [ ] What's New starts from the last completed run.
- [x] Fortis shows only busy blocks (22/11/2026: the connector itself returns free/busy only).
- [ ] A resolved item does not come back in the next run.
- [ ] A direct calendar instruction creates only that event.
- [ ] "Manda pro Bard": one rolling note, no duplicates, no email content.
- [ ] Dictated reply saved as a draft with "usei seu Perfil de Voz".

## Status and decision log

| Date | Decision | Why |
| --- | --- | --- |
| 28/07/2026 | First real workflow; Gmail tested OK. | Checar Emails and Responder Amigos were daily Obligations with no execution. |
| 11/11/2026 | Back from Paused to Active; Trigger field filled. | Test OK on record and Bom Dia kept the quick action. |
| 21/11/2026 | v2: retention and category labels; no automatic deletion; on demand only. | Approved by Odara (Designer handoff). |
| 21/11/2026 | v2.1: Review / Cleanup modes, one report, status labels, 🧾 Comprovantes and 💼 Carreira protected, DiR Tuset / Santander excluded. Pilot = archive only, review 21/12/2026. | Odara, live with the Builder, after her chat pilot. |
| 24/11/2026 | Task calendars (🪶 Tarefas, 🔺 Prazos, 🔁 Rotinas; Gibbs owns), ✅ done convention, 🤌🏻 Eu comiga mesma! +Odyssey capture via +odyssey. Output v4 layout in progress with Odara (Google Doc). | Odara, live with the Builder. |
| 24/11/2026 | Unread = only new, unseen mail. Archived threads and anything already shown in a report (Radar, Waiting, Action Needed) are marked read. | Odara, live with the Builder. |
| 23/11/2026 | Hotmail added as a second mailbox with its own rules (Trash allowed for approved classes, Recibos folder, inbox = actions only). | Odara, live with the Builder, after the first Hotmail clean-up. |
| 25/11/2026 | Output contract confirmed as final after the chat consolidation (HANDOFF 01, 06, 07): heading 🫵 Needs Me (Visual Language v1, replaces 🔺), 👀 Radar; full inline drafts only when the next move is hers, none when waiting on others. Pending shows — when not verifiable. | Odara, live with the Builder. |
| 22/11/2026 | v3: renamed Sweep (Gmail + Agenda); reads Google Calendar; dashboard My Day / What's New / Needs Me / Waiting / Cleanup; resolution reconciliation; events to Bardim only on her word, one rolling note. | Odara + Chatty experience design, Builder review; Odara approved the three decisions. |

**Registry**

- [x] Same Skills Mapping row as the former Gmail Sweep (relations kept).
- [x] This page is the single canonical spec. The Bom Dia quick action row points here. The Morning Message Sweep (v1) is historical, marked [ARCHIVE], not an instruction.
- [x] Part of linked to Bom Dia Claude.
- [x] Used by empty: open to any agent, Access Sensitive.
</content>
</page>
