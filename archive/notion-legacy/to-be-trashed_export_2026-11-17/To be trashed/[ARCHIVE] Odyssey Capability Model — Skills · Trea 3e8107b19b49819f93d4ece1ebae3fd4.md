# [ARCHIVE] Odyssey Capability Model — Skills · Treasures · Workflows · Tasks

> **Status: 🟢 Approved foundation — 2026-09-27**
> 

> This model defines what operational capabilities and execution mechanisms are in Odyssey. It does not by itself create new databases, Command Center UI, or integrations.
> 

## 1. Core model

| Concept | Definition | Core question |
| --- | --- | --- |
| 🧪 **Skill** | A repeatable operational capability Odyssey can execute. | What can Odyssey do? |
| 🗝️ **Treasure** | A Skill, or small group of Skills, exposed as an ad-hoc invocable tool. | What can I open/use now? |
| ⚙️ **Workflow** | A coordinated sequence of operations, usually involving multiple Skills, steps, Personas, or systems. | How do several capabilities work together? |
| ⏳ **Task** | A scheduled or triggered execution of a Skill or Workflow. | When does this need to happen? |
| 🧙 **Persona** | A persistent perspective/domain with identity, judgment, relationship, and expertise. | Who helps think about this? |
| 🛠️ **Builder** | A role with authority to construct, alter, or govern Odyssey itself. | Who can change the system? |

### Canonical shorthand

**Skills are capabilities.**  

**Treasures are invocable capabilities.**  

**Workflows are orchestrated sequences.**  

**Tasks are scheduled/triggered executions.**  

**Personas provide perspective.**  

**Builders shape the system.**

## 2. Skill

A Skill is the operational capability itself. It does not need a UI, a Treasure, a dedicated Persona, or a scheduled execution.

A Skill may be:

- used by a Persona;
- exposed through a Treasure;
- executed by a Task;
- included in a Workflow;
- kept internal when no dedicated interface is justified.

**MVP rule:** do not create Skills just to complete a theoretical capability tree. Build/promote them when a real use case exists.

## 3. Treasure

A Treasure is an ad-hoc entry point into one or more Skills.

**Treasure ≠ Resource.**  

**Treasure ≠ Persona.**  

**Treasure ≠ the underlying data.**

Example:

- Shopping List = Resource / Source of Truth
- Add-item capability = Skill
- **Supplies = Treasure**

A Treasure exists when the capability benefits from being explicitly discoverable and invocable in the Odyssey Command Center or another user-facing surface.

## 4. Workflow

A Workflow is the process layer. It coordinates multiple operations toward a result.

A Workflow may use:

- Skills;
- Personas;
- Sources of Truth;
- external systems;
- approved internal actions.

The same Workflow may have more than one entry point.

Example:

**Bom Dia Claude Workflow**

→ can be started by a scheduled Task  

→ can also be started manually/ad hoc.

The workflow should not be duplicated merely because its trigger changes.

**MVP rule:** document workflows before building dedicated workflow infrastructure. Create a separate workflow system only when real use justifies it.

## 5. Task

A Task is an execution that occurs because of a defined time, recurrence, or trigger.

A Task is **not synonymous with a notification or delivery to Odara.**

A Task may be:

### User-facing

A result is delivered to Odara.

- 08:00 → run Bom Dia Claude.

### Internal

The system performs maintenance without interrupting Odara.

- Daily → reconcile recurring Backlog items.

### Bridge

A task coordinates information or execution across Odyssey components or AI systems.

- ChatGPT produces an input → approved destination receives it → Claude uses it in a later workflow.

### Triggering

The task starts a larger workflow.

- Sunday → start Weekly Recap workflow.

**Core rule:** A Task may work *for* Odara without necessarily speaking *to* Odara.

## 6. Trigger

Trigger is a supporting concept, not a standalone Odyssey category in MVP.

A Task may be triggered by:

- a specific time;
- a recurrence;
- a condition;
- an approved event/state change.

Trigger is therefore an attribute/mechanism of a Task, not a seventh core entity.

## 7. Internal and cross-system Tasks

