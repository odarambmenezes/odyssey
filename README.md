# Odyssey — backup, archive and Builder workspace

Private repository of **Project Odyssey**, Odara's personal Life Operating System.

## ⚠️ Notion is the source of truth
Everything current lives in Notion (Project Odyssey). This repository never competes with it:

| Folder | What it is | Use it when |
|---|---|---|
| `notion-snapshot/` | Point-in-time copy of the core documentation pages and the schema of the core databases | Notion is unreachable (Operating Manual G16), or to compare structure over time |
| `archive/` | Legacy material removed from Notion, never current instructions | Tracing why something was decided or what existed before |
| `CHANGELOG.md` | Log of every structural session done by a Builder | Auditing what changed in the structure, when and why |
| `AGENTS.md` / `CLAUDE.md` | Instructions for Builder environments (Codex, Claude Code) | Automatically read at the start of every Builder session |

If a file here disagrees with Notion, **Notion wins**: the snapshot may simply be older.

## How it is updated
Structure in Notion changes only in a Builder environment (Claude Code or Codex), after reconciling with the live documentation (Operating Manual G21). Every structural session ends with:
1. a fresh `notion-snapshot/`,
2. a `CHANGELOG.md` entry,
3. one commit, so the diff shows exactly what changed.

A structural change that appears in a snapshot diff without a matching changelog entry was made outside a Builder environment and must be reviewed.

## Privacy (G22)
Private repository. The snapshot leaves out the Diário Pessoal, health and finance content until Odara decides otherwise. The archive holds older personal material, approved by Odara on 19 Nov 2026.
