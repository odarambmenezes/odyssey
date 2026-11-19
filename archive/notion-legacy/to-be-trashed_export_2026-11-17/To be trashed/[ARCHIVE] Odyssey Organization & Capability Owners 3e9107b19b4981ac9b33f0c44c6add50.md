# [ARCHIVE] Odyssey Organization & Capability Ownership

> **Status:** 🟢 Estrutura aprovada pela Odara em 28/09/2026 — Fase B aplicada. Mapa em preenchimento por auditoria. (ChatGPT: leitura pendente para o eixo de experiência.)
> 

> 
> 

> Próxima camada do 🏢 Operating Model. Define **quem é dono de quê** entre as capacidades do Odyssey. Não cria banco novo, não migra dados, não altera o Night Shift (piloto segue em paralelo).
> 

> 
> 

> **Princípio da fase:** Build in parallel, validate in reality.
> 

# 1. Onde esta camada se encaixa

| Camada | Responde | Onde vive |
| --- | --- | --- |
| 🧭 Capability Model | **O que** existe (Skill, Treasure, Workflow, Task) | página própria |
| 🏢 Operating Model | **Quem coordena** (Lore · Mayor · ChatGPT · Odara) | página própria |
| 🏢 **Organization & Capability Ownership** (esta) | **Quem é dono** de cada capacidade e **quem pode mudá-la** | esta página + roster existente |
| 🔐 Trust Boundary | **Quem pode mutar a estrutura** | Governance & Guardrails |

Nada aqui substitui as camadas acima. Esta página só junta "o que" com "de quem".

# 2. Dois tipos de autoridade

### 🔧 Ownership operacional (Persona)

A Persona pode **criar, ajustar e usar** Skills e Workflows **dentro do próprio domínio**, sem pedir licença.

**Schedule Tasks são a exceção (v2, 28/09):** a Persona pode ser owner operacional de uma Task e propor novas, mas **não cria nem altera Task sozinha**. Execução agendada é recurso escasso (≈ 5/dia no plano atual) e é governada pelo Hacker — ver ⏳ Schedule Task Governance (subpágina).

### 🏗️ Autoridade estrutural (Builders)

Mayor (estrutura), Hacker (saúde técnica), ChatGPT (experiência) alteram o que é **compartilhado pelo sistema inteiro**.

### 👑 Autoridade final (Odara)

Decisões significativas de vida e qualquer ação externa fora de uma autorização permanente já dada.

## Os 7 papéis (quem responde por quê)

| Papel | Quem | Responde por | No roster |
| --- | --- | --- | --- |
| Persona Owner | a Persona do domínio | o **resultado** na área da vida | campo Domínio |
| Skill Owner | Persona (ou Builder) que mantém a Skill | a **qualidade** da capability | campo Dono (linha tipo Poção/Skill) |
| Schedule Task Owner | Persona cujo trabalho precisa acontecer | **o que** a Task faz e se ainda é necessária | campo Dono (linha tipo Schedule Task) |
| Schedule Steward | 🖥️ Hacker | **o sistema de agendamento**: orçamento, formato, consolidação, saúde | sempre o Hacker — sem campo |
| Structural Authority | ⚓ Mayor | arquitetura, superfícies compartilhadas, Governance | — |
| Experience Oversight | 🎭 ChatGPT | experiência e narrativa das superfícies | — |
| Final Authority | 👑 Odara | decisões significativas | — |

Uma mesma Persona pode acumular papéis (ex.: o Bard é Persona Owner de Música e Task Owner do Radar de Shows). O Hacker nunca vira dono do trabalho — só do slot onde ele roda. E governa o agendamento **dentro** da governança aprovada: pode rejeitar, consolidar e ajustar configurações, mas mudar a própria governança ou a estrutura do sistema escala para o Mayor.

## O teste da linha (operacional × estrutural)

Uma mudança é **operacional** (a Persona decide sozinha) quando **todas** são verdadeiras:

1. Mexe só em Sources of Truth e artefatos do próprio domínio.
2. Usa conectores que já estão em uso no Odyssey.
3. Não muda uma superfície compartilhada: Bom Dia, Command Center, Crew Noticeboard (estrutura), Backlog (estrutura), Governance, taxonomia.
4. Não cria interrupção nova para a Odara (push, e-mail, notificação) — ver §4.
5. Não faz ação externa além de uma autorização permanente existente.

Se **qualquer** item falha → é estrutural (Builders) ou é decisão da Odara (ação externa / vida).

**Exemplo:** o Bard criar o Radar de Shows e o scan quinzenal = operacional ✅ (já validado no Decision Log de 27/09). O Bard mudar como o Bom Dia exibe shows = estrutural (superfície compartilhada).

