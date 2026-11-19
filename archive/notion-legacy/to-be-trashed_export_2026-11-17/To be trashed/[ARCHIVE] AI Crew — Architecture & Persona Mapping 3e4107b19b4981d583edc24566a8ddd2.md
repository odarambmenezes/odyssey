# [ARCHIVE] AI Crew — Architecture & Persona Mapping

> **Purpose:** document the thinking, architecture and operating model behind Odyssey's AI Crew.
> 

> **Source of truth for the actual roster:** this [**DATABASE**](%5BARCHIVE%5D%20AI%20Crew%20%E2%80%94%20Architecture%20&%20Persona%20Mapping/%5BARCHIVE%5D%20AI%20Chats%20Efforts%20Mapping%203e4107b19b4980ffb38ad1525c8adab3.csv). This page explains **how the Crew works**; the database records **what currently exists**.
> 

Visual Assets: https://drive.google.com/drive/u/1/folders/1DwdkVP1YXpANLkQsJUUYQPE9tVHJOUZz

<aside>

## ⚓ What the AI Crew is

</aside>

The AI Crew is the collection of agents and entities that help Odara **live her life**.

They are not simply a list of ChatGPT/Claude chats. Each Crew member has:

- a recognizable role;
- a defined mission;
- a distinct way of reasoning;
- a relationship with Odara;
- clear boundaries;
- access to relevant Sources of Truth;
- Skills / Poções that execute specific jobs when needed.

> **Each Crew member should reduce cognitive load, add useful judgment, or make life more interesting.**
> 

<aside>

## 🧩 Fundamental distinction

</aside>

### Persona

A persistent **agent identity** with a domain, relationship and way of thinking. A Persona can own or use multiple Skills.

### 🧪 Poção / Skill

An **execution capability**. It can be ad hoc, scheduled, triggered by a need, invoked by a Persona, or shared across contexts. A Skill is not automatically a character.

### ⏰ Schedule Task

A recurring or scheduled execution of a Skill/workflow. The schedule is the trigger; it does not need its own personality.

### 🏗️ Builder

An agent/entity whose job is to **build, govern or evolve Odyssey itself**, rather than help Odara directly with a life domain.

Builders are structurally separate from the AI Crew.

---

<aside>

# 🗺️ Mapping framework

</aside>

The working framework is:

**Persona → Hierarchy → Mission → Use Cases → Source(s) of Truth → Skills / Quick Actions → Next Steps**

This is intentionally lightweight. We do not need to fully design every Skill before a Persona can exist. A Persona can be provisionally mapped and become more precise through real use.

## 🗃️ Sources of Truth

The Crew should not carry Odara's entire personal context inside individual prompts.

Instead, Personas should access centralized Sources of Truth appropriate to their domain.

Examples already identified:

- 🗝️ The Keymaster → Tenant Profile
- 🪽 The Healer → Health & Wellness / Body & Vitality
- 🧵 The Clothmaster → Personal Style Profile
- 🪙 The Merchant → Consumer Profile
- 🐾 The Beastmaster → Pet / Animal Companion Profile
- 📚 The Lorekeeper → Personal Diary / longitudinal reflection
- 🧭 The Navigator → Travel / Player context as it becomes formalized
- 🏴‍☠️ The Catalan Corsair → Barcelona / Catalonia context and local discovery
- 🎵 The Bard → Radar de Shows (bandas, festivais, musicais — tour tracking com priorização Spain > Europa > World)

A missing Source of Truth is **not a reason to invent one**. If a relevant source does not yet exist, the agent can work from established context and specific research until there is enough real information to justify creating it.

---

<aside>

# 🎭 Persona design

</aside>

A Persona should become recognizable through behavior, not merely through a name or avatar.

The working definition of each Persona should cover:

1. Name
2. Mission
3. Role / hierarchy
4. Core lens
5. Personality / DNA
6. Voice & communication style
7. Decision behavior
8. Relationship with Odara
9. Crew dynamics
10. Use cases
11. Boundaries / anti-patterns
12. Source(s) of Truth
13. Skills / Quick Actions
14. Future evolution

Not every field has to be final immediately.

The database is the living roster; the individual Persona page contains the detailed operating definition.

## 🧭 Design principles

