<!-- Read through the Notion connector on 2026-11-21T12:57Z (Builder session). Canonical spec lives in Notion. -->
<page url="https://app.notion.com/p/3fe107b19b4980a7a771d69a0746f355">
<ancestor-path>
<parent-data-source url="collection://3fe107b1-9b49-80fe-8401-000b3da753cf" name="Skills Mapping"/>
</ancestor-path>
<properties>
{"Access":"Sensitive","Integrations":["Gmail"],"Mission":"Inbox triage and cleanup: keep the inbox focused on what needs Odara's attention, decision or action. Protects sensitive and transactional mail, labels low-value mail with independent retention and category labels and archives it (still searchable). Never sends, never deletes automatically.","Name":"Gmail Sweep","Part of":["https://app.notion.com/p/415107b19b4981c89304d079c61d31f1"],"Recurrency":"On demand (also offered in Bom Dia). No schedule.","Referencia Interna":"21/11/2026 v2 pilot (Builder): labels Pré-Arquivo/30 dias, Pinterest, Eventos, Profissional created in Gmail. Effective pilot safeguard 60 days; no automatic deletion; no Gmail filters; no schedule. Pilot record lives in the Grab & Go task 'Gmail Sweep v2 pilot'.","Status":"Active","Trigger":"\"gmail sweep\" or \"roda meu Morning Message Sweep\". Also a quick action offered (not executed) inside Bom Dia.","Type":"Skill","Use Cases":"Runs the Obligations Checar Emails and Responder Amigos / Famílias. Prioritizes immigration, employment, housing, finance, health and deadlines; drafts replies in Odara's Voice when asked; archives Pinterest / Eventos / Profissional newsletters into Pré-Arquivo/30 dias; highlights opportunities in one line. WhatsApp stays out.","Last real run":"2026-11-21"}
</properties>
<content>
<callout icon="📬" color="purple_bg">
<b>SKILL · Gmail Sweep (v2 · pilot)</b>

Inbox triage and cleanup: keep the inbox focused on what needs Odara's attention, decision or action. Low-value mail leaves the inbox with labels and stays searchable. Runs on demand and as a quick action offered in Bom Dia.
</callout>

<columns>
<column ratio="33">
<callout icon="👤" color="gray_bg">
<b>Used by</b>

Any agent. No owner, but Access Sensitive: it reads her inbox.
</callout>
</column>
<column ratio="33">
<callout icon="⚡" color="gray_bg">
<b>Trigger</b>

"gmail sweep" or "roda meu Morning Message Sweep". Also offered (never run on its own) as a quick action in Bom Dia Claude.
</callout>
</column>
<column ratio="33">
<callout icon="🚦" color="gray_bg">
<b>Status</b>

Active · v2 in <b>controlled pilot</b> since 21/11/2026. No schedule, no Gmail filter, no automatic deletion.
</callout>
</column>
</columns>

| Overview |  |
| --- | --- |
| Type | Skill |
| Part of | Bom Dia Claude (step 6, quick action: offered, not executed) |
| Access | <b>Sensitive (G22)</b>: reads her inbox |
| Recurrency | On demand. A daily scheduled run needs a separate approval. |
| Sources of truth | Gmail (connector). Existing tasks: Task Backlog <code>collection://a4f2dc93-71ae-44c6-8049-b2cd8f752220</code>. Reply tone: <mention url="https://app.notion.com/p/3fe107b19b498044b5edfba6128ba15a">Odara's Voice</mention>. |
| Connectors | Gmail ✅ (read, labels, archive, drafts) · WhatsApp ❌ · Outlook ❌ |
| Delivery | Short conversational batches, drafts saved in Gmail, a final report. Sending is always hers. |
| Last test | 21/11/2026: labels created, 6-thread pilot sample classified and archived (see the pilot task in Grab & Go). |

<callout icon="🎯" color="blue_bg">
## What it does
</callout>