# 3. Regras de ownership

1. **Reusar antes de criar.** Antes de criar uma capability, a Persona procura no registro se já existe algo equivalente. Se existe, usa (e pode propor melhoria ao dono).
2. **Dono ≠ exclusivo.** Qualquer Persona pode usar uma capability de outra. O dono mantém a qualidade; quem usa não recria.
3. **Nada de automação invisível.** Toda Skill, Workflow ou Schedule Task criada por uma Persona ganha uma linha no registro (§6) no mesmo dia. Sem registro, não existe.
4. **Mudança em Task deixa rastro.** Alterar o prompt ou horário de um Schedule Task = uma linha no histórico da capability (data, o que mudou, por quê).
5. **Horário sempre com fuso.** Todo Task novo usa `CRON_TZ=Europe/Madrid` (o Bom Dia sem fuso roda às 11h30 por isso).
6. **Domínio variante usa a Skill compartilhada.** Ex.: o Keymaster não cria uma "voz da Odara" própria; usa a Skill de voz + o template do domínio dele.
7. **Aposentar também é ownership.** O dono marca como descontinuada a capability que não é mais usada, em vez de deixar rodando.
8. **Execução agendada é recurso escasso.** A pergunta não é "isso pode ser uma Task?", e sim "isso precisa consumir uma execução agendada?". A Persona identifica a necessidade; o Hacker decide como ela roda (Skill ad hoc, módulo de um slot existente ou Task nova).

# 4. Quando resolver sozinho × quando subir

> A Odyssey tira coordenação da Odara. Não cria uma camada nova de coordenação para ela.
> 

**Resolve e registra** (não sobe): tudo que passa no teste da linha e usa uma capability existente.

**Sobe** somente se houver pelo menos um:

| Gatilho | Sobe para |
| --- | --- |
| 🔺 status legal, dinheiro além do combinado, saúde, relações importantes, algo irreversível | Odara |
| Ação externa fora de autorização permanente | Odara |
| Ambiguidade real sobre o que a Odara quer (não dá pra inferir do que já foi dito) | Odara |
| Conflito material entre domínios (ex.: Clau × Jaume) | Odara, com as duas visões |
| Falha no teste da linha (mudança estrutural) | Mayor (+ Hacker técnico, + ChatGPT se afeta experiência) |

**Orçamento de interrupção:** o canal padrão para chegar na Odara é o Bom Dia. Push/notificação fora dele só para 🔺, prazo Rígido próximo, ou algo que ela pediu explicitamente (ex.: show na Espanha do Radar de Shows — mantido).

# 5. Skills — a biblioteca compartilhada da Crew

**Definição:** um processo repetível, validado pela Odyssey, que pode ser usado por uma ou várias Personas.

### Ciclo de vida

🧪 **Candidata** → existe e já foi usada de verdade, mas só por quem criou.

🟢 **Validada** → usada com sucesso em situação real pelo menos 2 vezes, com cartão preenchido.

🌐 **Compartilhada** → validada e usada por pelo menos uma Persona além da dona.

📦 **Descontinuada** → não usar; mantém-se o registro.

### Cartão de Skill (curto, no corpo da linha do registro)

```
Dono:            Persona
Usada por:       Personas que já usam
Faz:             1 frase
Entrada:         o que precisa receber
Saída:           o que entrega e onde
Sources of Truth: de onde lê
Limites:         o que nunca faz (ex.: não envia sem autorização)
Histórico:       data · mudança · por quê
```

### O exemplo pedido já existe pela metade

"Generate Message in Odara's Voice" já tem dois pedaços: **🪶 The Quill** (reclassificada como Skill em 25/09) e a página **Perfil de Voz da Odara** (Source of Truth). O Keymaster já usa uma variante (template de e-mail v2). Primeira candidata natural a 🌐 Compartilhada, com dono a definir na auditoria.

# 6. Onde o mapa vive (sem banco novo)

O banco **AI Chats / Efforts Mapping** (roster da Crew) já classifica cada linha como Persona, Poção, Schedule Task ou Builder. Ele **já é** um registro de capacidades.

**Proposta (não aplicada — mudança de schema precisa de OK):** acrescentar ao banco existente:

- opção **Workflow** no campo Type (e renomear "Poção" para "Skill" quando a Odara quiser — hoje o Capability Model já usa Skill);
- **Dono** (relação com a própria base, apontando pra uma linha de Persona/Builder);
- **Usada por** (relação, múltipla);
- **Domínio** (seleção);
- **Estágio** (Candidata / Validada / Compartilhada / Descontinuada).

