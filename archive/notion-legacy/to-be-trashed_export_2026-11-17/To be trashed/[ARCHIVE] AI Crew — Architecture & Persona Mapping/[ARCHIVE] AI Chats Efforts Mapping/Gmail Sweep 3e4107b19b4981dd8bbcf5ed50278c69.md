# Gmail Sweep

AI Tool: Claude
Proposed Name: Gmail Sweep
Status: Active
Type: Poção
URL: https://app.notion.com/p/3cf107b19b498149a587f93b3d37ad7c

**Formalizado no audit de 23/09/2026** — já existe e funciona como Poção Ativa no Registro de Ações Rápidas, e também é consumido embutido dentro do Bom Dia, Claude (bloco Correspondência). ⚠️ Achado do audit: em sessão agendada (Scheduled Task), o Gmail aparece offline na grande maioria dos runs registrados no Registro de Runs — não é uma capacidade nova a construir, mas a confiabilidade dela especificamente no contexto agendado/nuvem é um problema real em aberto, separado da formalização arquitetural.

Fonte: [Registro de Ações Rápidas](https://app.notion.com/p/e07163015bd3472f943aa2ef3f0bc815?pvs=21) (Registro de Ações Rápidas)

### 🧪 MVP rule — batch size

Process **5 unread Gmail emails at a time**. Bring one batch to Odara for joint resolution; only after that batch is resolved/decided, fetch the next 5.

### Interaction

The Treasure opens the workflow directly rather than acting as a generic chat. Each batch is resolved together before the next batch is fetched.

Supported actions include reply, archive, mark as read and draft. **Never auto-send.**

### Visual direction

Enchanted magical broom / little cleaning creature: playful, alive and clearly associated with cleaning the inbox. It should not look like a trash can.

### Micro-personality

> **“Clear the deck. Five at a time.”**
> 

### Reliability note

The scheduled/cloud context has previously shown Gmail connectivity reliability issues in recorded runs. That is a runtime/integration issue, not a reason to redesign the Poção.