1. Reviews inbox threads, unread first; read threads too when needed for cleanup.
2. Classifies each one: urgency, importance, required action, informational value.
3. Puts first: 🔺 immigration / legal status in Spain (estrangería, consulate, AEAT), employment, housing, finance and billing, healthcare, personal commitments and deadlines.
4. Checks existing Odyssey tasks before proposing a new one; never creates a task from a newsletter by default.
5. Spots threads that need a reply and prepares drafts in her voice when she asks.
6. Classifies newsletters and promotions into categories and temporary retention, and archives eligible ones.
7. Highlights opportunities in one line ("Found a jazz event in Barcelona that might interest you") without creating work.
8. Leaves anything uncertain in the inbox.
9. Reports what it did, what is still open and the exceptions.

<callout icon="🏷️" color="blue_bg">
## Label architecture
</callout>

Retention and category are independent. A thread can have <b>at most one retention label</b> and <b>one or more category labels</b>.

| Kind | Gmail label | Meaning |
| --- | --- | --- |
| Retention | <code>Pré-Arquivo/30 dias</code> (nested under <code>Pré-Arquivo</code>) | Temporary information, out of the inbox, still searchable. Clock starts at the email's received date. Pilot safeguard: treat as 60 days (see below). |
| Category | <code>Pinterest</code> | Pinterest recommendation and inspiration emails. Kept for future visual/design work; consulted when a visual project comes up. No need to read each one. |
| Category | <code>Eventos</code> | Promotional newsletters from Fever, Ticketmaster and other event providers. |
| Category | <code>Profissional</code> | Professional newsletters, AI updates, career content. |

- Future periods are siblings under <code>Pré-Arquivo/</code> (for example <code>Pré-Arquivo/15 dias</code>). Do not create them without Odara's approval.
- Existing labels (RADAR, Newsletters, 🔥 Action Needed, ⏳ Waiting, Spain Housing 2026, Compras, ✈️ Spain, etc.) are left as they are. Never remove or rename an existing label during a sweep. <code>Newsletters</code> overlaps the new categories; its future is an open decision.
- Never add a retention label to a thread that needs action, and never treat a thread as disposable just because the sender is promotional.

<callout icon="🛡️" color="red_bg">
<b>Protected: never temporary-retained, archived by the sweep, or deleted</b>

Immigration, visa, residence, consular · employment, termination, legal · banking, billing, important financial records · healthcare · housing agreements and administrative documents · tickets, reservations, receipts, purchase confirmations, event changes, cancellations, refunds (including from Fever and Ticketmaster) · anything that needs a reply or decision · anything whose importance is uncertain. <b>Uncertain stays in the inbox.</b>
</callout>

<callout icon="🪜" color="blue_bg">
## Steps
</callout>

1. <b>Fetch.</b> Read inbox threads. Backend classification can use larger batches; what Odara sees comes in small conversational batches (about 5), most important first.
2. <b>Protect first.</b> Anything matching the protected list stays in the inbox, whatever the sender.
3. <b>Classify the rest:</b> action needed · reply needed · informational (keep) · Pinterest · Eventos · Profissional · uncertain.
4. <b>Check tasks.</b> For action items, look in the Task Backlog for an existing item before proposing a new one; propose, don't create, unless she asks (G21 level 2).
5. <b>Drafts.</b> If she dictates or asks for a reply in this sweep, save it as a Gmail draft using Odara's Voice and say "usei seu Perfil de Voz". If she only asked for a suggestion, show the text without saving. <b>Never send.</b>
6. <b>Clean up.</b> For eligible threads: add one category label + <code>Pré-Arquivo/30 dias</code>, then remove them from the inbox. Do not mark as read unless she asks.
7. <b>Highlight.</b> One line each for interesting events or professional content. Only if she shows interest: keep it beyond retention (remove the retention label), hand events to Bardim, or open follow-up work. Radar de Shows stays independent: don't repeat its research or schedule.
8. <b>Report.</b> Counts per class, what was archived, what stays in the inbox and why, exceptions. During the pilot, append a counts-only line to the pilot record (no email content).

<callout icon="⏳" color="yellow_bg">
<b>Retention policy (pilot)</b>