Com isso, a visão "Persona → Domínio → Skills → Workflows → Tasks → Compartilhadas → Dependências → Escalação" é só um **filtro/agrupamento** do roster — não um banco novo.

# 7. Mapa-semente (só o que já é fato; resto se preenche na auditoria)

| Persona | Domínio | Possui (operacional) | Usa de outros | Pares | Escala para |
| --- | --- | --- | --- | --- | --- |
| 🧙‍♀️ Lorekeeper | coordenação da vida, memória, diário | **Night Shift** (regras de roteamento, formato da Entrada, limiar de relevância) | — | toda a Life Crew | Mayor (estrutural) · Odara |
| 🔑 Keymaster (Clau) | moradia, contratos, burocracia | Radar de Lares (busca/triagem) · lente jurídica · template de e-mail v2 · *Task diário (planejado)* | Voz da Odara (variante) | Corsair | Lore · Odara (🔺 / contato) |
| 🏴‍☠️ Catalan Corsair (Jaume) | Barcelona/Catalunha, bairros | City Radar / Local Lens · regra de rota com pins | — | Keymaster | Lore |
| 🎵 Bard | música | Radar de Shows · Scan de shows (🧪 candidata) · Task Scan Quinzenal | — | Corsair (eventos locais) | Lore |
| 🧭 Navigator · 👗 Clothmaster · 🛍️ Merchant · 🐺 Beastmaster ☀️ Healer | — | *a auditar* |  |  | Lore |

**Capabilities sem dono hoje (decidir na auditoria):** Bom Dia (Workflow + Task) · Gmail Sweep · Side Quest · Supplies · The Ticket · The Quill · Manutenção Diária do Backlog.

### Future Hiring — 💰 Finance

**Status:** 🟡 Hiring / A contratar — posição registrada no roster, Persona ainda não ativada.

