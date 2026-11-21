<!-- Read through the Notion connector on 2026-11-21T15:10Z (Builder session, v2.1). Canonical spec lives in Notion. -->
<page url="https://app.notion.com/p/3fe107b19b4980a7a771d69a0746f355">
<ancestor-path>
<parent-data-source url="collection://3fe107b1-9b49-80fe-8401-000b3da753cf" name="Skills Mapping"/>
</ancestor-path>
<properties>
{"Access":"Sensitive","Integrations":["Gmail"],"Mission":"Inbox triage and cleanup: keep the inbox focused on what needs Odara's attention, decision or action. Protects sensitive and transactional mail, labels low-value mail with independent retention and category labels and archives it (still searchable). Never sends, never deletes automatically.","Name":"Gmail Sweep","Part of":["https://app.notion.com/p/415107b19b4981c89304d079c61d31f1"],"Recurrency":"On demand (also offered in Bom Dia). No schedule.","Referencia Interna":"21/11/2026 v2.1 pilot (Builder): archive only, the sweep never trashes; review on 21/12/2026. Target rule to test then: archive + 60-day manual review, or straight to Trash for an approved list. Labels: Pré-Arquivo/30 dias, Pinterest, Eventos, Profissional, 🧾 Comprovantes (protected), 🔥 Action Needed, ⏳ Waiting. No filters, no schedule. Pilot record in the Grab & Go task.","Status":"Active","Trigger":"Review (read-only): \"vamos ver nosso Gmail hoje\" and the Bom Dia quick action. Cleanup: \"gmail sweep\", \"limpa meu Gmail\", \"organiza minha Inbox\", \"roda meu Morning Message Sweep\". Ambiguous → Review.","Type":"Skill","Use Cases":"Runs the Obligations Checar Emails and Responder Amigos / Famílias. Prioritizes immigration, employment, housing, finance, health and deadlines; drafts replies in Odara's Voice when asked; archives Pinterest / Eventos / Profissional newsletters into Pré-Arquivo/30 dias; highlights opportunities in one line. WhatsApp stays out.","Last real run":"2026-11-21"}
</properties>
<content>
<callout icon="📬" color="purple_bg">
<b>SKILL · Gmail Sweep (v2.1 · pilot)</b>

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

<b>Review</b> (read-only): "vamos ver nosso Gmail hoje", and the Bom Dia quick action. <b>Cleanup</b>: "gmail sweep", "limpa meu Gmail", "organiza minha Inbox", "roda meu Morning Message Sweep". Ambiguous request → Review.
</callout>
</column>
<column ratio="33">
<callout icon="🚦" color="gray_bg">
<b>Status</b>

Active · v2 in <b>controlled pilot</b> since 21/11/2026, review on 21/12/2026. Archive only: the sweep does not trash. No schedule, no Gmail filter, no automatic deletion.
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
| Retention | <code>Pré-Arquivo/30 dias</code> (nested under <code>Pré-Arquivo</code>) | Temporary information, out of the inbox, still searchable. Clock starts at the email's received date. Nothing is deleted by age during the pilot (see Retention policy). |
| Category | <code>Pinterest</code> | Pinterest recommendation and inspiration emails. Kept for future visual/design work; consulted when a visual project comes up. No need to read each one. |
| Category | <code>Eventos</code> | Promotional newsletters from Fever, Ticketmaster and other event providers. |
| Category | <code>Profissional</code> | Professional newsletters, AI updates, career content. |
| Category (protected) | <code>🧾 Comprovantes</code> | Receipts and proof of payment. Archived for keeps: never retention, never Trash. |
| Category (protected) | <code>💼 Carreira</code> | Job applications, employers, work accounts, career documents. Never retention, never Trash. Career <i>newsletters</i> go to Profissional. |
| Status | <code>🔥 Action Needed</code> | She must act. Stays in the inbox. |
| Status | <code>⏳ Waiting</code> | Waiting on someone else. Stays in the inbox during the pilot (where it goes is decided at the review). |

- Future periods are siblings under <code>Pré-Arquivo/</code> (for example <code>Pré-Arquivo/15 dias</code>). Do not create them without Odara's approval.
- Existing labels (RADAR, Newsletters, 🔥 Action Needed, ⏳ Waiting, Spain Housing 2026, Compras, ✈️ Spain, etc.) are left as they are. Never remove or rename an existing label during a sweep. <code>Newsletters</code> overlaps the new categories; its future is an open decision.
- Never add a retention label to a thread that needs action, and never treat a thread as disposable just because the sender is promotional.

<callout icon="🛡️" color="red_bg">
<b>Protected: never temporary-retained, archived by the sweep, or deleted</b>

