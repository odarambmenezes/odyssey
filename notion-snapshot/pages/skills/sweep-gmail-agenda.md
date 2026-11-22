<!-- Read through the Notion connector on 2026-11-22T13:33Z (Builder session, v3). Canonical spec lives in Notion. Formerly gmail-sweep.md. Personal email address redacted. -->
<page url="https://app.notion.com/p/3fe107b19b4980a7a771d69a0746f355">
<ancestor-path>
<parent-data-source url="collection://3fe107b1-9b49-80fe-8401-000b3da753cf" name="Skills Mapping"/>
</ancestor-path>
<properties>
{"Access":"Sensitive","Integrations":["Gmail","Google Calendar"],"Mission":"One daily look at email and calendar: what Odara has today, what is new, what needs her, what she is waiting on, and a safe archive-only cleanup of low-value mail. Protects sensitive and transactional mail. Never sends, never deletes automatically.","Name":"Sweep (Gmail + Agenda)","Part of":["https://app.notion.com/p/415107b19b4981c89304d079c61d31f1"],"Recurrency":"On demand (also offered in Bom Dia). No schedule.","Referencia Interna":"22/11/2026 v3 (Builder): renamed from Gmail Sweep; reads Google Calendar (primary, Pessoal, Travel in full; Fortis busy only). Last real run stores date + time of the last completed sweep (What's New). Pilot: archive only, review 21/12/2026. No filters, no schedule. Pilot record in the Grab & Go task.","Status":"Active","Trigger":"Review (read-only): \"roda o Sweep\", \"vamos ver meu Gmail\", \"vamos ver minha agenda\", and the Bom Dia quick action. Cleanup: \"gmail sweep\", \"limpa meu Gmail\", \"organiza minha Inbox\". Ambiguous → Review. A direct calendar instruction does only that.","Type":"Skill","Use Cases":"Runs the Obligations Checar Emails and Responder Amigos / Famílias. Dashboard My Day / What's New / Needs Me / Waiting / Cleanup; drafts replies in Odara's Voice when asked; archives newsletters into Pré-Arquivo/30 dias; up to 3 events, passed to Bardim only on her word.","Last real run":"2026-11-22T13:30:00Z"}
</properties>
<content>
<callout icon="📬" color="purple_bg">
<b>SKILL · Sweep (Gmail + Agenda) · v3 pilot</b>

One daily look at email and calendar: what Odara has today, what is new, what needs her, what she is waiting on, and a safe cleanup of low-value mail. Decision-first and voice-friendly. Runs on demand and as a quick action offered in Bom Dia. Formerly "Gmail Sweep".
</callout>

<columns>
<column ratio="33">
<callout icon="👤" color="gray_bg">
<b>Used by</b>

Any agent. No owner, but Access Sensitive: it reads her inbox and calendar.
</callout>
</column>
<column ratio="33">
<callout icon="⚡" color="gray_bg">
<b>Trigger</b>

<b>Review</b> (read-only): "roda o Sweep", "vamos ver meu Gmail", "vamos ver minha agenda", and the Bom Dia quick action. <b>Cleanup</b>: "gmail sweep", "limpa meu Gmail", "organiza minha Inbox". Ambiguous → Review. A direct calendar instruction ("bloqueia uma hora amanhã") is not a sweep: do only that.
</callout>
</column>
<column ratio="33">
<callout icon="🚦" color="gray_bg">
<b>Status</b>

Active · pilot since 21/11/2026, review on 21/12/2026. Archive only: the sweep does not trash. No schedule, no Gmail filter, no automatic deletion, never sends.
</callout>
</column>
</columns>

| Overview |  |
| --- | --- |
| Type | Skill |
| Part of | Bom Dia Claude (quick action: offered, not executed). In the Bom Dia rebuild, its Agenda step should reuse this skill's My Day instead of a second calendar read. |
| Access | <b>Sensitive (G22)</b>: reads her inbox and calendar |
| Recurrency | On demand. A scheduled run needs a separate approval. |
| Sources of truth | Gmail for messages. Google Calendar for confirmed events and time blocks. Existing tasks: Task Backlog <code>collection://a4f2dc93-71ae-44c6-8049-b2cd8f752220</code>. Travel events: <mention url="https://app.notion.com/p/403107b19b49816b9c61e1d080ff5a4e">Regras do Odyssey Travel Calendar</mention>. Reply tone: <mention url="https://app.notion.com/p/3fe107b19b498044b5edfba6128ba15a">Odara's Voice</mention>. |
| Connectors | Gmail ✅ (read, labels, archive, drafts) · Google Calendar ✅ (read; create only on direct request) · WhatsApp ❌ (test pending in Grab & Go) · Outlook ❌ |
| Delivery | A short dashboard, then only real decisions, one question at a time if needed. Drafts saved in Gmail. Sending is always hers. |
| Last test | 22/11/2026: Review run, Gmail + Calendar (see the pilot task in Grab & Go). |

<callout icon="📅" color="blue_bg">
## Calendars read
</callout>