**Working name:** To be defined. **Historical note:** “The Quartermaster” was an early provisional name for the future Finance persona, but the title is now canonically assigned to [Gibbs, The Quartermaster](https://app.notion.com/p/Gibbs-The-Quartermaster-401107b19b49801db951e8660ae0f868?pvs=21) (career and business domain). The future Finance role remains separate and unnamed; do not infer an identity or change its mission.

**Domain:** Personal Finance & Financial Strategy · **roster domain:** Transversal.

**Mission:** fornecer contexto financeiro, guardrails e visão de impacto para que a Crew tome decisões mais conscientes dentro da realidade financeira da Odara.

**Transversal role:** Finance deverá apoiar outras Personas quando suas recomendações tiverem impacto financeiro — especialmente Merchant (compras), Beastmaster (custo de animal), Keymaster (moradia), Navigator (viagens) e Clothmaster (estilo/serviços).

**Authority boundary:** Finance informa e orienta; não vira automaticamente porteiro de decisões da Odara. A autoridade final continua com a Captain, salvo regras explícitas futuras.

**Sensitive domain:** antes da ativação, será necessário definir Sources of Truth, acesso, privacidade, limites de exposição, cálculos permitidos e ações que exigem aprovação explícita. Não criar nem popular dados financeiros sensíveis ainda.

**Design principle:** Finance deve funcionar como uma camada transversal de contexto e decisão, não como um simples controlador de contas.

**Builders:** ⚓ Mayor → Command Center, estrutura do Crew Noticeboard, integração com o Bom Dia, registro de capabilities, Governance. 🖥️ Hacker → saúde dos Tasks (fuso, conectores, falhas). 🎭 ChatGPT → experiência e narrativa das superfícies compartilhadas. *(Hacker ainda não tem linha no roster.)*

### Night Shift — divisão de ownership (documental, nada muda no piloto)

- **Lore (operacional):** quem recebe o quê, formato da Entrada, limiar de relevância, tom do resumo "Pro Bom Dia".
- **Mayor (estrutural):** limites do modo sombra, esquema do Noticeboard, integração com o Bom Dia, horário, conectores. Motivo: essas peças são superfícies compartilhadas por toda a Crew.
- Durante o piloto (até 03/10), nenhuma das duas partes altera o Task.

# 8. 📊 Monthly Area Reports

**Objetivo:** cada área consegue dizer, uma vez por mês, o que está acontecendo — sem a Odara ter que perguntar a cada Persona.

**Como gerar sem criar trabalho novo:** um único Schedule Task mensal (último domingo do mês) que "veste" cada Persona com atividade no mês e lê o que já existe: Noticeboard, Night Shift Log, Signals, Backlog por categoria, os Sources of Truth do domínio, histórico das capabilities. **Não** um Task por Persona. Área sem atividade = uma linha ("sem movimento").

**Template por área (curto):**

- O que aconteceu
- O que está funcionando
- O que não está
- Problemas
- Oportunidades
- Dependências
- Capabilities novas ou necessárias
- Tasks existentes da área (ainda necessárias?)
- Tasks propostas
- Possíveis consolidações
- ⬆️ Sobe para liderança (máx. 3)

**+ seção do Hacker (sempre):** uso do orçamento de execuções no mês, falhas, propostas recebidas e decisões tomadas, consolidações sugeridas.

**Saída:** uma página por mês (não banco), com as áreas + um resumo consolidado de 1 página para o Council.

**Nível de acesso:** o relatório vai ser lido pelo ChatGPT → conteúdo **Aberto**. Lore e Healer reportam só insight derivado, nunca conteúdo íntimo.

# 9. ⚓ Captain's Council

**Quem:** Odara + ChatGPT + Mayor (+ Lore quando relevante).

**Quando:** mensal, depois dos Area Reports.

**Pré-leitura:** só o resumo consolidado de 1 página. A Odara não precisa ler os relatórios por área.

**Pauta fixa (só isso):**

1. O que mudou?
2. O que aprendemos?
3. O que está funcionando?
4. O que não está?
5. O que precisa mudar?
6. O que entra no próximo ciclo?
7. O que deliberadamente **NÃO** vamos construir?

**Depois do Council:** Mayor → estrutura e execução · ChatGPT → experiência e narrativa · Lore → continuidade e conexão com a vida · Hacker → stewardship técnico e de agendamento · Personas → execução nos seus domínios.

**Saída:** roadmap do ciclo em três colunas (Agora · Próximo · Não) + linhas no Decision Log.

**Não é:** reunião operacional, revisão de tarefa por tarefa, lugar para resolver o que uma Persona já podia resolver sozinha.

**Mecânica prática:** como ChatGPT e Claude não estão no mesmo chat, o Council acontece em duas voltas: (1) ChatGPT lê o resumo e deixa a visão de experiência no handoff; (2) Odara + Mayor fecham o roadmap. A Odara só participa da volta 2.

# 10. Riscos

| Risco | Mitigação |
| --- | --- |
| Personas criando Tasks demais (custo, colisão de horário, conectores) | Registro obrigatório + Hacker revisa a saúde dos Tasks no Area Report mensal |
| Duas Personas criando a mesma coisa | Regra "reusar antes de criar" + registro filtrável |
| "Operacional" virar desculpa para mudar superfície compartilhada | Teste da linha em 5 pontos |
| Notificações se multiplicando | Orçamento de interrupção: Bom Dia como canal padrão |
| Reports e Council virando mais trabalho para a Odara | Um Task gera tudo; ela lê 1 página; Council com 5 perguntas fixas |
| Conteúdo íntimo chegando ao ChatGPT | Reports no nível Aberto; Lore/Healer só derivado |

# 11. Implementação em fases

**Fase A — agora (feita):** esta página, sem mudança em dados.

**Fase B — ✅ feita em 28/09:** campos Dono, Usada por, Domínio, Estágio + opção Workflow no roster ("Poção" mantido, renomear só quando a Odara quiser). Domínio preenchido nas 9 Personas e nos Builders; donos só onde já era fato (City Radar → Corsair, Night Shift → Lore, Radar de Shows → Bard, Radar de Lares → Keymaster). Registradas as capabilities que existiam fora do roster: Night Shift, Radar de Shows, Radar de Lares, Manutenção Diária, Hacker (Draft).

**Fase C — auditoria da Crew:** Persona por Persona, usando as capabilities reais (junto com a Capability Audit já aprovada).

**Fase D — fim de outubro:** primeiro Area Report (só áreas com atividade) + primeiro Captain's Council, já com a evidência do piloto Night Shift.

# 12. Não fazer agora

- Banco novo para ownership, reports ou Council.
- Alterar o Night Shift durante o piloto.
- Um Task por Persona para relatório.
- Preencher o mapa com suposição — só fato auditado.
- Dar autoridade estrutural a qualquer Persona.

---

> **Personas são donas do que fazem. Builders são donos do que é de todos. Odara é dona da vida dela.**
> 

[[ARCHIVE] Schedule Task Governance v1](%5BARCHIVE%5D%20Odyssey%20Organization%20&%20Capability%20Owners/%5BARCHIVE%5D%20Schedule%20Task%20Governance%20v1%203e9107b19b4981fdae2bc24389bbd955.md)