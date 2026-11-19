# [ARCHIVE] Governance & Guardrails

> **Decision — Bom Dia Cláudio Experience Spec v0.1 (28/09/2026): APROVADO.** A experiência foi consolidada após revisão detalhada do run de 28/09. A especificação canônica está em [[ARCHIVE] Bom Dia Claude — Experience Spec v0.1 (Aprovado 28/09/2026)](%5BARCHIVE%5D%20Bom%20Dia%20Claude%20(Rotina%20Matinal%20Completa)/%5BARCHIVE%5D%20Bom%20Dia%20Claude%20%E2%80%94%20Experience%20Spec%20v0%201%20(A%203e9107b19b4981c1b079c0241c174426.md). O próximo passo é produzir o prompt de implementação para Claude a partir desse contrato. O prompt deve explicar o racional das decisões e separar experiência, comportamento, arquitetura, integrações e critérios de aceitação. Não implementar mudanças estruturais antes desse handoff.
> 

## 🔐 Odyssey Internal Trust Boundary — Canonical

**Shared knowledge. Restricted structural mutation. Protected external boundary.**

- **Internal read access:** Parts of Odyssey should be able to read across the Odyssey when that context helps support Odara. Internal knowledge sharing is a feature, not a risk to be solved by unnecessary compartmentalization.
- **Structural authority:** Reading, reasoning, suggesting, and executing established workflows do not grant permission to alter Odyssey's architecture. Structural mutation is restricted to explicitly approved Builder chats: **Odyssey Mayor, the Odyssey PM/Build chat (this chat), and Building Odyssey**.
- **External boundary:** Odyssey is a private world for Odara to speak with herself. Internal knowledge may circulate across the system, but information must not be exposed to people or systems outside the Odyssey unless that external action is explicitly intended/authorized by Odara.
- **Execution vs. mutation:** A Persona or routine may act within an established workflow without gaining authority to redesign the workflow, taxonomy, architecture, or governance.

This boundary is canonical and should be treated as a first-order governance rule when designing integrations, permissions, agents, automations, and future Command Center capabilities.

> This page holds the *meta-rules* — how the project runs, evolves, and stays safe to keep building on — plus the running Decision Log and Session Log. Definitions of what things *are* (Task, Obligation, Quest, Categories) live in the [Codex](%5BARCHIVE%5D%20Codex%20(p%C3%A1gina%20legada%20do%20Notion)%203aa107b19b498052beaace4ac48408d2.md).
> 

## 🧱 Decision Log

Every architecture/taxonomy decision made so far, so nobody has to scroll through chat history to find *why* something is the way it is.

| Decision | Reasoning / Context |
| --- | --- |
| Schedule Task Governance v1 aprovada com ajustes da Odara; Bom Dia fixado em 11:30 Europe/Madrid (28/09/2026) | Hacker aprovado como Schedule Task Steward, com limite claro: governa o agendamento dentro das regras, mas mudança na governança/estrutura escala para o Mayor. Princípio incorporado: antes de criar execução agendada, verificar Skill, Workflow ou módulo de execução existente — maximizar trabalho útil por execução. Horário fixo + módulos é o padrão a explorar. Teto 3/dia + 2 de reserva = política inicial de segurança, a recalibrar pelo Hacker com dados reais. Absorção da Manutenção, varredura de casas e outros módulos no Night Shift = direções a validar, não decisões. Bom Dia: cron trocado de UTC para `CRON_TZ=Europe/Madrid 30 11 * * *` (mesmo horário local, sem salto em 25/10). |
| Schedule Tasks viram recurso escasso governado pelo Hacker (Schedule Steward); Personas não criam Task sozinhas (28/09/2026) | Plano Pro ≈ 5 execuções agendadas/dia (limite é de execuções, não de Tasks). Teto da casa: 3/dia, 2 de reserva. Persona identifica a necessidade; Hacker decide como roda (ad hoc, módulo de slot, Task nova). Veredito sobre bulk schedules: sim, como "slot + módulos" — um slot diário roda módulos de qualquer cadência checando a data. Alvo pós-piloto: 2 execuções/dia (Night Shift/Operação Diária + Bom Dia). Achado urgente: Bom Dia e Manutenção em UTC mudam de horário sozinhos em 25/10. Detalhe: ⏳ Schedule Task Governance v1. |
| Organization & Capability Ownership aprovado; roster da Crew vira registro de capabilities (28/09/2026) | Personas têm ownership operacional sobre Skills/Workflows/Tasks do próprio domínio; Builders mantêm autoridade estrutural (teste da linha em 5 pontos na página 🏢 Organization & Capability Ownership). Sem banco novo: AI Chats / Efforts Mapping ganhou Dono, Usada por, Domínio, Estágio e opção Workflow; dados existentes preservados (20 linhas verificadas). Regra: toda capability criada por Persona é registrada no mesmo dia. Monthly Area Reports + Captain's Council definidos, primeira edição prevista para fim de outubro. |
| 🧪 EXPERIMENTAL — Piloto Night Shift + Crew Noticeboard (Keymaster ↔ Corsair), 5 noites em modo sombra (28/09/2026) | Implementado pelo Mayor a partir do Operating Model (Odara + ChatGPT). Como chats não conversam entre si nem acordam sozinhos, a comunicação passa por 3 artefatos no Notion (Entrada da Noite, Crew Noticeboard, Night Shift Log) e um Scheduled Task às 05:00 Madri que "veste" Lorekeeper, Keymaster e Corsair. Bom Dia ganhou bloco opcional/fail-safe que lê o Noticeboard. Autoridade de contato do Keymaster pausada durante o piloto. Não é canônico: decisão de promover (ou não) o protocolo só depois da avaliação das 5 noites. Detalhe e rollback na página ⚓ Crew Noticeboard & 🌙 Night Shift — Pilot. |
| Radar de Shows (The Bard) validado como corretamente escopado — sem violação estrutural (2026-09-27) | Odara + The Bard construíram: database "Radar de Shows — The Bard" (Resource/Source of Truth), a metodologia de scan (Skill ainda não formalizada, uso real já existe), e o Scheduled Task "Radar de Shows - Scan Quinzenal" (trig_016DocVu3mhFhMy1QftuFxi9, dia 1 e 15, 9h47 Madrid). Classificação confirmada contra o 🧭 Odyssey Capability Model (2026-09-27): DB=Resource, scan=Skill, cron=Task, sem Treasure/Command Center novo (nada disso foi autorizado nem necessário ainda). Está dentro da autoridade read-broad/write-narrow do Persona — não precisou escalar pro Mayor antes de existir. Pendências que continuam em aberto, não resolvidas aqui: campo "Região de Referência" duplicando "Alcance" (não tocar sem confirmar com Odara), formalização futura como Skill/Poção, mudança de cadência pra bimestral (intenção declarada, não urgente).

**Calibração de organização concluída (27/09):** propriedade "Notas" ocultada da view padrão (não deletada — condição de deletar documentada na Metodologia); "Região de Referência" formalizada como pergunta fechada pra Odara decidir com um clique; Metodologia agora referencia de volta o Capability Model, este Decision Log e traz badge de status (🟡 Skill candidate); template mínimo de 3 blocos definido pra páginas de item daqui pra frente (sem retroagir nos 38 existentes); Log de Scans convertido pro mesmo formato tabular do Registro de Runs do Bom Dia Claude. Nada de Command Center/Treasure/taxonomia foi tocado — calibração ficou inteira dentro da autoridade do Persona. |
| Notion database = single source of truth for live data; GitHub repo = logic/code only | Lowest friction to maintain (already editing in Notion); Claude/ChatGPT both access Notion directly, no sync needed |
| GitHub repo setup postponed until routines are well-designed and running smoothly | Odara wants the core routines (Morning Sweep, food routine, etc.) solid and battle-tested before adding a code/backup layer on top |
| Repo structure mirrors the Architecture Overview 1:1 (one folder per system, each with its own README) | So nothing is ever ambiguous about where something belongs |
| Quest Engine v1 = Hybrid model (Cadence Queue + one Wildcard slot per check-in) | Cadence guarantees nothing gets lost; Wildcard keeps fun alive even on heavy days |
| Number of Quests per check-in is not fixed — it varies with what's actually due | Mirrors real life instead of forcing an artificial quota |
| "Admin" stays a broad catch-all Category | Simplicity for now |
| Claude is the primary GM for Odyssey (check-ins, routines, backlog, Notion/Gmail); ChatGPT stays in the loop for Side Quest/personal recommendation input, since it has more history with Odara on a personal level | Claude runs the system day-to-day; ChatGPT's longer personal context is a complementary input, to be figured out together over time how best to use it |
| Emotional/mental tasks (journaling, therapy logistics) fall under Health | No dedicated category yet |
| Official Category name is "Home" (not "House") | Naming consistency across the taxonomy |
| Recurrence vocabulary standardized, kept in Portuguese | Matches the live database's current language |
| Whole documentation (README + sub-pages) standardized in English | GitHub-ready; live database schema/values stay in Portuguese as a separate, deferred step |
| Sub-pages renamed: Databases → Codex (reference layer), Gamification Rules → Playbook (experience layer) | Thematic consistency with the Game Master framing |
| "New Projects" stays a Category for now; promotion-to-own-Category flow deferred | No template/flow designed yet |
| Redefined the core model: Task = generic raw entry; a Triage workflow (TBD) splits it into Obligation (need-to, gets Category/Recurrence) or Quest (not a need-to, fun/self-improvement) | Clears up the earlier confusing 3-tier Obligation→Task→Quest chain |
| Live database's Tipo field option renamed from "Task" to "Obligation" to match the new model | Keeps the 33 backlog rows consistent with the redefinition; all 33 rows manually restored after the rename briefly cleared them |
| Decision Log + Session Log moved from Codex to this page | Codex is meant to be pure reference (what things are); process/history belongs in Governance |
| Categories represent life areas only, not task types — removed "New Projects" and "Side Quest (pendente)" as Categories | Cross-checked against an external ChatGPT-authored project philosophy doc, which flagged that mixing life-area and task-type concepts in one taxonomy was inconsistent; the one affected row (a Quest) had its Category cleared rather than reassigned, since Quests don't require one |
| Progression: Memory Log is the primary progression system; XP stays as an optional lightweight layer alongside it, not replaced | Matches the principle that game mechanics should emerge naturally and never dominate the emotional experience — but XP isn't discarded, just demoted |
| Added "Última vez feito" (date field) to the Task Backlog schema — recurrence due-ness is now calculated from this field, not from Status alone | Without it, marking something "Feito" gave no way to know when the next occurrence is actually due; Status alone can't carry recurrence math |
| New Side Quest subtype: "Gestos de Bondade Aleatória" (random acts of kindness) — e.g. a heartfelt message to a stranger who moved her, visiting a nursing home, donating food | Odara noticed spontaneous generosity makes her feel more alive; ties directly to the "Encontrar um ritmo de vida com mais entusiasmo" Main Quest. No fixed cadence, never becomes an Obligation; suggested Wildcard weighting ~1-in-4-5, adjustable |
| Status field expanded from 3 to 6 values (A Fazer, Em Andamento, Feito (Ciclo), Done, Em Pausa, Aguardando Terceiros) — with an auto-revival rule flipping "Feito (Ciclo)" back to "A Fazer" once the next Próximo Deadline arrives | The old 3-state model (To Do/In Progress/Done) was too rigid — didn't distinguish a recurring item's light "done for this cycle" from a one-time item's permanent completion, and had no way to represent "paused on purpose" vs "blocked on someone else." See Codex, Completion Protocol |
| New "Rigidez" field (Rígido / Flexível) added to the Backlog schema; "Fazer mercado (semanal)" removed from Backlog (became ad hoc, same as Cozinhar/Planejar a semana) | Exact calendar dates were being applied uniformly to real hard deadlines (bank due dates, legal deadlines) AND soft self-care/home cadences (haircut, laundry) alike — flattening "vencido" urgency onto things that don't actually have a wrong day. Rigidez changes the GM's tone per item, not just the data. Classified: Rígido = Pagar contas mensais, Empadronamiento, TSI, Saída Definitiva do Brasil, Modelo 151, Passaporte, CNH; Flexível = all Personal Care, home upkeep, Check-up do Mês, Diário Pessoal, Stremio, assinaturas, Treino na Academia, testes de velocidade Aticco |
| Bom Dia Claude redesigned as an HTML artifact ("diário de bordo" visual identity), with 3 fixed sections (Intro/Personal Status, Obligations, Awareness) replacing plain chat text | Odara wanted more delight and a bit of chaos injected into the daily routine — fortune-cookie phrase, Flo cycle status, Spotify song, mini untracked side quest, plus richer Obligations/Calendar/News/Events sections. Visual direction approved 2026-08-22, tokens documented on the routine page for consistency across future generations |
| Side Quest generation engine v2: two modes (livre/ancorada em Main Quest via "holofote" orgânico), internal+external inspiration mix (mood/energy + weather/events/pop culture via Ticketmaster/Fever/web search), porte calibrated at delivery by Mood (not fixed at ideation), and learning via Recap Session pattern-surfacing instead of silent tracking. Applies to both Wildcard and Side Quest On-Demand — same engine, two entry points | Came from a dedicated brainstorm session Odara asked for explicitly — previous Side Quest logic was thinner (just "can occasionally target a Main Quest"). New "Última Side Quest Recebida" field added to Backlog schema (Main Quest rows only) to power the holofote silently. See Playbook, Side Quest Path |
| Bom Dia Claude Awareness section redesigned with tabs: "Notícias do Dia" (Mundo/Espanha-Barcelona/Brasil) and "Eventos" (Local Barcelona/Europa) — Europa filtered by easy-connection cities or a growing "Favoritos" list (seeded with Nightwish/Epica/Kamelot) | Vertical list was getting too long; tabs keep the HTML shorter and more interactive. Brasil news tab restores original scope that had quietly dropped. Same no-silent-tracking philosophy as Side Quests applies to learning what she likes/skips here |
| GitHub backup repo created (odarambmenezes/odyssey) — **kept private** (corrigido em 2026-09-01; um registro anterior dizia "made public", mas isso nunca chegou a se efetivar de verdade, e ela decidiu manter privado mesmo após descobrir a discrepância) | Notion publicly acknowledged an MCP tool-call reliability issue (2026-08-31) that stalled work mid-session. Repo holds a manual markdown mirror of docs as fallback. No personal task data ever committed — stays in private Notion only. Set up via Claude Code (OAuth device-flow, no token ever handled in chat). Privacy doesn't block the sync workflow — Claude Code has its own authenticated access regardless of public/private; only reason to go public would be letting the [claude.ai](http://claude.ai) chat (no token) read it directly, which isn't essential |
| Notion → GitHub fallback rule added to GM Charter (rule 16) | Any chat/task tries Notion first; only on error, checks the matching GitHub file; if neither works, surfaces the error rather than inventing. Sync is manual, not live/automatic |
| `about-me.md` in the GitHub repo stays standalone — not mirrored to/from Notion | It's a general "how I like to collaborate with any AI" doc (decision style, communication, working style), not Odyssey-specific data. No factual overlap with Player/Character Sheet (birthday, sign, cycle, limits). Some philosophical echo of GM Charter rule 15 (push back, be proactive) — intentional, not duplicated data, since one is general-purpose and one is Odyssey-specific |
| All Skills routines mirrored to GitHub (2026-09-01) — with a personal-data-omission pattern applied consistently | Where a routine's Notion page contains real personal data about other people (friend names/birthdays in Aniversários, contact list in Voice Profile, cycle dates in Corpo & Vitalidade), the GitHub mirror documents the mechanism only and points back to Notion for the actual data — even though the repo is currently private, per Scope Boundaries ("no personal task data ever gets committed") |
| Bom Dia Claude Template de Referência atualizado pra v4 (2026-09-02), depois de ficar desatualizado o suficiente pra causar um desvio real numa rodada agendada | A Scheduled Task seguiu o template à risca (como deveria) — só que o template ainda descrevia a versão sem tela de abertura, sem drag-and-drop, com timings antigos. Lição: sempre que o protótipo muda numa sessão, atualizar o Template de Referência no mesmo dia, não só a descrição em texto |
| Command Center construído como Claude Artifact (Opção A, 2026-09-20) — Fase 1 de um plano de 3 fases pra recuperar praticidade no projeto | Odara pediu um jeito visual/UX de acessar Odyssey no Mac e no iPhone (Add to Home Screen). Reaproveita a estética já aprovada (mesa de tarot, mapa náutico das Main Quests com clima ao invés de pontuação) do conceito "odyssey-command-center-concept.html". Conteúdo das 6 ilhas usa só dados já documentados (sem inventar sinal de atividade). Fase 2 (auditoria de skills/rotinas) e Fase 3 (polimento/testes) ficam pra depois, por pedido explícito dela de não perfeccionar agora |
| Novo modelo operacional (2026-09-21): o chat de Gestão de Projeto (PM) vira o board de decisão estrutural; Building Odyssey vira a "sala de máquinas" — recebe tarefas já decididas do PM e cuida só da implementação técnica | Odara pediu um gerente de projeto dedicado pra filtrar/priorizar ideias (viáveis agora vs. depois vs. nunca) sem ela ter que decidir factibilidade/timing sozinha, e pra não perder ideias boas só por chegarem cedo demais. Building Odyssey deixa de ser onde decisões acontecem |
| Building Odyssey formalmente arquivado (2026-09-21) — deixa de ser workspace ativo, vira registro histórico. Chat de PM (este) passa a ser também onde a construção técnica acontece (direto ou via subagentes), não só a decisão | Com subagentes disponíveis no chat de PM, não havia mais razão pra manter um segundo chat só pra execução — isso só recriava duas fontes vivas. Debrief completo coletado do Building Odyssey antes do arquivamento (ver Command Center abaixo). GitHub sync segue manual, sem rotina fixa — Odara aciona quando algo "fechar" o suficiente pra valer subir |
| Command Center Fase 1 — decisões de detalhe: vocabulário de "blocos", popup por ilha com snapshot manual (não live-pull do Notion — exigiria mais infraestrutura), clima ao vivo tecnicamente inviável dentro do sandbox do artifact (por isso fase do dia visual em vez de clima real), Claude Catalão = mesmo agente do chat "Catalaude/BCN Expert" com nova persona (não duplicado) | Detalhe completo em claude/[command-center-versions.md](http://command-center-versions.md) (Claude Project). URL do artifact: [https://claude.ai/artifact/6N4uHqSf4wMghTXE5YjSc9](https://claude.ai/artifact/6N4uHqSf4wMghTXE5YjSc9) |
| AI Crew do Command Center: só "Agente de Viagens" ativo por enquanto; construção dos outros 5 candidatos (Estilista, Corretora, Melhor Amiga, Concierge, Comunicadora) adiada de propósito | Nenhum tinha urgência comparável à de Viagens. Nomes piratas e páginas de Notion por agente só serão criados quando cada um for efetivamente "recrutado" |
| Command Center: ribbon 🔺 "Permanência em Barcelona" removido do topo (era iniciativa do Claude no Building Odyssey, não pedido dela); ornamentos do header definidos como duas flechas apontando pro título; bloco verde musgo mantido sem conteúdo, sem fixar o palpite de "painel de tasks urgentes" | Decisão dela (2026-09-21), via chat de Gestão de Projeto, revisando o que o Claude tinha decidido sozinho no Building Odyssey antes do arquivamento |
| Causa raiz dos itens recorrentes travados em "Feito (Ciclo)" identificada e corrigida (2026-09-23): a Scheduled Task de manutenção diária mencionada no Parking Lot desde 02/09 ("sendo criada por ela") nunca chegou a existir de fato — só havia a rotina de Bom Dia Claude agendada. Criada agora: "Odyssey — Manutenção Diária do Backlog", 6h todo dia, silenciosa, só reverte Status='Feito (Ciclo)' pra 'A Fazer' quando o Próximo Deadline já passou. Os 7 itens presos até agora (Pedicure, Limpar Quarto, Blondor, Sobrancelha, Unhas, Arrumar Quarto, Check-up do Mês) foram revividos manualmente na mesma sessão | Sem essa Scheduled Task, o auto-revival só disparava quando algum chat lia o Backlog manualmente — o que não estava acontecendo com regularidade suficiente |
| Command Center ganhou um bloco "Rotinas & Skills" (2026-09-23) — grade visual com todas as rotinas nomeadas do projeto, cada uma com um status claro (rodando sozinha / construída mas manual / criada mas não testada / em design) e link direto pra onde ela vive | Resposta direta ao pedido dela de ter um campo visual único mostrando o que funciona vs. não funciona. Também é a primeira resposta ao item do Parking Lot "Too many separate keywords/routine names" (02/09) — não resolve a fluidez completa que ela pediu, mas dá visibilidade de estado num só lugar, em vez de espalhado por páginas. Fonte: página Skills, Workflows and Automations + 3 sub-páginas de rotina (Side Quest On-Demand, Meal Routine, Aniversários) |
| Command Center: AI Crew redesenhada em "medalhão" (2026-09-23) — avatar circular com moldura dupla nos cards e no popup de cada agente (espaço reservado pros avatares reais quando existirem); contraste forte entre ativos (borda dourada + brilho) e a recrutar (∼55% opacidade, tracejado, dessaturado); filtro rápido por ícone (3 linhas, sem texto) ciclando todos/ativos/a recrutar. Popup das ilhas reestruturado com Main Quest (nome oficial do Notion), Pontos-chave e Skills conectadas (badges reaproveitando as cores de status do bloco Rotinas & Skills) | 3 opções visuais testadas antes num canvas de design separado (Selo de Cera / Página de Diário / Medalhão) — ela escolheu Medalhão achando que o círculo já é onde os avatares reais vão entrar depois. Mapeamento Main Quest ↔ ilha e skills conectadas veio direto da query no Backlog (Tipo=Quest, Categoria=Main Quest) — hoje só "Ritmo com Entusiasmo" tem skills de fato conectadas (Rotina de Alimentação, Side Quest On-Demand); as outras 5 ilhas mostram "nenhuma skill conectada ainda", sem inventar conexão |
| Princípio arquitetural/operacional fechado por Odara + Claude + ChatGPT: "Experiment freely. Protect what works. Promote only what has been validated." — nunca experimentar direto numa rotina/artefato já em uso diário; "Core estático, enhancement progressivo" (2026-09-23) | Incidente real (template do Bom Dia Claude desatualizado, 02/09) discutido junto com Claude e ChatGPT (áudio da Odara pra ambos). ChatGPT propôs inicialmente uma arquitetura formal de 3 estados (Production/Experimental/Promotion) + um "Odyssey Lifeboat" separado; Claude argumentou que o problema era hábito de trabalho, não falta de infraestrutura, e propôs versão mais leve reaproveitando o que já existe (versionamento nativo do Artifact, snapshot manual do Command Center). ChatGPT revisou e concordou, acrescentando só uma nuance: a versão em uso funciona como "protected baseline" enquanto a nova é experimentada — já implícito na regra 1, agora explícito no nome do princípio. Odara fechou os dois lados nesta versão. Substitui e resolve o item "Modo Teste vs Modo Produção" do Parking Lot. Regra final: (1) mudança visual/estrutural nasce em cópia/versão separada, nunca direto sobre algo em uso — essa versão em uso fica protegida (baseline) enquanto a nova é testada; (2) promove só após validação funcional — aprovação visual da Odara só quando a mudança tem impacto relevante de UX/visual, não pra ajuste técnico invisível nem edição pequena de conteúdo; (3) automação agendada (ex: Bom Dia Claude) — nenhuma mudança estrutural no template vira fonte da próxima execução agendada sem testar manualmente end-to-end antes; (4) Command Center e artefatos vivos em geral: static core + progressive enhancement — informação essencial aparece sem depender de JS/dado dinâmico, enhancements podem quebrar sem tornar o essencial inutilizável. |
| **AI Crew Signal Protocol** criado (2026-09-24): every AI Crew member now holds two simultaneous roles — Persona (serves Odara in its domain) and Signal Scout (surfaces potentially important signals about Odara that could improve Odyssey as a whole). Signals are observations, not automatically confirmed preferences — they never modify a Source of Truth automatically. They land in a new, separate **Odyssey Signals** inbox (distinct from Ideas Intake: Ideas Intake = project input, Signals = knowledge input) and get triaged in a review cadence (Weekly Pit Stop / Recap Session), where they may be promoted to a Source of Truth, discarded, or kept as an unconfirmed hypothesis. The system optimizes for a small number of genuinely useful signals, not exhaustive logging of every comment. The rule lives once, centrally, here and in the AI Crew Architecture page — individual Persona pages only carry a one-line pointer, not a duplicated copy. | Locked |

## 🚫 Limitação técnica descoberta: JS bruto trava no WAF do Notion (2026-09-02)

Blocos grandes de JavaScript executável (com padrões tipo `insertBefore`, `setPointerCapture`) disparam bloqueio 403 do Cloudflare do Notion, mesmo em blocos de código relativamente pequenos. **Solução adotada**: documentar comportamento de JS em prosa/passo-a-passo no Notion (número de ms de cada delay, o que cada handler faz), e manter o código executável real nos artefatos gerados na conversa (ou no GitHub, que não tem esse WAF). CSS e HTML puro não disparam esse bloqueio.

## 🧠 Shared Session Log

The Shared Session Log is the **bridge between Odyssey agents and Odara**, not a new Source of Truth. It preserves continuity between sessions so ChatGPT and Claude can resume from the same operational state without Odara acting as the handover layer.

### Operating principle

> **The Session Log is not the Source of Truth. It is the bridge between agents.**
> 

> 
> 

> Durable decisions, rules, live data, and canonical definitions must be promoted to their appropriate Source of Truth.
> 

### Session protocol

**Start Session**

1. Read the latest session entry.
2. Read the **Shared State** before doing new work.
3. Check **Decisions / Open Questions / Next Actions**.
4. Verify affected Sources of Truth before assuming the log is current.
5. Continue from **Where we stopped** rather than reopening settled decisions.

**Close Session**

1. Record what this agent actually did.
2. Record discoveries, decisions, and unresolved questions.
3. Update **Shared State** only with facts/decisions supported by the session.
4. Add the next actions and anything explicitly marked **Do Not Touch Yet**.
5. Record **Last Contributor**.
6. Link the Sources of Truth affected by the session.

**Agent handover rule**

- ChatGPT and Claude each contribute their own section.
- The **Shared State** is the consolidated project state, not a transcript or debate.
- If the agents disagree, record the disagreement explicitly under **Open Questions**; do not silently resolve it.
- The most recent contributor is always explicit.
- A later agent should not treat an old session note as canonical when the linked Source of Truth has changed.

### Session template

For each new session, use:

- **Session Focus**
- **ChatGPT Contribution**
    - Done
    - Decisions
    - Discoveries / Insights
    - Open Questions
    - Next Actions
- **Claude Contribution**
    - Done
    - Decisions
    - Discoveries / Insights
    - Open Questions
    - Next Actions
- **Shared State**
- **Where We Stopped**
- **Do Not Touch Yet**
- **Sources / Affected Pages**
- **Last Contributor**
- **Session Status**

### Historical sessions

- **2026-07-27** — Defined Vision, Design Principles, Success Metrics; built the Task Category taxonomy and initial 34-item Backlog; designed Quest Engine v1; split Databases → Codex and Gamification Rules → Playbook; built the Bestiary; moved Decision Log/Session Log to Governance.
- **2026-08-01** — Created "Building Odyssey" as the architecture/meta chat; reviewed core documentation; postponed GitHub setup; clarified Claude as primary GM and ChatGPT as complementary input; designed/documented Meal Routine.
- **2026-09-21** — Created the Gestão de Projeto (PM) chat; audited Backlog and architecture; defined PM as the structural decision board and Building Odyssey as the technical execution room; evolved Parking Lot into Ideas Intake.

### 🧭 2026-09-23 — AI Crew / Architecture Audit Session

**Session Focus:** AI Crew reconciliation, Step A/B audit, Bom Dia Claude operational audit, and shared agent architecture.

**ChatGPT Contribution**

- Reconciled the historical AI Crew roster against the canonical AI Crew database.
- Established the Persona / Poção / Schedule Task / Builder distinction.
- Clarified Builder split: **First Mate / Odyssey Command = system, implementation and governance**; **Art Direction / Narrative & Experience = visual, narrative and experience coherence**.
- Reviewed Claude's Step A/B audit and translated it into the next execution sequence.
- Proposed the Shared Session Log itself as the bridge for direct ChatGPT ↔ Claude continuity.

**Claude Contribution**

- *Done*
    - Ran Step A/B (read-only): inspected both real Scheduled Task configs, the 3 Bom Dia registries' actual rows (not just schema), 19 consecutive Run Log days (09-05→09-23), and the reconciled 14-row AI Crew database.
    - Ran Step C exactly to Odara's approved scope. **C1:** deleted the disabled zombie Scheduled Task (`Bom dia Claude`, `trig_01XMXv1Hb5pZu4JQtiSVYvtQ`, disabled since 2026-08-26); live task (`Card Pull of the Day`, `trig_01EC7E7Uf5AapZV4gmHpM3dZ`) untouched. **C2:** registered 3 already-real Poções in the AI Crew DB (Calendar Check, "O que tá pendente?", Gmail Sweep), Status=Under Review, each stating explicitly it formalizes existing capability rather than new code. **C3:** read the Side Quest On-Demand and City Radar/Local Lens pages directly to validate two proposed linkages, rather than assuming from the handoff description. **C4:** diagnosed, did not fix, three reliability issues.
    - Delivered 4 MD files to Odara (feedback on the ChatGPT handoff, the Step A/B audit, the Step C report, and Bom Dia Claude context for ChatGPT).
- *Decisions I consider closed*
    - Zombie task deletion and the 3 Poção registrations: done, low-risk, no need to revisit.
    - Daily News Briefing: stays out of scope until Odara reopens it.
    - The 3 reliability bugs are diagnosed with grounded hypotheses but deliberately **not fixed** — Odara explicitly asked to see the diagnosis before deciding on any fix, so no fix has been treated as done.
- *Discoveries / Insights not in ChatGPT's version*
    - **Self-correction, not ChatGPT's claim:** my own Step B audit originally said City Radar and the Eventos tab overlap directly and recommended not building anything new for Local Events/Discovery. Reading the actual City Radar/Local Lens page during Step C showed that was wrong — City Radar is an **unbuilt**, proposed biweekly automation (curated, tiered 🔥/🟡/👀), structurally different from the daily unfiltered Eventos tab. Related but distinct; when City Radar is eventually built it's new work, not a formalization. Flagging this correction explicitly rather than leaving the earlier wrong claim standing.
    - Side Quest On-Demand ↔ Mini Side Quest share one engine (Playbook Wildcard Slot) **by design**, confirmed at the documentation level — but Side Quest On-Demand's own page states it's "ainda não testada na prática." The linkage is real on paper, not yet verified by an actual run.
    - The three bug hypotheses are grounded in something concrete, not just named: (a) Backlog has no mandated pre-flight SQL query in the Scheduled Task prompt, unlike the 3 registries which do — that structural gap is the likeliest reason it's the one source that occasionally fails; (b) 0/19 selections for "Diário do Capitão" (Ativo, listed first of 4 themes) is under 0.5% likely by true chance and matches a known LLM positional-selection bias for prose "pick one at random" instructions, not a data bug; (c) Artifact-publish failures are named directly in the Run Log itself as a platform-level constraint on the Artifact tool in scheduled/auto sessions — meaning the "living artifact" cannot currently be trusted as an always-current mirror of what ran on those specific days.
    - The AI Crew DB `Status` field currently conflates "reconciliation reviewed" with "thing is real and working" — every row reads Under Review, including a Schedule Task that's run unattended for weeks and a Persona with no chat yet. Not fixed, just flagged for whoever reads that column as a maturity signal.
- *Open Questions (new, not yet in ChatGPT's list)*
    - Should AI Crew DB `Status` split into two signals (reconciliation vs. operational maturity), or is "Under Review" intentionally provisional until a second pass?
    - Should Side Quest On-Demand get an explicit test run before its Wildcard-engine linkage is called "confirmed" anywhere else in the docs?
    - Should the Run Log flag "artifact stale as of this date" whenever a scheduled run falls back to SendUserFile, so a future session doesn't trust the artifact URL blindly on those days?
- *Next Actions (proposed, not started)*
    - Odara decides whether/when to act on the 3 diagnosed bugs (candidate fixes are in the Step C report; none applied).
    - If/when wanted: extract Daily News Briefing as the one genuine new Poção candidate from the original handoff list — every other candidate on that list turned out to already exist. fileciteturn129file0L5-L10 fileciteturn129file0L69-L77

**Shared State**

- AI Crew roster is reconciled at the canonical mapping level.
- The current 14-row AI Crew database is the operational roster; legacy names remain only where needed for deliberate migration/renaming. It now also includes 3 newly-formalized Poções (Calendar Check, "O que tá pendente?", Gmail Sweep), Status=Under Review, no new code involved.
- Bom Dia Claude is a live production routine with a real scheduled task; the predecessor zombie task has been **deleted**, not just left inert.
- City Radar and the Eventos tab are related but distinct — City Radar is unbuilt; don't treat the Eventos tab as an existing formalization of it.
- Side Quest On-Demand and Mini Side Quest are designed to share one engine, but that convergence is unverified in practice — Side Quest On-Demand has never actually run.
- The next work is **stabilization and validation, not expansion**.
- Daily News Briefing is explicitly out of scope for now.
- Step C (cleanup + formalization + validation + diagnosis) is **complete** as scoped by Odara. The three reliability bugs (Backlog empty 2/19 days, theme-selection anomaly, Artifact-publish failures in scheduled sessions) are diagnosed with grounded hypotheses but intentionally not fixed — that decision is Odara's next call, not yet made.

**Where We Stopped**

- AI Crew Step A/B/C is complete, exactly as scoped by Odara — nothing beyond the approved scope was touched.
- Three reliability bugs are diagnosed, not fixed — awaiting Odara's decision on whether/how to fix them; that's the next real decision point, not a next action either agent should take unilaterally.
- The Shared Session Log protocol has now been used end-to-end by both agents for the first time in this same entry; the next test is whether ChatGPT can cross-check this closeout directly, without Odara bridging.

**Do Not Touch Yet**

- Do not redesign Bom Dia Claude.
- Do not build Daily News Briefing.
- Do not fix the Backlog/theme/Artifact bugs until the cause is diagnosed.
- Do not reopen reconciled AI Crew naming decisions without new evidence.

**Sources / Affected Pages**

- Governance & Guardrails
- AI Crew — Architecture & Persona Mapping
- Bom Dia Claude / Morning Ritual
- Bom Dia registries and Run Log
- Claude Step A/B audit

**Last Contributor:** Claude  

**Session Status:** 🟢 Closed — Claude completed the parallel closeout above. Next step: ChatGPT reads this entry and cross-checks it (first real test of the ChatGPT ↔ Claude protocol).

### 🎯 2026-09-24 — AI Crew Signal Protocol Implementation

**Session Focus:** Implement the AI Crew Signal Protocol — every AI Crew Persona also acts as a Signal Scout, surfacing potentially important signals about Odara into a new, central Odyssey Signals inbox, kept separate from Ideas Intake and never auto-modifying a Source of Truth.

**Claude Contribution**

- *Done*
    - Read Governance & Guardrails and AI Crew — Architecture & Persona Mapping (including the 2026-09-23 Shared Session Log entry) before making any change.
    - Logged the decision in the Decision Log above ("AI Crew Signal Protocol criado").
    - Created the **👁️ Odyssey Signals** inbox on this page, directly above Ideas Intake — its own table (Signal/Observation, Source Persona, Date, Domain/Area, Confidence/Nature, Possible Source of Truth, Status, Notes/Decision), explicit "not the same as Ideas Intake" framing, the Observation≠truth rule, and the 5 status values (novo/não revisado · em triagem · confirmado/promovido · descartado · mantém como hipótese). Left empty — no retroactive migration of old conversations, per explicit instruction.
    - Added a new "🎯 Signal Scout role" section to AI Crew — Architecture & Persona Mapping (between Crew Dynamics and Current Crew Map): the two-role (Persona + Signal Scout) framing, the double-agent metaphor, the Signal threshold list, the Observation≠truth rule with examples, the flow diagram (conversa → sinal → Odyssey Signals inbox → triagem → promover/descartar/hipótese), and the Ideas-Intake-is-different clarification.
    - Appended a single, uniform, minimal pointer ("## 🎯 Signal Scout", ~3 lines) to the end of all 8 individual Persona pages (Best Friend/Logkeeper, Claude The Traveler/Navigator, Buyer Expert/Merchant, Personal Clowder/Quartermaster, Claude Real Estate/Keymaster, Cloud The Stylist/Clothmaster, The Bard, Pet Companion/Beastmaster) — no full copy of the rule on any Persona page, just a reference back to the central section.
    - Ran a self-inflicted repair: an early `update_content` edit on the AI Crew Architecture page broke block nesting (rest of the page got trapped inside an unclosed callout). Fixed surgically across 3 follow-up edits with no data loss and no use of `allow_deleting_content` — confirmed clean via a fresh fetch (all original sections, the 9-row Roster reconciliation table, and the inline AI Chats/Efforts Mapping database all intact). Only cosmetic side effect: the new "Signal Scout role" heading isn't wrapped in the same purple callout styling as sibling sections.
- *Sanity check (all 8 answered "yes" before closing)*
    - Traveler/Keymaster/Clothmaster/Logkeeper can each identify a signal — yes, each page now points to the shared protocol.
    - A signal can reach the inbox without needing immediate promotion — yes, "novo/não revisado" and "mantém como hipótese" are valid resting states.
    - An unconfirmed preference stays a hypothesis, not a fact — yes, the Observation≠truth rule is stated on both the Governance and Architecture pages.
    - Ideas Intake stays separate — yes, distinct heading, distinct table, distinct language, positioned as its own section.
    - No Source of Truth is altered automatically — yes, explicit on both pages; promotion only happens through review.
- *Decisions left open*
    - No new field/anchor standardization was done across the 8 Persona pages beyond the appended pointer (their endings were already inconsistent — some end in "Boundaries," some in "Working principle" — left as-is since only an append was needed).
    - Exact review cadence for the Signal Inbox (alongside Weekly Pit Stop vs. Recap Session specifically) wasn't pinned down further than "a suitable existing cadence" — deliberately, per instruction not to create new scheduled routines or over-specify workflow.
- *Risks / points of attention*
    - The "Signal Scout role" section heading on the AI Crew Architecture page is a plain heading, not the purple callout used by sibling sections — cosmetic only, flagged for whoever next touches that page's styling.
    - The AI Crew Architecture page had its block structure surgically repaired mid-session after a corruption I introduced; worth a visual spot-check next time that page is opened directly in Notion, though the post-fix fetch showed everything intact.
- *What was deliberately NOT changed (per explicit scope)*
    - No Persona was redesigned, renamed, or created.
    - No Source of Truth was altered automatically by this change.
    - No comment from Odara has yet been turned into a signal — the inbox starts empty, no retroactive migration.
    - No new scheduled task/routine was created for triage.
    - Signals were not mixed with Ideas Intake.
    - No scoring/complex workflow was introduced — just the 5 flat status values.

**Shared State**

- The AI Crew Signal Protocol is now live: dual Persona/Signal-Scout role, a central Odyssey Signals inbox (Governance & Guardrails), the full behavioral rule in AI Crew — Architecture & Persona Mapping, and a one-line pointer on each of the 8 Persona pages.
- The Signal Inbox is empty by design — first real entries should come from live conversations going forward, not backfilled.

**Where We Stopped**

- Implementation is complete and scoped exactly as requested — no changes made outside the 9-step process Odara specified.

**Do Not Touch Yet**

- Do not retroactively migrate old conversations into Signals.
- Do not build a scoring/triage workflow beyond the 5 status values until real signals accumulate and reveal a real need.

**Sources / Affected Pages**

- Governance & Guardrails (Decision Log + new Odyssey Signals inbox)
- AI Crew — Architecture & Persona Mapping (new Signal Scout role section)
- All 8 individual Persona pages (minimal pointer appended)

**Last Contributor:** Claude  

**Session Status:** 🟢 Closed — ready for ChatGPT to read this entry and run the architectural cross-check.

### 🌙 2026-09-26 → 28 — Soul Discovery · Auditoria · Night Shift · Ownership

**Session Focus:** transformar a descoberta da alma do Odyssey em estrutura mínima, sem reconstruir o MVP.

**Claude Contribution (Mayor)**

- *Done:* Discovery Quiz + gap analysis (26/09); auditoria do Notion com oportunidades priorizadas (27/09); revisão da arquitetura da Crew e implementação do piloto Night Shift + Crew Noticeboard em modo sombra, com teste ponta a ponta (28/09); Organization & Capability Ownership + Schedule Task Governance v1 aprovadas com ajustes; roster ganhou Dono/Usada por/Domínio/Estágio; Bom Dia fixado em 11:30 Europe/Madrid; revisão do handoff MVP de Poções.
- *Decisions:* comunicação entre Personas via artefatos no Notion (chats não acordam sozinhos); Hacker = Schedule Steward com limite estrutural no Mayor; execução agendada é recurso escasso (teto inicial 3/dia).
- *Discoveries:* Project Knowledge do Claude defasado vs. Notion; 23/32 Obligations vencidas; 🔺 no item errado; Bom Dia e Manutenção em UTC; Bom Dia manual não tem o bloco Night Shift.
- *Open Questions:* XP no Mini Side Quest; timezone da Manutenção (Hacker); conectores demais nos Tasks.
- *Next Actions:* leitura objetiva do primeiro Bom Dia real (29/09, 12:15); avaliação do piloto em 03–04/10.

**Shared State:** piloto Night Shift rodando (28/09→03/10), modo sombra, contato do Keymaster pausado. Ownership e governança de Tasks aprovadas; migrações são direções a validar.

**Where We Stopped:** aguardando o primeiro turno real.

**Do Not Touch Yet:** Night Shift, Noticeboard, bloco Night Shift do Bom Dia, Command Center — até o fim do piloto.

**Sources / Affected Pages:** ⚓ Crew Noticeboard & 🌙 Night Shift — Pilot · 🏢 Organization & Capability Ownership · ⏳ Schedule Task Governance v1 · AI Chats / Efforts Mapping · Radar de Lares · Decision Log.

**Last Contributor:** Claude (Mayor) · **Session Status:** 🟢 fechada

## 🤖 AI Governance

- Claude is the primary GM running Odyssey day-to-day (check-ins, routines, Notion/Gmail access, backlog management) (see Decision Log above)
- ChatGPT remains in the loop as a complementary input for Side Quests and personal recommendations, given its longer personal history with Odara — how exactly that input gets used/merged is still being figured out together
- Claude has direct access to the Codex (categories, glossary) and the live Task Backlog database as the dominant rule source — it should defer to what's documented there over its own assumptions
- Any AI-proposed structural change (new Category, renamed field, new mechanic) gets logged in the Decision Log above before being treated as final

## 👁️ Odyssey Signals (AI Crew Signal Protocol — desde 2026-09-24)

This inbox is **not** the Ideas Intake below. Ideas Intake = “we have an idea for Odyssey.” Odyssey Signals = “we learned something about Odara.” Keep them separate.

Every AI Crew Persona also acts as a **Signal Scout**: while serving its own domain, it may notice something that could plausibly improve a future decision, a preference/profile, a routine, a Persona, a Source of Truth, a Skill, a Main Quest, or the Odyssey experience overall — and is worth surfacing here. This is not a mandate to log every comment; only signals with real potential to matter.

**Observation ≠ truth.** A Crew member records what it noticed ("Odara demonstrou preferência por X"), never a conclusion ("Odara prefere X"). Nothing here changes a Source of Truth automatically — promotion only happens through review (normally alongside a Weekly Pit Stop / Recap Session), when Odara + Claude + ChatGPT decide together whether it becomes canonical, gets discarded, or stays a hypothesis.

| Signal / Observation | Source Persona | Date | Domain / Area | Confidence / Nature | Possible Source of Truth | Status | Notes / Decision |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Odara lembrou com muito entusiasmo que era viciada em Para Para Paradise e DDR (jogos de dança/ritmo com coreografia) quando mais nova — tinha uma máquina de Para Para no Hot Zone perto de casa, jogava com os amigos, e diz que era muito boa (principalmente em DDR) | Lore | 02/10/2026 | Leisure / Nostalgia / Side Quest | Observação direta — ela mesma trouxe, com energia alta | Side Quest Generator / Player Sheet (interesses) | novo/não revisado | Possível side quest: achar lugar com máquina de DDR/Para Para em Barcelona (fliperama/arcade), ou revisitar via jogo em casa/evento retro. Ela pediu explicitamente pra isso virar matéria-prima de Side Quest. |

*Status values: novo/não revisado · em triagem · confirmado/promovido · descartado · mantém como hipótese.*

## 📥 Ideas Intake (gerido pelo chat de Gestão de Projeto — desde 2026-09-21)

Toda ideia nova (visual, estrutura, mecânica, escopo) entra aqui com fase recomendada e data de próxima revisão, pra nada se perder só por chegar cedo demais.

| Ideia | Área | Fase recomendada | Motivo | Próxima revisão |
| --- | --- | --- | --- | --- |
| Instagram privado só pra si/círculo próximo — registro pessoal, invertendo a lógica de rede aberta | Leisure / Auto Cuidado | Congelada | Devaneio noturno (18/09), ainda sem forma nem urgência — candidata a virar Side Quest de exploração se/quando ela quiser prototipar algo pequeno | Próximo Recap Session |
| Achar um hobby que vire side job/negócio próprio — monetizar experiências, reduzir dependência de CLT | Main Quest (candidata) | Próxima Fase | Devaneio noturno (18/09) com peso maior — conecta com "Encontrar um ritmo de vida com mais entusiasmo" e independência financeira; precisa de mais forma antes de virar Main Quest formal | Próximo Weekly Pit Stop |

## 🅿️ Parking Lot (itens antigos — migração pro formato acima na próxima revisão geral)

Things flagged as "think about this eventually," not urgent enough to design now.

- **Too many separate keywords/routine names.** As more routines get built (Meal Routine, Birthday Alert, Bom Dia, Weekly Pit Stop, etc.), Odara is worried about losing track of which keyword triggers what. She wants something more fluid and connected, not a growing pile of separate named things to remember. No design yet — needs calm, dedicated thought later, possibly once more routines exist and the actual pain point is clearer.
- **House Hunting became a skill, not a Backlog Obligation (2026-08-22).** Removed from Backlog. When designed as a skill/routine chat, preserve these criteria: up to €1600/month, El Born or Sarrià-Sant Gervasi preferred (not strict, needs to be well-connected), 2 bedrooms or 1 large bedroom + office space, MUST be long-term contract (not "temporada") to allow empadronamiento. **Aceita pet (2026-09-10): importante, não bloqueador** — ela está amadurecendo a ideia de um cachorro pequeno que viaje com ela (ver Main Quest "Considerar um cachorro companheiro"), então um apartamento que aceite pet pesa a favor, mas não descarta opções boas que não aceitem. Tied to the Empadronamiento being on hold (see Decision Log).
    
    **Atualização 2026-09-22 (primeira busca real via Idealista, feedback completo dado sobre 6 opções):**
    
    - **AC: importante mas não bloqueador (por ora)** — mesma lógica do pet: aparece como item de checklist (✅/⚠️/❌) em cada opção, não exclui de cara. Ela prefere ver o panorama completo antes de decidir se vira filtro duro.
    - **Filtros duros confirmados:** orçamento, tipo de contrato (longa duração, sem "temporada"/"vacacional"/"solo estudiantes"), exterior/luz, e **mínimo de 50m²** (abaixo disso fica pequeno demais pra avaliar direito, principalmente com 2 quartos, 2026-09-22). Tudo o mais (AC, elevador, varanda, mobiliado, pet) é checklist informativo, não corte.
    - **Mobiliado (completo/parcial/não) substitui o antigo campo "tipo de cozinha"** no formato de apresentação — informação mais útil pra decisão de mudança.
    - **Verificação de status obrigatória antes de apresentar:** sempre reconferir se o anúncio segue ativo (Idealista despublica rápido — 2 de 6 anúncios da primeira leva saíram do ar em poucas horas). Evitar trazer anúncios sem atualização há mais de ~30-40 dias sem reconfirmar que ainda estão ativos.
    - **Mostrar data real de atualização** (ex: "18/09") em vez de texto relativo ("há 4 dias").
    - **Estatísticas de engajamento (views, salvos, emails de interesse), quando disponíveis no próprio anúncio,** entram como contexto de estratégia (ex: alta concorrência + anúncio parado há muito tempo = provavelmente já alugado), nunca como filtro de exclusão.
    - **Formato de apresentação:** opções numeradas (1, 2, 3...) pra referência rápida em conversa; cada uma leva uma nota interna (status/raciocínio) e um one-liner do Claude prefixado com 🤖 (parecer do Claude, não um comentário dela) com o que chamou atenção naquele imóvel.
    - **Removido:** disclaimer genérico sobre política de pet no topo da lista — não agregava, já que o Idealista não expõe isso como campo estruturado; segue mostrando por listagem apenas quando de fato disponível.
    - Ver também o processo de contato/carta de apresentação (link Google Docs + template de email), documentado na página PERFIL DE INQUILINA.
- **Planejar a semana / Cozinhar comida pra semana / Responder Amigos-Famílias** also removed from Backlog (2026-08-22), becoming ad hoc/recurring skills instead of tracked Obligations.
- **Modo Teste vs Modo Produção (flagged 2026-09-02) — Resolvido 2026-09-23.** Ver Decision Log: "Regra de Promoção... Core estático, enhancement progressivo". Fechado como regra de hábito de trabalho (nunca experimentar direto numa rotina viva; promover só após validação funcional), não como arquitetura nova de ambientes/estados.
- **Scheduled Task de manutenção (2026-09-02, sendo criada por ela).** Rotina separada e leve, de madrugada, só pra aplicar a regra de auto-revival (Codex) e resetar a tabela de "Pagar contas mensais" todo mês — antes essas coisas só aconteciam quando algum chat lia o Backlog manualmente, causando itens presos.
- **Chats separados por escopo (2026-09-02).** Building Odyssey volta a ser só decisões estruturais do projeto inteiro. Iteração contínua no Bom Dia Claude (visual, widgets, temas) migra pra um chat dedicado, dentro do mesmo Claude Project "Odyssey" (pra herdar contexto via Project Knowledge, se configurado).
- **Modo Survival vs Modo Fluxo (2026-09-03, GM Charter regra 17).** Originado no chat de viagens, mas identificado como comportamento válido pra todo o projeto — não é específico de viagem. Survival ativa em tópicos de saúde/segurança/integridade, muda o tom completamente, e o GM se posiciona ativamente (não só reporta). Nível de ação (só alertar vs já trazer alternativas) varia por caso, com exceções padrão possíveis se ela definir uma preferência fixa. Fluxo é o padrão normal pra ajustes espontâneos sem risco.
- **Três camadas de documentação, sem conflito (2026-09-05, esclarecido pelo chat Bom Dia Claude).** (1) **Notion** = fonte de verdade — o que humanos consultam e o que rotinas agendadas leem. (2) **Claude Project (`claude/*.md`, dentro do Project Odyssey no [claude.ai](http://claude.ai))** = memória de trabalho do Claude entre sessões daquele chat específico — não é documentação canônica, só contexto operacional pra não começar do zero. (3) **GitHub** = backup do Notion (GM Charter regra 16), só acionado se Notion cair. Decisão canônica (nome oficial, filosofia, regras) sempre mora no Notion.
- **Nome oficial da seção de notícias: "Notícias do Dia" (2026-09-05).** "A Gazeta"/"Odyssey Gazette" continuam válidos como apelido estilístico/kicker visual na tela — não é uma renomeação real, os dois convivem (nome funcional vs decoração).
- **Card "Hoje" aposentado de propósito (2026-09-05).** Durante a v5 do Bom Dia Claude, foi confundido com o "Arcano"/Carta do Dia sob o mesmo nome e removido acidentalmente. Na revisão, decidiu-se não trazer de volta — a Carta do Dia já cobre o papel de "resumo do dia". Marcado Inativo no Registro de Cartas, não deletado.
- **Dívida técnica identificada (2026-09-05): bancos de widgets são aspiracionais, não reais ainda.** Registro de Cartas / Ações Rápidas / Temas nunca são de fato consultados pela rotina agendada — mini cards e Poções estão hardcoded no HTML. Sinalizado pro chat Bom Dia Claude corrigir.
- **Curadoria de Escolha (2026-09-06, GM Charter regra 18).** Regra de interface universal: qualquer sugestão com múltiplas opções (Side Quest, evento, viagem, etc.) vem como máximo 1-3 opções curadas com "porquê" breve, sem hora/logística até ela escolher algo específico. Calibração do filtro acontece só no Recap Session (mensal), nunca vira auditoria ativa dela.
- **Viés natural pra fora de tela nas Side Quests (2026-09-10, Playbook).** Ela quer reduzir tempo de tela substituindo por experiências reais, não restringindo. Side Quests passam a pender por natureza pra atividades fora de tela, em qualquer Mood (Borocôchô calibra o porte, não empurra pra tela como saída fácil). Também nessa sessão: critério de casa atualizado (aceita pet = importante, não bloqueador) e nova Obligation de lazer ("Procurar aula de canto/coral em Barcelona").
- **Project Knowledge + Project Instructions redesenhados (2026-09-02).** Os 4 documentos (Codex, Playbook, GM Charter, Governance) viraram Project Knowledge de verdade (upload de arquivo, não só links) — qualquer chat novo no Project já nasce com esse contexto. As Project Instructions foram enxugadas pra só o operacional (links diretos, estrutura de chats, conectores) — sem duplicar filosofia/vocabulário que já vive no Knowledge, e sem threads ativas temporárias (moradia, papelada), que ficam só no Backlog pra não desatualizar as Instructions sozinhas.
- **Cadência de revisão visual (2026-09-02).** Mudanças visuais grandes revisadas semanalmente (ex: junto do Weekly Pit Stop), não toda sessão — evita iteração sem fim, que vai contra o princípio de reduzir carga cognitiva. Ajustes pequenos/bugs continuam podendo ser corrigidos a qualquer hora.
- **Odyssey Logbook / Diário de Bordo do Odyssey.** Future idea: a chronological, narrative record of meaningful moments in the evolution of the project — architectural turning points, milestones, discoveries, experiments, failures and changes in philosophy. Distinct from the personal diary, and not intended as a technical changelog. Parked intentionally until there is enough project history for it to become meaningful; no new database or workflow now.

## 🔄 Review Cadence

- The taxonomy and rules are treated as a **living system** — reviewed together at least every six months, or sooner if something visibly breaks (e.g. a Category becomes overloaded)
- Nothing here is permanent by default; everything is open to revision as real usage reveals what doesn't work

## 🧭 Scope Boundaries

- Odyssey is a **personal, single-player system** — not a multi-user product, not something designed for anyone else's life
- The GitHub repo holds logic, prompts, and documentation only — no personal task data ever gets committed; that stays in the private Notion database
- Odyssey optimizes for *her* reduced cognitive load and enjoyment — success is never measured by external productivity benchmarks

## 🧱 Change Protocol

1. **Structural decisions happen in the Gestão de Projeto (PM) chat — not in Building Odyssey.** The PM chat evaluates every new idea (visual, structural, mechanic, scope), decides what happens now vs. later vs. never, and is responsible for keeping the whole system (Notion + the chat network) coherent. Building Odyssey is the *"sala de máquinas"*: it receives concrete, already-decided tasks from the PM chat and handles the technical build. Routine-specific chats (Bom Dia Claude, Rotina de Alimentação, Side Quest, etc.) stay execution-only — running the routine, marking things done, day-to-day operational writes (Obligation status, Shopping List items, calendar events that fit the existing flow). None of these chats redesign a rule, change a mechanic, or restructure a page on their own — they flag it, and the decision/edit happens in the PM chat.
2. Propose the change in conversation (with Claude or ChatGPT)
3. Log the decision + reasoning in the Decision Log above
4. Update whichever page(s) the change actually affects (Codex, Playbook, this page, etc.)
5. If the change touches the live database schema, confirm before applying — schema changes can silently clear existing data (learned this the hard way — see Decision Log above)

## 🔐 Data & Privacy

- The Task Backlog (real obligations, routines, personal details) lives only in her private Notion workspace
- The GitHub repo is documentation + code only, safe to make public or share without exposing personal life data

[Arquivo (Removidos do Backlog)](%5BARCHIVE%5D%20Governance%20&%20Guardrails/Arquivo%20(Removidos%20do%20Backlog)%203b3107b19b4981399ef5de0ab9acdb73.md)

**AI Crew audit Step A/B/C executado (2026-09-23)** — handoff do ChatGPT auditado contra o estado real (Scheduled Tasks, os 3 registries do Bom Dia Claude, 19 dias de Run Log, banco AI Crew reconciliado). Ações aprovadas pela Odara e executadas: (1) deletado o Scheduled Task zumbi "Bom dia Claude" (desativado desde 26/08, predecessor pré-v5); (2) formalizadas 3 Poções já reais na AI Crew DB (Calendar Check, O que tá pendente?, Gmail Sweep) sem código novo; (3) validação: Side Quest On-Demand ↔ Mini Side Quest compartilham o mesmo engine documentado no Playbook mas isso ainda não foi testado na prática; City Radar ↔ Eventos tab é uma correspondência MAIS FRACA do que o audit inicial sugeriu — City Radar ainda não existe em forma construída, então não é uma formalização, seria trabalho novo. Bugs diagnosticados mas **não corrigidos** (aguardando decisão separada da Odara): Backlog retornou vazio/indisponível 2x em 19 dias (hipótese: sem query SQL fixa, diferente dos 3 registries); tema "Diário do Capitão" nunca sorteado em 19 dias apesar de Ativo (hipótese: viés de seleção do modelo pra "aleatório" em prosa, não RNG real); Artifact tool bloqueado em sessão agendada/auto em pelo menos 3 dos 19 dias, causando fallback pra SendUserFile sem reconciliar o artefato vivo depois. Daily News Briefing explicitamente fora de escopo por pedido dela.

**Command Center: Diário de Bordo das Rotinas + contador narrativo + prateleira expandida (2026-09-23, v15)** — trabalho autônomo enquanto a Odara definia personas da AI Crew com o ChatGPT. Três adições, todas sem depender de dados externos ainda pendentes:

1. Faixa "Diário de Bordo das Rotinas" abaixo do mapa — todas as rotinas nomeadas (Bom Dia Claude, Manutenção do Backlog, Rotina de Alimentação, Side Quest On-Demand, Diário Pessoal, Recap Session) num só lugar, com o mesmo código de cor 🟢/🌸 do resto do sistema. Antes, só dava pra ver status de skill clicando em cada ilha ou agente.
2. Chip narrativo "30 amanheceres registrados" na faixa de info rápida, puxado do número real de execuções do Scheduled Task do Bom Dia Claude (Card Pull of the Day) — primeira vez que um dado de automação real vira flavor text direto na tela principal.
3. Prateleira de poções ganhou 3 atalhos novos: testar Diário Pessoal, testar Recap Session, e o Registro de Chats — reduz a fricção pra ela mesma disparar os testes das rotinas 🌸 sem precisar de mim junto.

Reasoning: pedido explícito foi "trabalhar de forma livre" identificando melhorias de narrativa/experiência/automação/liberdade enquanto ela trabalha nas personas em paralelo — nada aqui depende de links de chat reais ou avatares, então dava pra avançar sem bloqueio.

## 🔄 Handoff — AI Crew MVP Poções (2026-09-24)

**Para Claude / Cláudio — revisar antes de considerar esta arquitetura final:**

ChatGPT + Odara fecharam hoje o **MVP real de Poções**. O objetivo não é completar uma árvore teórica de Skills; é manter um conjunto pequeno de capacidades que Odara realmente pretende usar no dia a dia. A memória e o trabalho já construído por Claude sobre cada rotina têm precedência prática: **revisitar as páginas, prompts, workflows e decisões existentes e validar se esta modelagem representa corretamente o que já foi construído. Não substituir o desenho existente por uma abstração nova só para encaixar no modelo.**

### MVP atual

1. 📧 **Gmail Sweep — Active**
    - Lote de **5 e-mails não lidos por vez**.
    - Trazer um lote para Odara resolver junto; só depois buscar os próximos 5.
    - A regra é operacional, não um tracking de produtividade.
    - A capacidade já existia; a formalização de hoje não deve apagar o workflow detalhado já construído por Claude.
2. 🌅 **Bom Dia, Claude / Morning Ritual — Manual Run — Active**
    - A execução manual deve disparar **a mesma rotina** do Schedule Task.
    - Não criar uma segunda rotina paralela nem uma versão reduzida diferente.
    - O Schedule Task continua sendo o gatilho automático; a Poção é o gatilho sob demanda para rodar a mesma execução em qualquer horário.
    - **Revisar o desenho técnico existente do Bom Dia antes de alterar qualquer coisa.**
3. 🧭 **City Radar / Local Lens — Active**
    - Barcelona & Catalonia Discovery como capacidade de descoberta/contexto.
    - Importante: o audit anterior mostrou que City Radar ainda não estava realmente construído como capacidade independente; portanto, o registro como MVP hoje é uma decisão de arquitetura/escopo, **não evidência de que a implementação já esteja pronta**.
    - Revisar o que Claude já construiu/documentou sobre descoberta local e distinguir claramente o que já existe do que ainda precisa ser construído.
4. 🌟 **Side Quest Generator — Active**
    - Reutiliza o engine existente de Side Quest On-Demand.
    - O engine documentado inclui os dois modos (livre/ancorado em Main Quest), mistura de sinais internos + dados externos, calibração de porte pelo Mood e aprendizado via Recap Session, sem tracking silencioso.
    - Confirmar se o workflow atual realmente corresponde a esse engine e se o Mini Side Quest do Bom Dia usa o mesmo motor na prática.

### Decisão de escopo

**Não criar agora** as dezenas de Skills teóricas mapeadas por Persona. Capacidades naturais de uma Persona, recursos que ela pode consultar e pequenos jobs que não justificam uma interface própria permanecem fora do catálogo MVP. Podemos promover novas capacidades quando o uso real demonstrar necessidade.

### O que Claude deve fazer agora

- Reabrir/revisitar os workflows e páginas que já construiu para **Gmail Sweep, Bom Dia Claude, City Radar e Side Quest**.
- Comparar o MVP acima com a implementação real, preservando o conhecimento e os detalhes já existentes.
- Apontar **somente discrepâncias materiais, riscos ou decisões que precisem de aprovação da Odara**.
- Se estiver tudo coerente, não reconstruir nada: apenas registrar que o desenho existente está alinhado.

**Princípio:** *Experiment freely. Protect what works. Promote only after it has been validated.*

**Last contributor:** ChatGPT  

**Handoff status:** 🟡 Awaiting Claude review

### ↳ Revisão do Claude (Mayor) — 28/09/2026

Li as páginas reais, o roster, o Registro de Runs do Bom Dia e os Scheduled Tasks. Nada reconstruído. Só discrepâncias materiais:

1. **📧 Gmail Sweep — alinhado.** Lote de 5 bate com a AI Crew Architecture e com o roster (Active). Observação fora da Poção: o Registro de Runs mostra "Gmail offline (run automático)" em vários dias entre 13 e 24/09 — o conector falha com frequência nas execuções agendadas. Assunto para o Hacker, não para a Poção.
2. **🌅 Bom Dia Manual Run — divergência nova (criada em 28/09).** A Poção manual aponta para a página da rotina no Notion; a execução agendada usa o prompt do Task. Desde 28/09 o bloco 🌙 Night Shift só existe no prompt do Task — então o Bom Dia manual **não mostraria** a seção Night Shift. Viola o princípio "mesma rotina, dois gatilhos". Correção proposta (depois do piloto, dentro da revisão do Bom Dia): mover o bloco para a página da rotina, que os dois gatilhos leem. Não alterado agora por decisão da Odara (sem mudança estrutural durante o piloto).
3. **🧭 City Radar / Local Lens — coerente com a ressalva do handoff.** Continua sendo um atalho (prompt-launcher) no Treasure Chest; desde 25/09 a capacidade real de descoberta local vive no Catalan Corsair, que agora é o Dono no roster. Não há implementação independente — e não precisa haver até o uso pedir.
4. **🌟 Side Quest Generator — um ponto para a Odara decidir.** O Mini Side Quest do Bom Dia está exibindo "+XP" (ex.: "+15 XP" em 27/09). O engine documentado e o Playbook dizem que o Memory Log é a progressão e XP "nunca é o ponto". Se o XP não significa nada pra ela, sai; se significa, entra no Playbook. Confirmar na prática se o Mini Side Quest e o Side Quest On-Demand usam o mesmo motor segue pendente (depende de teste com a Odara).

**Decisão de escopo (não criar Skills teóricas) — alinhada** e já incorporada no Capability Model (27/09) e no Organization & Capability Ownership (28/09).

**Handoff status:** ✅ Reviewed by Claude (28/09) — 2 pontos abertos para a Odara/Bom Dia (itens 2 e 4).

## 🔄 Handoff — Roteiro pós-Discovery Quiz (2026-09-26)

**Para ChatGPT / Chatty — contexto e próximos passos aprovados por Odara:**

Fizemos hoje uma sessão de descoberta ("Soul Discovery") sobre o que o Command Center deve *sentir* quando ela volta, e cruzei isso com toda a arquitetura existente (Codex, Playbook, GM Charter, Governance, AI Crew Architecture, Command Center v19). O documento completo e o gap analysis estão guardados no Project Knowledge do Claude (`claude/discovery-quiz-2026-09-26.md` e `claude/gap-analysis-discovery-quiz-2026-09-26.md`) — se precisar do texto completo, peça pra Odara exportar/colar.

**Achado central:** a alma do projeto é *"Eu não preciso carregar tudo na minha cabeça sozinha SEM AJUDA"*. A conclusão do gap analysis foi **zero mudanças estruturais necessárias agora** — a arquitetura (Internal Trust Boundary, Signal Scout, Sources of Truth, MVP protection) já responde a essa descoberta por instinto. O que falta não é arquitetura nova, é uma capacidade específica ainda não construída.

### Foco de build aprovado agora

**Revisitar o Bom Dia Claude / Morning Ritual de ponta a ponta** (workstream já marcado como "parked for full revisit"). Motivo: é onde vive o gap mais concreto encontrado — a experiência de **retorno após dias fora** ("alguém segurou isso por mim enquanto eu estava fora" antes de qualquer lista aparecer) não existe hoje em nenhum lugar do sistema. Isso acontece no chat dedicado Bom Dia Claude, não aqui.

**Pergunta em aberto pra resolver durante essa revisão:** onde vive a "pergunta difícil ao vivo" (qualquer parte da Crew podendo notar uma contradição e perguntar na hora, não só registrar no Signal Scout pra revisão depois)? Ainda não tem dono definido.

### Trilha paralela, sem prioridade (housekeeping, zero risco)

Fechar pendências pequenas já listadas no `command-center-versions.md`: links reais dos chats "a recrutar" (Clothmaster, Keymaster, Lorekeeper, Merchant, Bard, Beastmaster, Healer) e o chip hardcoded "30 amanheceres registrados".

### Explicitamente NÃO construir agora

Curadoria dinâmica do Command Center (esconder/priorizar conteúdo por sobrecarga), novos Personas ou Treasures além do roster atual (9+9), redesign do mapa de ilhas (redução da ilha de games / ilhas de hobby — isso é Odyssey 2.0, ainda cedo).

### Pedido pra ti, Chatty (art direction)

Nada de assets finais ainda — isso é fase conceitual. Mas já pode começar a pensar, como diretor de arte, em **linguagem visual/tom pro momento de reencontro** (o "Bem-vinda de volta, já organizei o convés" do Discovery Quiz): que sensação de cor/composição comunica "isso foi segurado por você" antes de qualquer lista aparecer — sem redesenhar nada do Bom Dia Claude existente ainda, só explorando o tom emocional desse momento específico. Odara vai te mandar imagens/referências direto quando essa exploração começar a ficar concreta (isso não passa bem por Notion).

**Last contributor:** Claude

**Handoff status:** 🟡 Awaiting ChatGPT input