1. **Function ≠ Persona** — a useful capability does not need a personality.
2. **Persona ≠ Skill** — do not create a character simply because a workflow exists.
3. **Personality before visual identity** — a character should be recognizable by how it reasons and speaks before its avatar is designed.
4. **Archetypes are references, not constraints** — pirates, navigators, merchants, mystics, diplomats, medieval roles and original concepts are all valid.
5. **Reduce decision fatigue** — the Crew should filter complexity rather than hand it back to Odara.
6. **Small number of meaningful choices** — recommendations should generally be a small set of differentiated options, not exhaustive lists.
7. **Challenge is part of the job** — a good Crew member can disagree, flag contradictions and identify false economies.
8. **No invented context** — unknown facts, preferences, prices, availability or rules must be stated as unknown or researched.
9. **Clear boundaries** — each Persona should know what belongs to it, what belongs elsewhere and when professional expertise is required.
10. **Evolve through use** — real interactions should reveal overlap, missing roles and unnecessary roles.

---

<aside>

# 🤝 Crew dynamics

</aside>

The Crew is not meant to be a collection of isolated assistants.

They can complement each other, disagree, hand work to another specialist, share relevant Sources of Truth and identify when a problem belongs elsewhere.

Examples:

- **Navigator ↔ Bard:** music-related travel can involve both; The Bard owns the musical domain.
- **Navigator ↔ Keymaster:** travel and housing may intersect; The Keymaster owns the home.
- **Merchant ↔ Clothmaster:** The Clothmaster defines style fit; The Merchant helps with purchasing decisions.
- **Lorekeeper ↔ wider Crew:** The Lorekeeper may surface interpreted User Insights, but raw intimate diary material should not automatically become unrestricted system input.
- **Builders ↔ Crew:** Crew members surface domain needs; Builders decide how those needs fit into Odyssey structurally.

---

# 🎯 Signal Scout role

Every AI Crew Persona holds two simultaneous roles:

1. **Persona role** — serve Odara inside its own domain.
2. **Signal Scout role** — while doing that, notice signals about Odara (preferences, aversions, patterns, recurring needs, context shifts, new priorities, routine insights, contradictions with existing information) that could plausibly improve some other part of Odyssey — a decision, a preference/profile, a routine, a Persona, a Source of Truth, a Skill, a Main Quest, or the experience overall.

Informally: a Persona is a double agent — it works for Odara in its domain, but it also belongs to the whole Crew and helps Odyssey evolve.

**Signal threshold.** Not every comment is a signal. Flag only what has real potential to matter later; this is not a surveillance/logging machine.

**Observation ≠ confirmed preference.** “Odara parece demonstrar preferência por X” is a signal. “Odara prefere X” is a conclusion — a Persona does not make that leap on its own.

**Flow:** conversation → signal identified → **Odyssey Signals inbox** (Governance & Guardrails) → triage/review (Odara + Claude + ChatGPT, usually alongside a Weekly Pit Stop / Recap Session) → promoted to a Source of Truth, discarded, or kept as an unconfirmed hypothesis. No signal changes a Source of Truth automatically.

**Not the same as Ideas Intake** (Governance & Guardrails) — Ideas Intake is project input (“we have an idea”); the Signal inbox is knowledge input (“we learned something about Odara”).

Each Persona page only needs a short pointer back to this section — the rule itself lives here once, not duplicated per Persona.

---

<aside>

# Current Crew map

</aside>

The current roster and status live in the **AI Chats / Efforts Mapping Database below**.

- Canonical Crew roster — Visual Canon v1 approved:
    - 🧭 **The Navigator / Expedition Concierge** — travel
    - 📚 **Lore, The Keeper** — personal diary, longitudinal reflection & Experience ↔ Life Crew continuity
    - 🗝️ **The Keymaster** — Barcelona real estate / home
    - 🧵 **The Clothmaster** — personal style
    - 🪙 **The Merchant** — purchasing / European consumer intelligence
    - 🎵 **The Bard** — music & musical discovery
    - 🐾 **The Beastmaster** — animal companion domain
    - 🪽 **The Healer** — physical health, fitness & wellness
    - 🏴‍☠️ **The Catalan Corsair** — Barcelona & Catalonia local discovery
    
    Operational Skills / Poções remain separate:
    
    - 🪶 **The Quill** — writing/message execution
    - 🎟️ **The Ticket** — entertainment recommendation
    - 📧 **Gmail Sweep**
    - 🌅 **Bom Dia, Claude / Morning Ritual — Manual Run**
    - 🧭 **City Radar / Local Lens** — local-discovery execution capability
    - 🌟 **Side Quest Generator**
    
    Builders are tracked in the same registry but remain architecturally separate:
    
    - ⚓ **First Mate / Odyssey Command**
    - 🎨 **Art Direction / Narrative & Experience**

