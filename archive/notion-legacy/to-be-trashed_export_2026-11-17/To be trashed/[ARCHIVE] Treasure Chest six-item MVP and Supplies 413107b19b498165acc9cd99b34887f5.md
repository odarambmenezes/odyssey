# [ARCHIVE] Treasure Chest six-item MVP and Supplies spec (25 Sep 2026)

<aside>
🗄️

Archived 09 Nov 2026 by Odara's decision. This is history, not current instructions. The Command Center history already records a later nine-item Treasure Chest (26 Sep 2026). Moved here verbatim from Reconciliation needed.

</aside>

## 💰 Treasure Chest — Canonical MVP Set (2026-09-25)

The current Command Center Treasure Chest canon is the **six-item MVP set defined in the Odara + ChatGPT design pass**:

1. 📦 **Supplies** — active shopping-list interface
2. 🌅 **Bom Dia, Claude** — Morning Ritual / existing system; parked for dedicated revisit
3. 🌟 **Side Quest** — Side Quest On-Demand / Generator
4. 📧 **Gmail Sweep** — inbox-cleaning workflow
5. 🎟️ **The Ticket** — film, series & entertainment recommendation capability
6. 🧭 **City Radar / Local Lens** — Barcelona & Catalonia local-discovery capability

**Important distinction:** Treasure is the Command Center interface/artefact. The underlying Resource, Persona, Skill or Schedule Task remains separate. Do not add other utilities to this canonical Treasure set simply because they are useful elsewhere in Odyssey.

---

## 💰 Treasure Chest — MVP Treasure #1: Supplies

**Status:** 🟢 Approved

**Mission:** Instant access to the active shopping list: quickly register something missing from home or retrieve the consolidated shopping list. The interaction must be direct and fast — “papo reto, pá pum.”

**Concept:** Supplies is a Treasure in the Odyssey Treasure Chest. It is the interface/artefact, not the underlying list itself.

**Resource / Source of Truth:** An **Active Shopping List** will serve as the living source of truth for current shopping needs. Supplies operates on this resource: add items, consult/consolidate the list, mark items as bought, and remove items when appropriate. Before creating a duplicate structure, verify whether the existing Shopping List can become/serve this resource.

**Interaction:**

- “Acabou shampoo.” → register it immediately.
- “Me dá minha lista de compras.” → return the consolidated active list.
- No long explanatory text for quick actions.
- The pop-up should be a compact functional mini-interface, not a chat transcript.

**Name:** Supplies

**Visual direction:** Unified Odyssey Rune language. Supplies may be represented by a small rune/insignia associated with provisions, with a wooden market/produce crate as the visual inspiration. The exact symbol and final visual treatment remain open for the visual-design pass.

**Micro-personality:** Efficient ship's-stores keeper. Brief nautical acknowledgements: “Aye aye, Captain.” / “Registered.” / “Added.” / “Marked.” Personality should remain lightweight and never slow the interaction.

**Card / pop-up principle:** Card can show a small live status such as the number of pending items. Opening it should expose the active list and minimal actions such as Add and Mark as Bought.

**Architectural distinction:** Treasure = interface/capability exposed in the Command Center. Resource = underlying living data. Supplies must not become the database itself.