Immigration, visa, residence, consular · employment, termination, legal · banking, billing, important financial records · healthcare · housing agreements and administrative documents · tickets, reservations, receipts, purchase confirmations, event changes, cancellations, refunds (including from Fever and Ticketmaster) · anything that needs a reply or decision · anything whose importance is uncertain · explicit exclusions until Odara releases them: <b>DiR Tuset / Santander</b>. <b>Uncertain stays in the inbox.</b> Never infer that a bill was paid, an account secured or a government notice resolved.
</callout>

<callout icon="🪜" color="blue_bg">
## Steps
</callout>

1. <b>Pick the mode.</b> Review mode reads, classifies and reports, and changes nothing. Cleanup mode does the steps below. Once Odara starts a Cleanup, finish every batch without asking "continue?"; bring her only real decisions, in small batches (about 5), most important first.
2. <b>Protect first.</b> Anything matching the protected list stays in the inbox, whatever the sender.
3. <b>Classify the rest:</b> action needed · waiting · reply needed · receipt (Comprovantes) · informational (keep) · Pinterest · Eventos · Profissional · uncertain.
4. <b>Check tasks.</b> For action items, look in the Task Backlog for an existing item before proposing a new one; propose, don't create, unless she asks (G21 level 2).
5. <b>Drafts.</b> If she dictates or asks for a reply in this sweep, save it as a Gmail draft using Odara's Voice and say "usei seu Perfil de Voz". If she only asked for a suggestion, show the text without saving. <b>Never send.</b>
6. <b>Clean up.</b> For eligible threads: add one category label + <code>Pré-Arquivo/30 dias</code>, then remove them from the inbox. Receipts get <code>🧾 Comprovantes</code> only. Do not mark as read unless she asks. <b>During the pilot the sweep never moves anything to Trash</b>; Trash happens only when Odara asks for a specific batch.
7. <b>Highlight.</b> One line each for interesting events or professional content. Only if she shows interest: keep it beyond retention (remove the retention label), hand events to Bardim, or open follow-up work. Radar de Shows stays independent: don't repeat its research or schedule.
8. <b>Report once, at the end.</b> Counts per class, what was archived, what stays in the inbox and why, open Waiting items, exceptions. During the pilot, append a counts-only line to the pilot record (no email content).

<callout icon="⏳" color="yellow_bg">
<b>Retention policy</b>

<b>Pilot (now, until the review on 21/12/2026):</b> archive only. Eligible mail gets its category + <code>Pré-Arquivo/30 dias</code> and leaves the inbox. The sweep never trashes and nothing is deleted by age. Trash only when Odara asks for a specific batch. Keep an auditable record (counts and thread references, not content).

<b>Target rule (to be tested at the review, not active):</b> two lanes.

1. <b>Archive and review:</b> the default. Mail stays archived with the retention label; after 60 days Odara reviews it by hand before anything is deleted, as an importance filter.
2. <b>Straight to Trash:</b> only for categories or senders Odara puts on an approved list. Gmail deletes Trash for good after 30 days, which is the safety margin. Never protected classes.

At the review, Odara decides the Trash list and the retention period (the label name follows the decision). Changing the policy never deletes already-labelled mail retroactively: that cohort is reviewed and its first cleanup approved explicitly.
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

Trash or delete anything (each batch, until the Trash list is approved). New labels, filters or rules. Marking as read in bulk. Creating tasks or involving Bardim. Changing the retention period. A scheduled run.
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
- [ ] Review mode: zero changes in Gmail.
- [ ] Cleanup mode: runs to the end without "continue?", one final report; protected list and DiR Tuset / Santander untouched; nothing trashed.
- [ ] Full conversational run with Odara: decisions in batches of about 5, 🔺 and housing at the top.
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
| 21/11/2026 | v2.1 after the chat pilot: Review / Cleanup modes, run to the end with one report, status labels, 🧾 Comprovantes protected, DiR Tuset / Santander excluded. Pilot = archive only, review 21/12/2026; target two-lane rule (archive + 60-day manual review, or approved Trash list) to be tested then. | Odara, live with the Builder. The chat pilot's Trash moves were approved by her in that chat. |

<callout icon="🔗" color="gray_bg">
<b>Registry</b>

- [x] Skills Mapping row updated for v2.
- [x] This page is the single canonical spec. The Bom Dia quick action row points here. The Morning Message Sweep (v1) is historical, marked \[ARCHIVE\], not an instruction.
- [x] Part of linked to Bom Dia Claude.
- [x] Used by empty: open to any agent, Access Sensitive.
</callout>
</content>
</page>