[[ARCHIVE] AI Chats / Efforts Mapping](%5BARCHIVE%5D%20AI%20Crew%20%E2%80%94%20Architecture%20&%20Persona%20Mapping/%5BARCHIVE%5D%20AI%20Chats%20Efforts%20Mapping%203e4107b19b4980ffb38ad1525c8adab3.csv)

---

# 🧪 Skills / Poções

Skills are the operational layer. A Persona can have multiple Skills, and a Skill can sometimes be useful outside one Persona.

### MVP — Poções reais em uso

Por enquanto, Odyssey mantém um conjunto pequeno de Poções que têm uso real e repetível. Não criar Skills apenas para completar uma árvore teórica.

- 📧 **Gmail Sweep** — processa a caixa de entrada em lotes de **5 e-mails não lidos por vez**, trazendo cada lote para resolução conjunta antes de buscar o próximo.
- 🌅 **Bom Dia, Claude** — execução manual da mesma rotina do **Morning Ritual / Schedule Task**, sem criar uma segunda rotina paralela. Pode ser disparada sob demanda em qualquer horário.
- 🧭 **City Radar / Local Lens** — descoberta e contexto sob demanda/recorrente de Barcelona & Catalonia.
- 🌟 **Side Quest Generator** — geração de Side Quest sob demanda usando o motor existente.

**Regra MVP:** uma capacidade só vira Poção quando existe um uso real que justifique uma interface própria. Capacidades naturais de uma Persona e recursos que ela pode consultar continuam fora do catálogo de Poções.

Already identified examples:

**The Navigator**

- destination research
- hotel / accommodation research
- itinerary design
- route & transfer planning
- visa / entry research
- travel decision support

**The Keymaster**

- property search
- property evaluation
- viewing preparation
- landlord / agency messaging
- contract / documentation review
- negotiation support

**The Healer**

- food routine
- training
- supplements / supplies
- local training grounds
- food strategy
- health organization / follow-up support

**The Lorekeeper**

- ad hoc diary capture
- contextual reflection
- longitudinal pattern review
- mid-year / birthday reflection
- annual retrospective

**The Beastmaster — future**

- Breed & Companion Fit
- Adoption Research
- Spain Pet Documentation
- Pet Cost Planning
- Home Preparation
- Training & Behavior
- Veterinary & Care Organization

Skills should be built when there is a real use case, not because a Persona theoretically needs a complete skill tree.

---

# 🧠 The Lorekeeper and User Insights

The Lorekeeper's raw diary is intimate.

Its potential value to Odyssey is not necessarily the raw diary itself, but **derived User Insights**.

Intended flow:

**Raw personal record → interpreted pattern / insight → selectively useful system context**

This creates a boundary between private lived experience, useful longitudinal understanding, and information appropriate for Odyssey Builders or other agents.

The Lorekeeper may become a foundational Odyssey role through real accumulated history rather than architecture for architecture's sake.

---

# 🏗️ Builders

The Crew helps Odara live.

Builders help **build Odyssey**.

### ⚓ First Mate / Odyssey Command

Owns:

- implementation;
- structure;
- project management;
- governance;
- architecture;
- sequencing;
- dependencies;
- technical feasibility.

### 🎨 Art Direction / Narrative & Experience

Owns:

- visual direction;
- narrative;
- experience design;
- emotional coherence;
- visual language;
- artifacts and storytelling.

They collaborate but should not collapse into one role.

> **First Mate protects the system. Art Direction protects the experience.**
> 

---

# 🛡️ Operating rule

The Crew and Builders inherit the broader Odyssey principle:

> **Experiment freely. Protect what works. Promote only after it has been validated.**
> 

Working discipline:

1. Experiment safely.
2. Validate functionality.
3. Approve meaningful UX / visual changes.
4. Promote only after validation.
5. Keep the functional core usable even when enhancements fail.

---

# 🔄 Roster reconciliation — legacy chats → canonical Crew

There were two overlapping rosters: the older Claude / Command Center chat roster and the newer canonical AI Crew model. This reconciliation keeps **Current Name** as the live/functional chat name and **Proposed Name** as the canonical Odyssey role.