| Calendar | How |
| --- | --- |
| Primary ([redacted]) · Odara (Pessoal) · Odyssey Travel Calendar | In full. |
| Odara Menezes \[Fortis\] | Busy blocks only, no titles or details. |
| Família · Holidays in Brazil | Only when relevant to today or a decision. |

<callout icon="🧭" color="blue_bg">
## The dashboard
</callout>

1. <b>My Day:</b> today's confirmed events and time blocks from the calendars above. Tomorrow only if something needs preparing.
2. <b>What's New:</b> emails received since the last <b>completed</b> sweep (read or unread). The time of the last completed sweep is the skill's <b>Last real run</b> (date + time).
3. <b>Needs Me:</b> verified open decisions or actions, 🔺 first: immigration / legal / tax in Spain, employment, housing, finance and billing, healthcare, deadlines.
4. <b>Waiting:</b> threads labelled ⏳ Waiting.
5. <b>Cleanup:</b> what was archived (Cleanup mode) or could be (Review mode).
6. <b>Events worth a look:</b> at most 3, with the real event or artist name and one line on why.

Keep it short and scannable; analysis happens behind the scenes. If a decision is needed, ask one specific question she can answer by voice.

<callout icon="🏷️" color="blue_bg">
## Label architecture
</callout>

Retention and category are independent. A thread can have <b>at most one retention label</b> and <b>one or more category labels</b>.

| Kind | Gmail label | Meaning |
| --- | --- | --- |
| Retention | <code>Pré-Arquivo/30 dias</code> (nested under <code>Pré-Arquivo</code>) | Temporary information, out of the inbox, still searchable. Clock starts at the email's received date. Nothing is deleted by age during the pilot (see Retention policy). |
| Category | <code>Pinterest</code> | Pinterest recommendation and inspiration emails. Kept for future visual/design work. No need to read each one. |
| Category | <code>Eventos</code> | Promotional newsletters from Fever, Ticketmaster and other event providers. |
| Category | <code>Profissional</code> | Professional newsletters, AI updates, career content. |
| Category (protected) | <code>🧾 Comprovantes</code> | Receipts, tickets and proof of payment. Never retention, never Trash. |
| Category (protected) | <code>💼 Carreira</code> | Job applications, employers, work accounts, career documents. Never retention, never Trash. Career <i>newsletters</i> go to Profissional. |
| Status | <code>🔥 Action Needed</code> | She must act. Stays in the inbox. |
| Status | <code>⏳ Waiting</code> | Waiting on someone else. Stays in the inbox during the pilot. |

- New retention periods are siblings under <code>Pré-Arquivo/</code>. New labels need Odara's yes.
- Existing labels (RADAR, Newsletters, Spain Housing 2026, Compras, ✈️ Spain, etc.) are left as they are; never removed or renamed during a sweep.
- Never add a retention label to a thread that needs action, and never treat a thread as disposable just because the sender is promotional.

<callout icon="🛡️" color="red_bg">
<b>Protected: never temporary-retained, archived by the sweep, or deleted</b>

Immigration, visa, residence, consular · employment, termination, legal · banking, billing, important financial records · healthcare · housing agreements and administrative documents · tickets, reservations, receipts, purchase confirmations, event changes, cancellations, refunds · anything that needs a reply or decision · anything whose importance is uncertain · explicit exclusions until Odara releases them: <b>DiR Tuset / Santander</b>. <b>Uncertain stays in the inbox.</b> Never infer that a bill was paid, an account secured or a government notice resolved.
</callout>

<callout icon="🪜" color="blue_bg">
## Steps
</callout>

1. <b>Pick the mode.</b> Review reads Gmail and Calendar, builds the dashboard and changes nothing. Cleanup does the same plus step 7. Once Odara starts a Cleanup, finish without asking "continue?".
2. <b>Read the calendar</b> for My Day (calendars table above).
3. <b>Read Gmail:</b> inbox, plus everything received since Last real run.
4. <b>Protect first.</b> Anything on the protected list stays in the inbox, whatever the sender.
5. <b>Classify:</b> action needed · waiting · reply needed · receipt · career · informational · Pinterest · Eventos · Profissional · uncertain.
6. <b>Reconcile before proposing.</b> Look in the Task Backlog for an existing item; propose, don't create, unless she asks. Email opportunities are suggestions, not events: check the calendar for duplicates and conflicts before proposing one. If Odara says something is resolved, stop treating it as pending: remove 🔥 Action Needed and archive it (Cleanup), and check the related task; never assume later mail from that sender is resolved.
7. <b>Clean up (Cleanup mode only).</b> Eligible threads get one category label + <code>Pré-Arquivo/30 dias</code> and leave the inbox. Receipts get 🧾 Comprovantes, career mail 💼 Carreira. Do not mark as read unless she asks. <b>No Trash during the pilot</b> unless she asks for a specific batch.
8. <b>Drafts.</b> If she dictates or asks for a reply, save a Gmail draft using Odara's Voice and say "usei seu Perfil de Voz". <b>Never send.</b>
9. <b>Events.</b> Show at most 3 genuinely relevant events. Only when she says so ("manda pro Bard"): add them to one open Noticeboard note To Bardim (update it if it exists), with source reference and rationale, no email content. Radar de Shows stays independent. No ticket purchase, no calendar booking.
10. <b>Finish.</b> One reconciled summary: verified changes, open matters, decisions waiting for her, notes actually posted. Never invent a next action. Set <b>Last real run</b> to now (date + time). During the pilot, append a counts-only line to the pilot record.

