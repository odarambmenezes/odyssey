# [ARCHIVE] City Radar & Local Lens (old Barcelona Discovery design)

<aside>
⚓️

**Purpose:** Help Odara discover Barcelona as a place she is actually building a life in — not simply as a tourist.

</aside>

## 🗺️ Architecture

This is a **Main Quest support system**, not an AI Crew persona.

The former **Claude Catalão / The Local** concept is being split into focused capabilities:

- **City Radar** → proactive recurring discovery
- **Local Lens** → on-demand context + personal fit check

Core principle:

> **Local importance ≠ Odara relevance.**
> 

The system should not surface something merely because it is culturally important, popular, or “what locals do.” It should explain the context, then filter for what is plausibly interesting to Odara.

## 📡 City Radar

**Type:** Recurring Skill / Automation  

**Suggested cadence:** Every 2 weeks, adjustable after testing.

### Mission

Scan Barcelona and, when relevant, Catalonia for newly announced or upcoming experiences that Odara is genuinely likely to enjoy or find meaningful.

### What it looks for

- Festivals and local celebrations
- Cultural events and exhibitions
- Neighborhood events
- Interesting one-off experiences
- Local traditions and holidays
- Events that offer genuine opportunities to explore the city
- International / multicultural experiences
- Unexpected discoveries that fit Odara's interests

### Curation rules

The Radar should:

1. Research broadly.
2. Filter aggressively.
3. Return only a small, curated set.
4. Explain **why each item made the cut**.
5. Distinguish between:
    - **🔥 Likely your thing**
    - **🟡 Interesting, but with caveats**
    - **👀 Wildcard**
    - **🇨🇺 Local context worth knowing, even if the event itself is probably not her thing**
6. Avoid treating “important local tradition” as a reason by itself to recommend attendance.
7. Learn from feedback: what Odara attends, skips, loves, dislikes, and why.

### Personalization inputs

The Radar should eventually use relevant Odyssey Sources of Truth, especially:

- Main Quest / Barcelona life context
- Bard's Songbook / cultural & music interests
- Personal Style Profile where relevant
- Other established preferences and blockers

## 🪄 Local Lens

**Type:** On-demand Potion / Skill

### Use case

Odara encounters something organically — a poster, event announcement, street celebration, festival, neighborhood tradition — and asks:

> “What is this? Is it actually my thing?”
> 

### Response should cover

**What it is**

- What the event/tradition/activity actually is.

**Why it matters**

- Relevant history, cultural context, or local meaning.

**What it is like in practice**

- Atmosphere
- Music / programming
- Audience
- Scale
- What someone actually does there

**Odara Fit**

- How well it matches her known interests and preferences.
- Potential blockers or mismatches.
- Whether it seems worth her time, and *why*.

The system should **alert, not presume**. If something contains a known blocker or possible mismatch, explain it without spoilers where applicable and let Odara decide.

## 🧭 Guiding Principle

> **The goal is not to make Odara “do local things.” The goal is to help her discover which parts of Barcelona can become part of her life.**
> 

## 🔗 Relationship to other systems

**The Bard** owns music discovery, artists, live music, festivals, musical communities and music-related travel opportunities.

**Barcelona & Catalonia Discovery** owns broader local integration and cultural discovery.

When an event overlaps, the systems can inform each other rather than duplicate the same responsibility.

## 📝 Next Steps

- [ ]  Define the exact City Radar output format.
- [ ]  Test one manual Radar run before automating.
- [ ]  Define the Sources of Truth it may access.
- [ ]  Build the Local Lens prompt/skill.
- [ ]  Establish feedback loop so the Radar learns from real attendance and reactions.
- [ ]  Decide whether the old Claude Catalão chat remains useful as an interface or becomes a legacy chat.