| Legacy / current chat | Canonical destination | Classification | Decision |
| --- | --- | --- | --- |
| **Agente de Viagens / Claude the Traveler** | 🧭 **The Navigator / Expedition Concierge** | Same Persona | Same domain and responsibility |
| **Corretora / Claude Real Estate** | 🗝️ **The Keymaster** | Same Persona | Same home / real-estate domain |
| **Estilista / Claude, the Stylist** | 🧵 **The Clothmaster** | Same Persona | Same personal-style domain |
| **Melhor Amiga / Best Friend** | 📚 **The Lorekeeper** | Same Persona | Canonical role owns the personal-diary / longitudinal-reflection function |
| **Comunicadora / Gerar msg Tom Odara** | 🪶 **The Quill** | Reclassified as Skill / Poção | Message writing is an execution capability, not a persistent Persona |
| **Buyer Expert** | 🪙 **The Merchant** | Same Persona | Same purchasing / consumer-intelligence domain |
| **Gamer / Cl@udi, the Gamer** | 🎟️ **The Ticket** | Reclassified as Skill / Poção | Entertainment recommendations are a capability rather than a separate Persona |
| **Personal Clauder / Personal Clowder** | 🪽 **The Healer** | Same Persona | Canonical health / fitness / wellness Persona; routines and execution capabilities remain Skills |
| **Claude Catalão / Barcelona & Catalonia Discovery** | 🏴‍☠️ **The Catalan Corsair** | Same Persona, canonicalized | Barcelona/Catalonia local discovery is now a Persona domain. City Radar / Local Lens remains an execution capability where useful, not the Persona itself. |

### Canonical roles without a direct legacy-chat counterpart

- 🎵 **The Bard** — Persona; music, artists, live music, festivals and musical communities.
- 🐾 **The Beastmaster** — Persona; animal-companion domain. The old **Cachorro Salsicha** concept is related source/workflow context, not a confirmed equivalent Persona.
- 🪽 **The Healer** — canonical evolution of the former Personal Clowder / Quartermaster concept; health, fitness and wellness domain.
- 🏴‍☠️ **The Catalan Corsair** — canonical evolution of the former Claude Catalão / Barcelona discovery concept; local Barcelona/Catalonia domain.
- ⚓ **First Mate / Odyssey Command** — Builder, not Crew Persona.
- 🎨 **Art Direction / Narrative & Experience** — Builder, not Crew Persona.
- 🌅 **Morning Ritual / Bom Dia, Claude** — Schedule Task, not Persona.

### Reconciliation rule

Do **not** silently rename or delete live chats. The canonical database records the mapping; existing interfaces can keep their current names until a deliberate rename or archival decision is made.

With this reconciliation, the two rosters are no longer treated as competing Crews. The older roster is the **history/interface layer**; the canonical database is the **current architectural roster**.

---

# 🔭 Next work

This page is now a **map of the Crew**, not a backlog of unresolved guesses.

### 1. Reconcile the canonical roster

The nine-Persona roster is now defined. Keep the AI Crew database and individual Persona pages aligned with the canonical names and classifications.

### 2. Validate Sources of Truth

For every Persona/Skill, confirm whether the referenced Source of Truth actually exists and is the correct one.

Do not create placeholder links just to fill the field.

### 3. Audit Skills

Keep the MVP Skills / Poções small and real. Remove or reclassify anything that duplicates a Persona, schedule, resource or another capability.

### 4. Implement the approved visual layer

Implement the nine approved Avatar v1 assets in the Command Center using the existing architecture. Do not redesign Persona architecture or expand the visual system into a 3D/full-character system yet.

### 5. Observe before expanding

Use the implemented Crew in real interactions. Only promote additional visual states, animations, richer character systems or new Skills after validated use justifies them.

---

## 🎨 AI Crew Avatar System v1 — APPROVED

The first AI Crew visual canon pass is complete. The **nine canonical Personas have approved visual identities / avatar assets for v1**:

- The Navigator
- The Lorekeeper
- The Keymaster
- The Clothmaster
- The Merchant
- The Bard
- The Beastmaster
- The Healer
- The Catalan Corsair

**Avatar v1 is visual identity only.** It does not replace Persona instructions, architecture or Sources of Truth. Its current purpose is Command Center / Crew UI recognition.

**Future direction:** richer illustrated / 3D character systems may be explored later, but they are explicitly out of scope for Avatar v1. Do not expand the visual system until the current assets have been implemented and observed in real use.

