<page url="https://app.notion.com/p/40c107b19b498031b5e5f5fa01cc84b6" icon="🚢">
<ancestor-path>
<parent-data-source url="collection://3fe107b1-9b49-8063-81e6-000b78bf6c2f" name="Odyssey - Architecture Overview"/>
<ancestor-2-database url="https://app.notion.com/p/3fe107b19b4980e7bb68f0766bb96772" title=""/>
<ancestor-3-page url="https://app.notion.com/p/3aa107b19b49808bbf8cd2719803ed0d" title="Project Odyssey"/>
</ancestor-path>
<properties>
{"Last Update":"2026-11-19T14:23:50.069Z","Name":"02 O Navio","Pillar":"Estrutura","Purpose":"Establishes the operational foundation of Odyssey — its architecture, governance, systems, and the rules that keep everything connected and working together.","Select":"Reconciliada","url":"https://app.notion.com/p/40c107b19b498031b5e5f5fa01cc84b6"}
</properties>
<iconMetadata>{"type":"emoji","emoji":"🚢"}</iconMetadata>
<content>
<quote color="green_bg">
<b>The ship should carry the complexity, so the Captain can enjoy the journey.</b>
</quote>

<callout icon="🚢" color="blue_bg">
<toggle>
<b>02 · O Navio — Operational Foundation</b>

<b>What this page is:</b> The machinery behind Odyssey. It explains <b>how the project stays coherent, connected, safe and able to evolve</b>, even when different AI models, chats and tools are involved.

<b>When to use:</b> When an AI needs to locate the right Source of Truth, understand who operates what, plan a handoff, choose where to document a change or identify an integration dependency.

<b>Boundary: </b><mention url="https://app.notion.com/p/3fe107b19b49805c9585dc8b9b21c8f6">01 A Bússula</mention> says <i>why</i> Odyssey exists. O Navio shows <i>how its parts work together</i>. Universal instructions and permissions live in the <mention url="https://app.notion.com/p/3aa107b19b4981079aaecf1f72b1bb98">Odyssey Operating Manual</mention>; Persona-specific behavior lives with the <mention url="https://app.notion.com/p/3fe107b19b49800e9135e9e895749250">04 AI Crew & Skills</mention>.
</toggle>

<b>Operational state:</b> <b><span color="orange">UNDER AUDIT</span></b> — the architecture described here includes both existing practices and capabilities still being tested. A documented intention is not proof of a working integration.
</callout>

<columns>
<column ratio="50">
<callout icon="🧭" color="gray_bg">
<b>Experience & meaning</b>

The Bússola protects the human side: clarity, curiosity, freedom, emotion and a life actively lived.
</callout>
</column>
<column ratio="50">
<callout icon="⚙️" color="gray_bg">
<b>Structure & continuity</b>

The Navio supports the practical side: sources, ownership, coordination, permissions, implementation and recovery.
</callout>
</column>
</columns>

<callout icon="🤖" color="blue_bg">
## 01 AI START HERE — Navigate the ship
</callout>

<b>Arriving in a fresh chat?</b> Use this sequence before handling Odyssey project work:

1. <b>Find the home:</b> locate the current page/database responsible for the topic. Notion is the live documentation, not the chat transcript.
2. <b>Understand the mission:</b> read the <mention url="https://app.notion.com/p/3fe107b19b49805c9585dc8b9b21c8f6">01 A Bússula</mention>, <mention url="https://app.notion.com/p/3aa107b19b4981079aaecf1f72b1bb98">Odyssey Operating Manual</mention> and <mention url="https://app.notion.com/p/3aa107b19b4981b192b1fc071711e4b0">Player / Character Sheet</mention> when needed for the interaction.
3. <b>Know your role and environment:</b> determine whether you are acting as a general AI collaborator, a Builder or a Crew Persona. Model names are tools, not fixed job descriptions. In a chat you never change structure; that happens only in a Builder environment (Operating Manual G21).
4. <b>Verify before claiming:</b> read the actual source, check access/tool availability and distinguish proposed, approved, implemented and validated.
5. <b>Act within authority:</b> the Operating Manual governs edits, sharing, external commitments, sensitive information and deletion.
6. <b>Leave continuity:</b> with authorization, update the existing canonical home in place; provide a clear handoff if another agent must continue.

