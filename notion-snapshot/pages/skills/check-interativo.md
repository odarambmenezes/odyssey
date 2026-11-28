<!-- Written to Notion by the Builder session on 2026-11-28 (cards become the main decision skill). Canonical spec lives in Notion. -->
<page url="https://app.notion.com/p/424107b19b4981939ba6c79dc68ecf7e" icon="🃏">
<properties>
{"Access":"Open","Documentação":"https://claude.ai/artifact/3JAv7SUbpTZDeTTHQeSCQg","Integrations":["Notion"],"Mission":"Odyssey's main way to ask Odara for decisions: a deck of cards inside a Grab & Go ticket, answered in the tickets panel, delivered back to whoever asked without copy-paste.","Name":"Check Interativo","Referencia Interna":"Tickets panel artifact 1298083d-0f48-42dc-bcd6-12fd98853981 (MVP, frozen until v2)","Status":"Active","Trigger":"A Persona needs one or more decisions from Odara outside a live chat; \"me manda em cartas\"; \"faz um check interativo\".","Type":"Skill","Use Cases":"Any decision that can wait for Odara: alignment checks, confirming several proposals, picking between options, reviews after an audit. Not for a single quick question inside a live chat.","date:Last real run:start":"2026-11-28"}
</properties>
<content>
## What it is

Odyssey's main way to ask Odara for decisions (Odara, 28/11/2026). A Persona puts one or more questions as a deck of cards inside a <b>ticket</b> (a Grab & Go row). Odara answers in the <b>tickets panel</b>, one card at a time, by swipe, tap or voice, wherever she is. When she finishes a ticket, the panel saves her answers in the ticket and leaves a Crew Noticeboard note for whoever asked. Nobody copies or pastes anything.

<b>Proven 28/11/2026:</b> Odara answered 15 tickets in one session on a treadmill, on her phone, with weak signal.

<b>When to use:</b> any decision a Persona needs from Odara outside a live conversation, or several decisions at once. A single quick question inside a live chat stays in the chat (Operating Manual G18).

<b>Tickets panel (the active version):</b> https://claude.ai/artifact/3JAv7SUbpTZDeTTHQeSCQg. This MVP is frozen until Lori's v2 is ready and approved by Odara: no changes to it meanwhile, except a fix for something broken.

## Open a ticket with cards (any Persona, Claude or ChatGPT)

1. Create a Grab & Go row: Type Decision (or the fitting type), Needs Odara = You decide, Status <b>Ready</b>, Requested by = you, Assignee = who acts next, and a one-line Why it matters.
2. In the page body, add a heading <code>## Check</code> followed by one JSON code block with the deck: <code>{"id":"unique-id","title":"...","cards":[...]}</code>.
3. Set the <b>Cards</b> property to the number of cards. Without it the ticket lands in "Para você fazer", not with the cards.
4. A ticket without a <code>## Check</code> block still works: the panel shows one free-answer card.

## Card types

| Type | How Odara answers | Use for |
| --- | --- | --- |
| <code>yesno</code> | Swipe right = yes, left = no (or ✓ / ✕) | Approving a proposal |
| <code>choice</code> | One tap on an option | Picking one of 2–3 curated options (G18) |
| <code>multi</code> | Tick several, then confirm | "Which of these apply?" |
| <code>open</code> | Speak or type, then confirm | A short free answer |

Shape of one card: <code>{"id":"c1","type":"choice","tag":"Who needs it","title":"...","body":"...","options":[{"label":"...","hint":"...","rec":true}],"effect":"➜ ..."}</code>. Every card can carry a comment, and every card has "Agora não".

<b>Card rule:</b> one question per card; <code>body</code> says why it matters in one line; recommend one option with the reason (<code>choice</code>/<code>multi</code>: <code>"rec": true</code> on that option, reason in its <code>hint</code>; <code>yesno</code>: <code>"rec": "sim"</code> or <code>"não"</code> plus <code>"recWhy"</code>); at most 3 options; <code>effect</code> says what the answer unlocks. If Odara would need to research to answer, the card is not ready. Optional <code>"mental": 1|2|3</code> marks the thinking a card asks. No sensitive detail beyond what the decision needs (G22).

## What happens when Odara answers

- Her answers go to a <code>## Check · answers</code> code block in the same ticket. Read it; never edit it.
- When every card is answered, the panel sets <b>Answered on</b> and <b>Delivered on</b>, moves the ticket from Ready to In Progress, and posts one Noticeboard note "Odara respondeu: ‹ticket›" to whoever asked (Requested by; Hacker when empty). The note carries only the link, never the answers.
- A card left on "Agora não" keeps the ticket Ready: next time the panel asks only that card. The ticket is delivered when it is complete.
- Without signal, answers stay on her phone and are sent when the signal returns; the panel says so.

## Picking up (the Persona who asked)

When invoked, check your 📬 Noticeboard inbox. For each "Odara respondeu" note: read the answers in the ticket, act within your permissions (G21), pass anything that is not yours to the right Crew member with a note, and close the ticket as Done with <b>Proof</b>. Anything new or consequential goes back to Odara as a new card, never as a long message.

## How Odara uses the panel

The panel opens on a menu. "Responder cartas" opens the cards full screen, one ticket after another; after each ticket a screen confirms "Gravado e entregue" and who received it, and the next ticket opens only when she taps "Próximo ticket". The other menu entries list what she has to do herself and what is with the Crew.

## Rules

- A run Odara calls a test is never applied as truth.
- ChatGPT reads and writes tickets through its Notion connector, like Claude.

## History

- 26/11/2026: first pilot as a standalone deck (one artifact, decks in its own database), then moved into Grab & Go tickets and the tickets panel.
- 28/11/2026: real use at scale (15 tickets); checkout step removed, delivery automatic; made the main decision skill.
</content>
</page>