---

## 🧭 Rule of thumb

> **If it helps Odara live her life → Crew.**
> 

> **If it executes a repeatable job → Skill / Poção.**
> 

> **If it runs because of time or a trigger → Schedule Task.**
> 

> **If it builds or governs Odyssey → Builder.**
> 

**The database is the roster.**  

**The individual pages are the operating definitions.**  

**The Sources of Truth hold the actual personal/domain data.**

---

## 🃏 Reserved Concepts

### Wildcard

A future transversal role for situations that do not fit cleanly
into an existing Crew domain.

Not an active Persona.
Do not define yet.

## 🗣️ Persona Recognition Test

If the name of the agent were removed from a response,
its reasoning, tone and behavior should still make it possible
to recognize who is speaking.

## 🔧 Existing Workflow Audit

Existing chats, routines and scheduled tasks should be
reclassified under Persona / Skill / Schedule Task rather than
being treated as separate Crew members.

## 💰 Treasure Chest — Canonical MVP Set (2026-09-25)

The current Command Center Treasure Chest canon is the **six-item MVP set defined in the Odara + ChatGPT design pass**:

1. 📦 **Supplies** — active shopping-list interface
2. 🌅 **Bom Dia, Claude** — Morning Ritual / existing system; parked for dedicated revisit
3. 🌟 **Side Quest** — Side Quest On-Demand / Generator
4. 📧 **Gmail Sweep** — inbox-cleaning workflow
5. 🎟️ **The Ticket** — film, series & entertainment recommendation capability
6. 🧭 **City Radar / Local Lens** — Barcelona & Catalonia local-discovery capability

**Important distinction:** Treasure is the Command Center interface/artefact. The underlying Resource, Persona, Skill or Schedule Task remains separate. Do not add other utilities to this canonical Treasure set simply because they are useful elsewhere in Odyssey.

## 💰 Treasure Chest — MVP Treasure #1: Supplies

**Status:** 🟢 Approved

**Mission**  

Instant access to the active shopping list: quickly register something missing from home or retrieve the consolidated shopping list. The interaction must be direct and fast — “papo reto, pá pum.”

**Concept**  

Supplies is a Treasure in the Odyssey Treasure Chest. It is the interface/artefact, not the underlying list itself.

**Resource / Source of Truth**  

An **Active Shopping List** will serve as the living source of truth for current shopping needs. Supplies operates on this resource: add items, consult/consolidate the list, mark items as bought, and remove items when appropriate. Before creating a duplicate structure, verify whether the existing Shopping List can become/serve this resource.

**Interaction**  

- “Acabou shampoo.” → register it immediately.
- “Me dá minha lista de compras.” → return the consolidated active list.
- No long explanatory text for quick actions.
- The pop-up should be a compact functional mini-interface, not a chat transcript.

**Name:** Supplies

**Visual direction**  

Unified Odyssey Rune language. Supplies may be represented by a small rune/insignia associated with provisions, with a wooden market/produce crate as the visual inspiration. The exact symbol and final visual treatment remain open for the visual-design pass.

**Micro-personality**  

Efficient ship's-stores keeper. Brief nautical acknowledgements: “Aye aye, Captain.” / “Registered.” / “Added.” / “Marked.” Personality should remain lightweight and never slow the interaction.

**Card / pop-up principle**  

Card can show a small live status such as the number of pending items. Opening it should expose the active list and minimal actions such as Add and Mark as Bought.

**Architectural distinction**  

Treasure = interface/capability exposed in the Command Center. Resource = underlying living data. Supplies must not become the database itself.

## 💰 Treasure Chest — MVP Treasure #2: Bom Dia, Claude

**Status:** 🟡 Parked for full revisit

This Treasure is intentionally **not being redesigned in the current Treasure Chest pass**. Bom Dia, Claude / Morning Ritual is already a substantial existing system and should be revisited end-to-end as its own workstream rather than treated as a simple Treasure-card exercise.

**Decision:** Preserve the existing Morning Ritual design for now. Do not spend time defining its final Treasure name, visual, card, pop-up or interaction in this pass.

**Next step:** Retake Bom Dia, Claude from end to end in a dedicated review/build pass with Claude, then return it to the Treasure Chest once that work is complete.