<b>North-star test:</b> Could Odara open another AI chat and continue without manually rebuilding the project context? If not, the operating system still has a gap.

<callout icon="🏴‍☠️" color="blue_bg">
## 02 The Captain, Builders & Crew
</callout>

<callout icon="👑" color="purple_bg">
<b>Odara — The Captain</b>

Odara is the primary player and final decision-maker for meaningful choices about her life and the project. The system should give her clarity and agency, not make her the messenger, archivist or integration layer between agents.
</callout>

<columns>
<column ratio="50">
<callout icon="🛠️" color="gray_bg">
<b>The Builders — maintain the ship</b>

Builder responsibilities include documentation architecture, tools, technical foundations, integrations, quality checks and repair.

<b>A Builder is an environment, not a chat or a Persona.</b> Structural work happens only in <b>Claude Code</b> or <b>Codex</b>, which can run long multi-step changes, verify them and version them in GitHub. Chats (Claude, ChatGPT) are where Odara lives with the Crew: conversations, decisions, Persona work and each Persona's own Sources of Truth. Either model may build, as long as it does so from a Builder environment.

<p>
<b>Builders at a glance:</b> 
</p>

- 🖥️ <mention url="https://app.notion.com/p/3fe107b19b4980aaabbee3096706ac52">Hacker, The Good</mention> (works in Claude Code) leads infrastructure and structural construction: documentation architecture, databases, shared surfaces, integrations, technical health, scheduled tasks and GitHub. The former Mayor role was absorbed here; legacy pages that mention Mayor now mean Hacker.
- 🎨 <mention url="https://app.notion.com/p/3fe107b19b4980f6addcec870cbe6619">Chatty, The Designer</mention> is the Art Director: experience, visual direction and narrative, designed with Odara in chat; structural implementation of her designs happens in a Builder environment (“Experience Director” and “Art Director / ChatGPT” are older names for the same role).
- Both Builders are registered in <mention url="https://app.notion.com/p/3fe107b19b4980979bc6ccfd5c1a2c4b" type="database">Crew Mapping</mention>.

<b>Authority:</b> <mention url="https://app.notion.com/p/3fe107b19b4980979bc6ccfd5c1a2c4b" type="database">Crew Mapping</mention> governs role assignments. Model ≠ Persona ≠ ownership. The currently documented edit permissions remain in <mention url="https://app.notion.com/p/3aa107b19b4981079aaecf1f72b1bb98">Odyssey Operating Manual</mention>; future autonomy changes require explicit approval.
</callout>
</column>
<column ratio="50">
<callout icon="🎭" color="gray_bg">
<b>The Crew — bring the world to life</b>

Personas contribute distinct expertise, narrative voice and domain-level continuity.

Their roles, statuses, instructions and domain Sources of Truth belong in <mention url="https://app.notion.com/p/3fe107b19b49800e9135e9e895749250">04 AI Crew & Skills</mention>, not in a duplicate roster here.

<b>Important:</b> ChatGPT or Claude may embody a Persona; the <i>AI model</i>, <i>Persona identity</i>, <i>domain ownership</i> and <i>technical access</i> are different things.
</callout>

<toggle heading="h3">
🔍 Working differences between AI models — observations, not permanent assignments

Odara has historically used <b>Claude</b> heavily for structural, analytic and code-related work, and <b>ChatGPT</b> heavily for creative direction, images, narrative and experience. This has helped the partnership, but must <b>not</b> become an exclusive division of abilities or assume that a plan guarantees a feature.

<b>Plans reported for the current workflow:</b> Claude Pro and ChatGPT Plus. These are account context, not guarantees of access to a connector, feature, quota or specialized tool. Model plans, tools and capabilities change; verify the active session and choose the tool suited to the task. Both systems can assist with rational and emotional aspects without being cast as opposites.
</toggle>

<p />
</column>
</columns>

<callout icon="🧱" color="blue_bg">
## 03 · The Ship's Blueprints — where truth lives
</callout>

<b>The architecture is intentionally lightweight:</b> one live home for project knowledge, one technical home for code/backups and clearly identified channels for work and handoffs. <b>Notion first:</b> if the existing Notion workflow meets the need, use it instead of maintaining another tool. ClickUp was explored but set aside for this reconciliation after connector limits and workflow friction; this is a project workflow decision, not a claim that ClickUp is globally unavailable.

