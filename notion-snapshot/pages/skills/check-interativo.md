<!-- Read through the Notion connector on 2026-11-26T23:17Z (Builder session, tickets pilot v1). Canonical spec lives in Notion. -->
<page url="https://app.notion.com/p/424107b19b4981939ba6c79dc68ecf7e" icon="🃏">
<properties>
{"Access":"Open","Documentação":"https://claude.ai/artifact/274dgfAdFgTWLv5AgFwfSW","Mission":"Bring Odara several decisions, confirmations or options at once as a deck of interactive cards she answers fast (swipe, tap, voice), and return a final report the Persona reads directly.","Name":"Check Interativo","Status":"Active","Trigger":"\"Faz um check interativo\", \"me manda em cartas\", or a Persona proposing it when there are several decisions to confirm at once.","Type":"Skill","Use Cases":"Alignment checks on a Persona page or SoT; reviewing several proposals in one go; picking between visual options; quick confirmations when Odara is on the iPad and in an interactive mood. Not for a single yes/no (ask in chat).","date:Last real run:start":"2026-11-26"}
</properties>
<content>
## What it is

A reusable Claude artifact (one link, always the same) that shows Odara a deck of cards, one decision per card, and ends with a report. She answers by swipe, tap or voice; the Persona reads the report straight from the artifact. Approved by Odara on 26/11/2026 after a pilot run with Gibbs.

<b>When to use:</b> several things to confirm at once, or when Odara is in a more interactive mood. A single decision stays in chat.

## Card types

| Type | How Odara answers | Use for |
| --- | --- | --- |
| <code>yesno</code> | Swipe right = yes, left = no (or ✓ / ✕) | Approving a proposal |
| <code>choice</code> | One tap on an option shown on the card | Picking one of 2–3 curated options (G18) |
| <code>multi</code> | Tick several, then confirm | "Which of these apply?" |
| <code>open</code> | Speak or type, then confirm | A short free answer |

Every card can carry a comment (🎤). A numbered map at the top shows each card's state (green ✓ answered, yellow passed without an answer) and jumps to any card; any answer can be changed from the final report without losing the others.

Voice: the page's microphone works in Chrome and the Claude desktop app; on iPad Odara uses the keyboard's dictation mic. Each card should state its <b>practical effect</b> in one line.

## How to run it (Claude only)

1. Write the deck into the artifact's database with the Claude artifacts tools:
   - <code>decks/<deck-id></code> = <code>{id, title, sub, cards: [{id, type, tag, title, body, options: [{label, hint}], effect}]}</code>
   - <code>config/current</code> = <code>{deck: "<deck-id>"}</code> (pass its current version when overwriting).
2. Send Odara the link and say how many cards there are.
3. When she says "terminei o check" (or sends part of it early), read <code>answers/<deck-id></code>: <code>sent: true</code> means she pressed send, <code>complete: false</code> means a partial send (unanswered cards show "sem resposta" in <code>report</code>). Each send replaces the previous one.
4. Apply only what was approved, within the Persona's permissions (G21). Anything new or consequential still goes back to her, one recommendation at a time.

Fallback: if saving fails, Odara copies the report from the page and pastes it into the chat.

## Tickets (Grab & Go) · pilot v1 since 26/11/2026

The Check is Odyssey's ticket system ("Mesa do Capitão", provisional name; Lori names it and does the visual). <b>A ticket is a Grab & Go row</b> that needs Odara (Needs Odara = You decide / You do). The tickets panel reads the <b>🎫 Tickets</b> view and shows the tickets in lanes:

| Status | Lane |
| --- | --- |
| Ready and Cards above 0 | 🃏 Com cartas, esperando você |
| Ready without Cards | 🫵 Para você fazer (action outside the panel) |
| In Progress | 👀 Com a tripulação |
| Blocked | ⛔ Travado |
| Idea | 💡 Ideias |
| Done | ✅ Fechados (flagged "sem prova" without Proof) |

Product proposal Odara approved as pilot v1: https://claude.ai/artifact/8kKx6EfmE8K3Ge3qVQ1dRW

<b>How Odara works the panel:</b> "Resolver 5 agora" opens the top 5 tickets with cards in a row, ending on a finish screen. "Mutirão" runs through every ticket with cards at once, with "faltam N" and a skip button. Every card has "Agora não" (the card comes back next time) and a 4-second undo instead of a confirmation. Ready tickets untouched for 5 days show "parado".

Tickets panel (test link): https://claude.ai/artifact/3JAv7SUbpTZDeTTHQeSCQg

<b>To open a ticket with cards (any Persona, Claude or ChatGPT):</b>

1. Create a Grab & Go row: Type Decision (or the fitting type), Needs Odara = You decide, Status Ready, Requested by = you, Assignee = who acts next, plus a one-line Why it matters.
2. In the page body, add a heading <code>## Check</code> followed by one JSON code block with the deck: <code>{"id":"unique-id","title":"...","cards":[...]}</code>. The card shapes are the four types above.
3. Set the <b>Cards</b> property to the number of cards. Without it the ticket lands in "Para você fazer", not in the cards lane.
4. A ticket without a <code>## Check</code> block still works: the panel shows one free-answer card.

<b>Card rule (all Personas):</b> one question per card; <code>body</code> says why it matters in one line; recommend one option with the reason (<code>choice</code>/<code>multi</code>: <code>"rec": true</code> on that option, reason in its <code>hint</code>; <code>yesno</code>: <code>"rec": "sim"</code> or <code>"não"</code> plus <code>"recWhy"</code>); at most 3 options; <code>effect</code> says what the answer unlocks ("➜ With this, Cap sends 3 hotels tomorrow"). If Odara would need to research to answer, the card is not ready.

<b>What the panel writes back:</b>

- Odara's answers go to a <code>## Check · answers</code> code block in the same page. Read it; do not edit it.
- When every card is answered (none left on "Agora não"), the panel sets <b>Answered on</b> and moves the ticket from Ready to In Progress.
- <b>Checkout:</b> answered tickets without <b>Delivered on</b> wait in the checkout. It builds <b>one report for Hacker</b> (Claude Code), grouped by Requested by. Odara pastes it into Hacker's chat and taps "marcar entregue", which sets Delivered on.
- <b>Hacker on a checkout report:</b> do what is his and close it with <b>Proof</b> (link to what changed). For any other Persona, post a Crew Noticeboard note for her with the ticket link, so the Persona finds it when Odara opens her chat. Reply to Odara in one line: what was done, what went to the Noticeboard.
- A ticket closes as Done only with Proof.
- A comment with <code>@lori</code> or <code>@gibbs</code> gets a reply on the card. Claude answers inside the panel as that Persona, using the Persona's page. The reply is stored in the same answers block.

## Rules

- A run Odara calls a test is never applied as truth.
- Answers stay inside the artifact; no sensitive data in card text beyond what the decision needs (G22).
- ChatGPT cannot read the artifact's database: from there, ask Odara to paste the report.

## History

- 26/11/2026: pilot with Gibbs (alignment check on hierarchy and his page). All four card types, voice comment and report reading worked. Run as a test, not applied.
- 26/11/2026: first real run (Gibbs audit deck, 22 cards, loaded from the database). Navigation reworked the same day: card map with states, edit from report, partial send.
</content>
</page>