<callout icon="⏳" color="yellow_bg">
<b>Retention policy</b>

<b>Pilot (now, until the review on 21/12/2026):</b> archive only. Eligible mail gets its category + <code>Pré-Arquivo/30 dias</code> and leaves the inbox. The sweep never trashes and nothing is deleted by age. Trash only when Odara asks for a specific batch. Keep an auditable record (counts and thread references, not content).

<b>Target rule (to be tested at the review, not active):</b> two lanes.

1. <b>Archive and review:</b> the default. Mail stays archived with the retention label; after 60 days Odara reviews it by hand before anything is deleted, as an importance filter.
2. <b>Straight to Trash:</b> only for categories or senders Odara puts on an approved list. Gmail deletes Trash for good after 30 days, which is the safety margin. Never protected classes.

At the review, Odara decides the Trash list and the retention period (the label name follows the decision). Changing the policy never deletes already-labelled mail retroactively.
</callout>

<callout icon="🔐" color="purple_bg">
## Approvals and limits
</callout>

<columns>
<column ratio="33">
<callout icon="🟢" color="green_bg">
<b>Inside a sweep she started</b>

Read Gmail and the calendars above, classify, check tasks. In Cleanup: apply approved labels and archive eligible, non-protected threads. Save a draft she dictated. Update Last real run. Create one calendar event she asked for directly (G21 level 2).
</callout>
</column>
<column ratio="33">
<callout icon="🟡" color="yellow_bg">
<b>Needs her yes</b>

Trash or delete anything (each batch). New labels, filters or rules. Marking as read in bulk. Creating Backlog tasks. Posting to Bardim. Proposing a calendar event found in email. Changing the retention period. A scheduled run.
</callout>
</column>
<column ratio="33">
<callout icon="🔴" color="red_bg">
<b>Never</b>

Send, forward or reply. Automatic deletion. Editing or deleting existing calendar events without a direct request. Summarize a thread that was not actually read. Copy email content into the Crew Noticeboard or any shared page (G22). Fortis event details.
</callout>
</column>
</columns>

<callout icon="🛟" color="blue_bg">
## When it fails
</callout>

If Gmail or Calendar does not answer, or an action needs in-app approval that was not given: say so in one line, show the other source anyway, and continue. Never invent a summary or an event. Scheduled runs have failed before with error 400.

<callout icon="🚫" color="blue_bg">
## What it does NOT do
</callout>

- Send anything. Ever.
- WhatsApp or Instagram (WhatsApp Business read-only test is a Grab & Go task).
- Create Gmail filters or automatic rules.
- Run on a schedule.
- Close Backlog Obligations on its own (that is the skill Marca como feito).
- Replace Radar de Shows or book events.

<callout icon="🧪" color="blue_bg">
## Acceptance tests
</callout>

- [x] Labels exist once each, retention nested under <code>Pré-Arquivo</code> (21/11/2026).
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

<callout icon="📜" color="blue_bg">
## Status and decision log
</callout>

| Date | Decision | Why |
| --- | --- | --- |
| 28/07/2026 | First real workflow; Gmail tested OK. | Checar Emails and Responder Amigos were daily Obligations with no execution. |
| 11/11/2026 | Back from Paused to Active; Trigger field filled. | Test OK on record and Bom Dia kept the quick action. |
| 21/11/2026 | v2: retention and category labels; no automatic deletion; on demand only. | Approved by Odara (Designer handoff). |
| 21/11/2026 | v2.1: Review / Cleanup modes, one report, status labels, 🧾 Comprovantes and 💼 Carreira protected, DiR Tuset / Santander excluded. Pilot = archive only, review 21/12/2026. | Odara, live with the Builder, after her chat pilot. |
| 22/11/2026 | v3: renamed Sweep (Gmail + Agenda); reads Google Calendar; dashboard My Day / What's New / Needs Me / Waiting / Cleanup; resolution reconciliation; events to Bardim only on her word, one rolling note. | Odara + Chatty experience design, Builder review; Odara approved the three decisions. |

<callout icon="🔗" color="gray_bg">
<b>Registry</b>

- [x] Same Skills Mapping row as the former Gmail Sweep (relations kept).
- [x] This page is the single canonical spec. The Bom Dia quick action row points here. The Morning Message Sweep (v1) is historical, marked \[ARCHIVE\], not an instruction.
- [x] Part of linked to Bom Dia Claude.
- [x] Used by empty: open to any agent, Access Sensitive.
</callout>
</content>
</page>