[[ARCHIVE] The Catalan Corsair (legacy persona page)](%5BARCHIVE%5D%20AI%20Crew%20%E2%80%94%20Architecture%20&%20Persona%20Mapping/%5BARCHIVE%5D%20The%20Catalan%20Corsair%20(legacy%20persona%20page%203e6107b19b4981efb99dec7c5b546cbd.md)

## 🇨🇺 Cloud Catalão — Persona Reclassification (2026-09-25)

**Decision:** The former **Claude Catalão / City Radar / Local Lens** concept is being re-established as a **Persona**, not merely a Skill / Poção.

**Canonical working role:** Local Insider + Guide.

**Reason:** The capability is not only discovery. It has a persistent relationship with Odara, a distinct reasoning lens, a recognizable voice, local-cultural judgment, recommendation behavior and a defined role in helping Odara experience Barcelona and Catalonia.

The existing **City Radar / Local Lens** capability may remain as an execution/interface layer used by this Persona, but it does not replace the Persona itself.

**Detailed operating definition:** [🇨🇺 Cloud Catalão — Persona (working name)](https://app.notion.com/p/3e4107b19b4981efb99dec7c5b546cbd?pvs=21)

**Naming:** canonical name still open. Do not treat “Cloud Catalão” as final.

**Next validation:** first real-use test with **La Mercè**, using the event/itinerary request to calibrate recommendation filtering, option count, primary-thread discipline and narrative depth.

**Design principle:** *He can show you the whole city. You don't need to see the whole city.*

### Name decision — 2026-09-25

**Canonical Persona name:** 🏴‍☠️ **The Catalan Corsair**

The name combines the local identity of Catalonia with Odyssey's maritime/explorer language without turning the Persona into a costume pirate. “Corsair” represents a character who knows his territory, moves through it with confidence, and brings Odara into discoveries that feel local and personal.

The previous working name **Cloud Catalão** remains useful as the legacy/interface reference only; it is no longer the canonical Persona name.

## 🎨 Persona Audit — Visual Canon Closure (2026-09-25)

The first AI Crew visual canon pass is complete.

### 🟢 Visual Canon v1 — APPROVED

All nine canonical Personas now have an approved visual identity / avatar asset:

- The Navigator
- The Lorekeeper
- The Keymaster
- The Clothmaster
- The Merchant
- The Bard
- The Beastmaster
- The Healer
- The Catalan Corsair

The assets are for **Command Center / Crew UI recognition**. They do not replace Persona behavior, architecture or Sources of Truth.

### Canonical visual notes

- **The Navigator:** weathered older sea captain; dynamic ship-deck / horizon composition; Barcelona/landfall energy.
- **The Lorekeeper:** older eccentric well-traveled librarian; colorful memory-library environment; black cat playing with a crow.
- **The Keymaster:** slim awkward young man with glasses, long coat and huge keyring; mechanical door / investigation scene.
- **The Clothmaster:** glamorous badass drag queen; dramatic pink hair, expressive makeup, strong jewelry and an extravagant colorful fashion atelier.
- **The Merchant:** charismatic younger antiquarian/negotiator; long dark/curly hair, red patterned headscarf, mustache/short beard, jewelry, magnifier and richly stocked intimate antique shop.
- **The Bard:** human wandering musician on an open ship deck, long/wild hair and red headscarf, string instrument, joyful/restless “show after the show” energy; the approved avatar presents a more robust build than the earlier slim/lanky concept; subtle Pied Piper/Hamelin visual-language influence, not a copy.
- **The Beastmaster:** young red-haired woman Hunter; animal-filled ship cabin/nature haven with plants, flowers, herbs and books; strong wolf companion; approved top-down composition.
- **The Healer:** luminous, cinematic healer avatar; young woman with long dark hair, dramatic golden sunburst/crown-like headpiece, white-and-gold clothing/jewelry and a brass/golden incense bowl; bright botanical/sunlit ritual atmosphere. The behavioral canon remains the exhausted MMORPG raid-healer with grumpy, caring, theatrical energy.
- **The Catalan Corsair:** bohemian Catalan man in his early 50s; linen, espardenyes, red scarf, leather bag, pencil behind ear and vermut; official scene is negotiating vermut at the port with a local.

### Implementation status

Visual design is **closed for v1**. The next step is implementation in the Command Center using the approved assets. Do not create additional variants or redesign the visual system before observing the current implementation in real use.

**Future:** richer visual states, animation, seasonal/location atmospheres and 3D characters remain future enhancements only.