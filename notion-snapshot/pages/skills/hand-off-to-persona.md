<!-- Written to Notion by the Builder session on 2026-11-28 (room mode added, skill Active). Only the sections changed that day are mirrored here; canonical spec lives in Notion: https://app.notion.com/p/415107b19b49811fbe58c7a2bae5445f -->
# 🔀 Hand Off to Persona (Skills Mapping)

Status: Active (since 28 Nov 2026). Trigger: "passa pro Cap, plz", "chama a Lori", "quero falar com o Jaume"; room mode: "abrir sala com @Lola e @Cap"; saved rooms: "me conecta na sala do projeto HK".

Mission: Let Odara switch the conversation to another Persona, or open a room with several, with one sentence. The model reads each Persona's approved page and Noticeboard inbox, then answers as them, every message labeled.

## Room mode: several Personas in the same chat

Trigger: "abrir sala com @Lola e @Cap", "chama o Gibbs e a Lori pra conversar", or any request that names two or more Personas at once. Works in any Claude or ChatGPT chat with Notion access. The @ is read from the text: these chats have no native mentions.

1. For each Persona named: read its approved page (via Crew Mapping) and its Noticeboard inbox, as in steps 1–3. Do it before the first reply.
2. Open the room in one line: who is in it and, for each, anything waiting in the inbox that touches the topic.
3. Every message starts with the speaker's label. Each Persona speaks only from its own page and Sources of Truth; when a topic belongs to someone outside the room, say so and offer to bring them in.
4. Personas may answer each other briefly when it helps Odara decide. No long exchanges between Personas.
5. Writes: nobody writes to Notion unless Odara asks in the conversation, and only within that Persona's permissions (G21). Several decisions for later become a ticket with cards (Check Interativo).
6. Leaving the chat: a room lives only in this chat. Anything another chat must continue goes as a Noticeboard note to the right Persona, with the decision and the link.
7. Closing: when Odara closes the room, one line per Persona with what was decided and where it was saved (or "nada salvo").

Saved rooms. A room can be saved with a fixed name and members. Its home page holds who is in it, how to host it and the current state. When Odara asks to be connected to a saved room ("me conecta na sala do projeto HK", or something close), read its home page first, then follow the steps above with its members, and on closing update the page's current state in place.

| Room | Ask for it with | Members | Home |
| --- | --- | --- | --- |
| Project Hong Kong | "sala do projeto HK", "sala de Hong Kong", "sala HK" | Odara, Lori (host), Cap, Marty | Project Hong Kong (Backlog quest, https://app.notion.com/p/426107b19b4981e58f5bdf10619e6ea4) |

A new saved room is a new row here plus a home page for the project (G20: the home first).

What a room is not: a simulation inside one chat, played by one model. It does not wake the Persona's own chat, give it independent access, send anything outside Odyssey or start an automation. The Captain's Deck has a stored version of the same idea ("Salas da tripulação").