Scheduled Tasks may operate internally and may coordinate ChatGPT, Claude, Notion, or other explicitly authorized systems.

They may:

- execute established capabilities;
- query approved Sources of Truth;
- transform information;
- pass information between approved systems;
- update authorized live data;
- start approved Workflows;
- prepare information for later use.

They do **not** gain structural authority merely because they are automated.

They may not silently:

- redesign architecture;
- change taxonomy;
- alter governance;
- create structural categories;
- promote hypotheses into facts;
- expand their own permissions.

This preserves the canonical trust boundary:

> **Knowledge is shared. Execution is delegated. Structural authority is restricted.**
> 

## 8. Relationships

A single Skill may have multiple execution surfaces:

**Skill → Treasure**  

Ad-hoc human invocation.

**Skill → Task**  

Scheduled/triggered execution.

**Skill → Workflow**  

Use as one operation within a larger process.

**Workflow → Task**  

A Task starts a Workflow.

**Workflow → Treasure**  

A Treasure can provide an ad-hoc entry point into a Workflow.

**Persona → Skill**  

A Persona may own, use, or provide judgment around a Skill.

**Persona → Workflow**  

A Workflow may involve one or more Personas.

**Builder → System**  

Builders have structural authority over Odyssey itself.

## 9. Examples

| Existing Odyssey concept | Recommended classification |
| --- | --- |
| Email processing | Skill |
| 📧 Gmail Sweep | Treasure |
| Side Quest generation | Skill |
| 🌟 Side Quest | Treasure |
| Entertainment recommendation | Skill |
| 🎟️ The Ticket | Treasure |
| Barcelona discovery | Skill(s) |
| 🧭 City Radar / Local Lens | Treasure / execution surface |
| Shopping List | Resource / Source of Truth |
| 📦 Supplies | Treasure |
| Bom Dia Claude logic | Workflow |
| 🌅 Bom Dia Claude manual run | Ad-hoc entry point / Treasure |
| 🌅 Bom Dia Claude scheduled run | Task |
| Daily Backlog revival | Task |
| Weekly Recap process | Workflow |
| The Navigator | Persona |
| Odyssey Mayor / First Mate | Builder |

This table is a **classification starting point**, not yet the final audit of every existing Odyssey routine.

## 10. Design rules

1. **Do not create a new category when an existing one explains the behavior.**
2. **Do not turn every Skill into a Treasure.**
3. **Do not turn every Workflow into a Task.**
4. **A schedule does not define the capability; it defines when it executes.**
5. **A Treasure is an entry point, not the underlying data.**
6. **One Workflow should support multiple valid entry points when possible.**
7. **Automation can be internal; user-facing delivery is optional.**
8. **Tasks may coordinate systems, but automation does not grant structural authority.**
9. **Notion remains the canonical Source of Truth for live Odyssey data.**
10. **Experiment freely. Protect what works. Promote only after validation.**

## 11. What this changes

The old mental model tended to mix:

- the capability itself;
- the interface used to invoke it;
- the scheduled execution;
- and the process coordinating several capabilities.

The new model separates those layers without requiring a large new architecture.

This means Odyssey can grow from:

**“things I can ask Claude to do”**

into:

**capabilities → usable tools → orchestrated workflows → scheduled/internal execution**

without turning every new idea into another Persona, Skill, or Command Center button.

## 12. Implementation boundary

This document is the **conceptual foundation**.

It does not authorize:

- creation of new databases;
- Command Center redesign;
- new Treasures;
- new Personas;
- new integrations;
- automatic migration of existing records.

Those come only after the existing Odyssey is audited against this model.

### Next approved phase

**Capability Audit**

1. Audit existing Skills / Poções.
2. Audit current Treasure Chest.
3. Audit existing Scheduled Tasks.
4. Identify existing Workflows.
5. Reclassify ambiguous items.
6. Identify only the minimum structural changes required.
7. Update Codex / Governance / AI Crew Architecture / Playbook as needed.
8. Only then implement Command Center or integration changes.

> **The goal is not to make Odyssey more complex.**
> 

> 
> 

> **The goal is to make it easier to understand what Odyssey can do, when it does it, and how its parts work together.**
>