- Target policy: 30 days. <b>Effective pilot safeguard: 60 days</b> minimum before any review for deletion.
- <b>No automatic deletion</b> by age. Nothing is deleted just because it is older than 30 days.
- Any bulk deletion needs Odara's explicit approval of that specific batch.
- Keep an auditable record (counts and thread references, not content) of what was classified, archived, skipped or deleted.
- When the pilot is approved for production, Odara and the Builder decide on moving to 30 days. Policy changes never delete existing labeled mail retroactively: the existing cohort is reviewed and the first production cleanup is approved explicitly.
</callout>

<callout icon="🔐" color="purple_bg">
## Approvals and limits
</callout>

<columns>
<column ratio="33">
<callout icon="🟢" color="green_bg">
<b>Inside a sweep she started</b>

Read, summarize, classify, check tasks. Apply the approved labels and archive eligible, non-protected threads (approved design, 21/11/2026). Save a draft she dictated (G21 level 2).
</callout>
</column>
<column ratio="33">
<callout icon="🟡" color="yellow_bg">
<b>Needs her yes</b>

Trash or delete anything (each batch). New labels, filters or rules. Marking as read in bulk. Creating tasks or involving Bardim. Changing the retention period. A scheduled run.
</callout>
</column>
<column ratio="33">
<callout icon="🔴" color="red_bg">
<b>Never</b>

Send, forward or reply. Automatic deletion. Summarize a thread that was not actually read. Copy email content into the Crew Noticeboard or any shared page: reference, don't transcribe (G22).
</callout>
</column>
</columns>

<callout icon="🛟" color="blue_bg">
## When it fails
</callout>

If the Gmail API does not answer or an action needs in-app approval that was not given: say so in one line, offer the manual Gmail link or a retry, and continue the rest of the routine. Never invent a summary. Scheduled runs have failed before with error 400 and "Gmail offline".

<callout icon="🚫" color="blue_bg">
## What it does NOT do
</callout>

- Send anything. Ever.
- WhatsApp or Instagram (no connector; WhatsApp only in a separate Claude in Chrome session).
- Create Gmail filters or automatic rules: not configured and not approved.
- Run on a schedule.
- Close Backlog Obligations on its own (that is the skill Marca como feito).

<callout icon="🧪" color="blue_bg">
## Acceptance tests
</callout>

- [x] Labels exist once each, retention nested under <code>Pré-Arquivo</code> (21/11/2026).
- [x] Pinterest, Fever promo and Zapier sample: category + retention label, out of the inbox, still searchable (21/11/2026).
- [x] Fever and Ticketmaster tickets / purchase confirmations stay in the inbox untouched (21/11/2026).
- [x] Uncertain threads (event reminders, local news digest, group emails) stay in the inbox (21/11/2026).
- [x] No task created, no email sent, no existing label changed (21/11/2026).
- [ ] Full conversational run with Odara: batches of about 5, 🔺 and housing at the top.
- [ ] Dictated reply saved as a draft with "usei seu Perfil de Voz".
- [ ] Gmail down: says so and continues, no invented summary.

<callout icon="📜" color="blue_bg">
## Status and decision log
</callout>

| Date | Decision | Why |
| --- | --- | --- |
| 28/07/2026 | First real workflow; Gmail tested OK. | Checar Emails and Responder Amigos were daily Obligations with no execution. |
| 11/11/2026 | Back from Paused to Active; Trigger field filled. | Test OK on record and Bom Dia kept the quick action. |
| 21/11/2026 | v2: triage + cleanup with independent retention and category labels; 60-day pilot safeguard; no automatic deletion; on demand only. | Approved by Odara (Designer handoff). Inbox had \~295 threads, most low-value. |

<callout icon="🔗" color="gray_bg">
<b>Registry</b>

- [x] Skills Mapping row updated for v2.
- [x] This page is the single canonical spec. The Bom Dia quick action row points here. The Morning Message Sweep (v1) is historical, marked \[ARCHIVE\], not an instruction.
- [x] Part of linked to Bom Dia Claude.
- [x] Used by empty: open to any agent, Access Sensitive.
</callout>
</content>
</page>