<columns>
<column ratio="50">
<callout icon="📓" color="green_bg">
<b>Notion — Live Source of Truth</b>

<mention url="https://app.notion.com/p/3aa107b19b49808bbf8cd2719803ed0d">Project Odyssey</mention>

Current instructions, principles, Persona definitions and canonical project records are referenced from Notion.

<b>Plan reported:</b> Notion Free. Official Free-plan reference, checked 06 Nov 2026: <b>5 MB max per uploaded file; 7 days of page history</b> ([Notion pricing](https://www.notion.com/pricing)). Recheck before treating these limits as durable.

<b>Design principle:</b> a live page says what is true <i>now</i>, not the chronological history of every discussion. A change is integrated into its existing section.
</callout>
</column>
<column ratio="50">
<callout icon="💾" color="gray_bg">
<b>GitHub — Code & potential backup</b>

[odarambmenezes/odyssey](https://github.com/odarambmenezes/odyssey)

<b>Documented workflow:</b> manually updated after structural sessions, not synchronized live with Notion. The Operating Manual (G16) names it as a fallback <b>when Notion is unavailable</b>, not a competing current source.

<b>Technical custodian:</b> Hacker, The Good / authorized Builders. <b>Unverified:</b> repository contents, most recent update, completeness and ability to restore. Do not report a successful backup without checking those facts.
</callout>
</column>
</columns>

<callout icon="⚠️" color="yellow_bg">
<b>Do not equate a link with a working system.</b>

Notion is the primary live documentation. GitHub is not a verified real-time mirror of Notion. Private memories in different AI products are neither shared automatically nor a substitute for canonical records. If a source is unreachable, report the limitation and verify the fallback before relying on it.
</callout>

### 🗺️ One concept, one home

<table header-row="true">
<colgroup>
<col width="371.99998474121094" />
<col width="322.3522644042969" />
</colgroup>
<tr>
<td>
Need
</td>
<td>
Canonical destination
</td>
</tr>
<tr>
<td>
Purpose, values, experience principles
</td>
<td>
<mention url="https://app.notion.com/p/3fe107b19b49805c9585dc8b9b21c8f6">01 A Bússula</mention>
</td>
</tr>
<tr>
<td>
Universal AI rules, permission boundaries
</td>
<td>
<mention url="https://app.notion.com/p/3aa107b19b4981079aaecf1f72b1bb98">Odyssey Operating Manual</mention>
</td>
</tr>
<tr>
<td>
Interaction preferences of the player
</td>
<td>
<mention url="https://app.notion.com/p/3aa107b19b4981b192b1fc071711e4b0">Player / Character Sheet</mention>
</td>
</tr>
<tr>
<td>
Architecture, coordination, integration model
</td>
<td>
<b>02 · O Navio (this page)</b>
</td>
</tr>
<tr>
<td>
Visual identity, typography, assets
</td>
<td>
<mention url="https://app.notion.com/p/3fe107b19b49800f8af1f79ebedd1f20">03 A Paisagem </mention>
</td>
</tr>
<tr>
<td>
Persona definitions, roles, domain ownership
</td>
<td>
<mention url="https://app.notion.com/p/3fe107b19b49800e9135e9e895749250">04 AI Crew & Skills</mention>
</td>
</tr>
<tr>
<td>
History, logs and lessons — not a permanent archive of retired documentation
</td>
<td>
<mention url="https://app.notion.com/p/3fe107b19b4980a3b94de83b692dd5fb">05 A Jornada</mention>
</td>
</tr>
<tr>
<td>
Live operational state: open obligations, shopping, birthdays
</td>
<td>
<mention url="https://app.notion.com/p/416107b19b4981f4beeeecc87e51b8bd">06 O Hoje</mention>
</td>
</tr>
</table>

<callout icon="📜" color="blue_bg">
### THE CODE — Live documentation, not a dump
</callout>

<b>The mistake we will not repeat:</b> adding dated notes to the bottom of pages created duplicated protocols, conflicting information and exhausting reconciliation. <b>Keep today's truth clear; preserve history elsewhere.</b>

<columns>
<column ratio="50">
<callout icon="🔄" color="gray_bg">
<b>01 · Update, don't append</b>

Integrate approved changes into the existing page. Track <b>proposed → approved → implemented → validated</b> without piling versions in the live body.
</callout>

<callout icon="🧷" color="gray_bg">
<b>02 · One Truth, One Home</b>

Find the canonical source and owner first. Link across documents rather than making competing copies.
</callout>
</column>
<column ratio="50">
<callout icon="📝" color="gray_bg">
<b>03 · Document as you go</b>

After authorized decisions, update the relevant SoT in the same session when tools permit. Chats are not the shared memory; disclose anything not yet saved.
</callout>

<callout icon="🗺️" color="gray_bg">
<b>04 · Leave a clear trail</b>

Pages show purpose, ownership, state and relevant links. Cleaning outdated references is part of the work, not a new system to manage.
</callout>
</column>
</columns>

<callout icon="⚖️" color="green_bg">
<b>Conflict rule </b>

<b>Authority determines which source governs. Recency determines which valid version applies within that source.</b>

Follow the documented instruction hierarchy and identify the canonical owner. Within that authoritative source, the latest <b>approved</b> version applies. A newer note elsewhere does not silently override it. Surface unresolved conflicts to Odara under the Operating Manual.
</callout>

<toggle heading="h3">
🔎 Maintenance, provenance & legacy reconciliation

- <b>Permission:</b> the authoritative G20/G21 rules live in the <mention url="https://app.notion.com/p/3aa107b19b4981079aaecf1f72b1bb98">Odyssey Operating Manual</mention>, not in a duplicate rulebook here.
- <b>History:</b> Significant session records and lessons belong in <mention url="https://app.notion.com/p/3fe107b19b4980a3b94de83b692dd5fb">05 A Jornada</mention>. Retired source documents leave Odyssey after the G21 checks and Odara's decision. Important decisions are recorded in the Session Log (see the Operating Manual glossary).
- <b>Reconciliation method:</b> inventory → choose owner/destination → classify confirmed/provisional/superseded → propose/approve → validate links and behavior → preserve superseded records appropriately. No silent deletion.
- <b>Source check:</b> use the live Operating Manual and the canonical pillar/Skills Mapping pages. Former Notion Playbook and legacy Codex are retired and must not be consulted as operational sources.
- <b>Cleanup:</b> correct drift when authorized; otherwise flag it for the established project reconciliation workflow. Avoid spawning another page or backlog.
</toggle>

<callout icon="🪑" color="blue_bg">
## 04 Communication & continuity — no human glue
</callout>

<b>Separate chats do not automatically share context, see one another's screens or notify other agents.</b> The system needs explicit handoffs and an authoritative record so Odara is not forced to relay every update herself.

<columns>
<column ratio="50">
<callout icon="📨" color="gray_bg">
<b>Now: Crew Noticeboard</b>

<page url="https://app.notion.com/p/410107b19b4981009b2ada911ec304fb">
Crew Noticeboard
</page>

Established shared destination for cross-agent notes and handoffs.
</callout>
</column>
<column ratio="50">
<callout icon="🚪" color="gray_bg">
<b>Exploring: One Door</b>

Target experience: Odara opens one chat and asks for the Cap, another Persona or a Builder without searching multiple conversations.

<b>Status: proposal / test required.</b> Persona voice, permissions, context retrieval and handoff quality must be demonstrated before treating the switch as real.
</callout>
</column>
</columns>

<b>Minimum useful handoff:</b> objective · current status · relevant links/SoT · decisions already approved · next action · blocker/owner. Keep it short; avoid reproducing sensitive material or entire chat transcripts.

<b>Handoffs between agents:</b> two skills, <b>Leave a Note for a Persona</b> and <b>Hand Off to Persona</b>, are the intended mechanism (both On Draft, to be tested when the Personas are reactivated), so this is <b>not an active automated handoff</b> yet. The board is kept tidy by a fortnightly clean-up run by Lori (skill Noticeboard Clean-up, process still to be designed). Notes have no expiry date: an unread limit applies instead, and notes are never deleted.

<toggle heading="h3">
🔧 Cross-model asset exchange — an open integration need

ChatGPT and Claude may need to share images, renders, screenshots, HTML files and code outputs. A shared folder or browser workflow could help, but <b>the full two-way exchange has not been validated</b>. Do not claim automatic transfer or independent access just because an integration exists.

Desired behavior: assets stored at a verifiable address; Notion links to the canonical artifact; each receiving agent checks it can actually open and inspect the file. Choose the simplest proven transport before introducing more infrastructure.
</toggle>

<callout icon="🛡️" color="blue_bg">
## 05 · Operational readiness & known limits
</callout>

<b>One crucial distinction:</b> <b>Documented</b> is not necessarily <b>working</b>. These statuses guide what to verify before relying on a capability.

<b>Operational permission:</b> reading, researching and drafting are generally available; editing, restructuring, sharing, scheduling and external commitments follow the <mention url="https://app.notion.com/p/3aa107b19b4981079aaecf1f72b1bb98">Odyssey Operating Manual</mention>. Do not treat future ideas about autonomous Builders as current authorization.

| Area | Current reading | Required check |
| --- | --- | --- |
| Notion as project SoT | Established practice | Page and connector access in the active session |
| ChatGPT / Claude collaboration | Both used; coordination is manual or via shared records | Handoff readability and permissions |
| Crew Noticeboard | Existing documented channel | Whether messages can be retrieved and followed up |
| GitHub repository | Linked, technical use intended | Contents, access, last valid backup and sync method |
| Single-entry Persona routing | Concept / not validated | Persona fidelity, context, handoff and user effort |
| Shared images / HTML review | Need identified; bridge not validated | Two-way file access and real screenshots |
| Automations / scheduled work | Tool- and account-dependent | Actual active schedule, ownership, quotas and timezone |

<toggle heading="h3">
⚙️ Practical learnings — verify before relying on them

- <b>Notion editing:</b> use focused updates when possible, preserve native blocks and children, read back material changes. Large rewrites or code-heavy blocks may need a different workflow. Do not treat prior API failures as permanent platform limitations.
- <b>Schedules:</b> the project uses <b>Europe/Madrid</b> as the relevant local time zone. Historical notes mention limits on scheduled runs; quotas and available tools must be rechecked in the account executing the task. A task set up in one AI does not become active in the other.
- <b>Connectors:</b> access is session-specific. Previous connection failures — including Ticketmaster in early November 2026 — are historical observations, not a blanket rule.
- <b>Notion plan limits:</b> file-size/history constraints were previously researched; verify the current plan and official limits before making architecture decisions.
- <b>Code and backup:</b> GitHub may be the right technical home, but the backup's fidelity and recovery process must be tested, not inferred from repository existence.
</toggle>

<callout icon="🗺️" color="blue_bg">
## Grab & Go - Task Manager
</callout>

<database url="https://app.notion.com/p/1ee7ad29377949e2af70cb3ca6c3faa6" data-source-url="collection://d9baf9a3-2d3f-41be-8fdd-152d8ee1fd91" inline="true">
Grab & Go
</database>

<database url="https://app.notion.com/p/c72071d037784ba5b6308c82a5a36d07" data-source-url="collection://a4f2dc93-71ae-44c6-8049-b2cd8f752220" inline="false" color="yellow_bg">
Odyssey — Backlog de Tarefas
</database>
</content>
</page>

<parent-data-source-schema url="collection://3fe107b1-9b49-8063-81e6-000b78bf6c2f">
The SQLite table definition for this page's parent data source. Use these column names and option values to set this page's properties, create sibling pages, or query the data source.
These columns are read-only, so don't set them: "Last Update".
<sqlite-table>
CREATE TABLE IF NOT EXISTS "collection://3fe107b1-9b49-8063-81e6-000b78bf6c2f" (
	url TEXT UNIQUE,
	createdTime TEXT, -- ISO-8601 datetime string, automatically set. This is the canonical time for when the page was created.
	"Pillar" TEXT, -- one of ["Estrutura", "Experiencia", "Visual", "Execution", "Aprendizagem", "Presente"]
	"Select" TEXT, -- one of ["To Reconcile", "Stuck", "In Progress", "Reconciliada", "Fechada"]
	"Last Update" TEXT NOT NULL, -- ISO-8601 datetime string, automatically set. This is the canonical time for when the page was last edited.
	"Purpose" TEXT,
	"Name" TEXT
)
</sqlite-table>
</parent-data-source-schema>