---
name: auditoria-notion-oportunidades-2026-09-27
description: Auditoria do Notion do Odyssey (27/09) — oportunidades priorizadas de melhoria em experiência, narrativa, usabilidade, clareza, automação, conectores e otimização, filtradas pelo teste de decisão do Discovery Quiz.
sources: [chat]
---

# Auditoria do Notion — Oportunidades de melhoria

**Data:** 2026-09-27 · **Autor:** Mayor (Building Odyssey)
**Escopo lido:** página raiz Project Odyssey, Governance & Guardrails, AI Crew Architecture, Capability Model, Skills/Workflows, Bom Dia Claude, Player Sheet, Resources, Task Backlog (schema + dados), Diário Pessoal, e os 3 Scheduled Tasks ativos.
**Filtro aplicado:** cada item passou pelo teste "isso tira peso da cabeça da Odara ou cria mais uma coisa pra ela carregar?". Quase tudo abaixo é *limpeza e conexão* do que já existe — nada pede banco novo, Persona nova ou Treasure novo.

---

## 🔝 Top 5 — maior impacto por esforço

### 1. O Backlog virou a "bagunça pra quando eu voltar" (experiência / alívio)
Dados de hoje: **23 de 32 Obligations abertas estão com prazo vencido.** Parte é ruído, não pendência real:
- 4 mensagens pontuais de 10/09 ainda abertas ("Responder o Iago", "Responder a Lucila", "Mandar mensagem pra minha mãe", "Responder ao pessoal sobre ida à casa deles **hoje**").
- 7 "Agendar [médico]" + 1 "📞 Lembrete: organizar agendamentos médicos" — 8 linhas pro mesmo assunto, todas travadas em 18/09.
- Duplicata: "Procurar aula de canto / coral" e "🔺 Procurar mais aulas de coral".
- "CNH Brasileira (referência — sem ação pendente)" — referência, não ação.
**Proposta:** uma triagem de 15 min (ela decide, eu preparo) + transformar os 8 itens de saúde num único **Boss "Temporada de Consultas"** (o Codex já prevê Boss com cuidado extra). É exatamente o "alguém segurou isso por mim" do Discovery Quiz aplicado ao dado real.

### 2. 🔺 no lugar errado, e o item 🔺 de verdade sem alarme (prioridade legal)
- O 🔺 (reservado a status legal na Espanha, GM Charter regra 8) está num item de **coral**.
- "Encontrar um Long Term Contract" — Rígido, prazo **22/10**, e a Governance registra que contrato longo é o que permite o **empadronamiento** — está sem 🔺.
- "Deadline Alert" está como "Design pending" desde julho. Hoje nenhum mecanismo avisa quando um item Rígido se aproxima.
**Proposta:** corrigir os dois 🔺 agora (edição simples) + desenhar o Deadline Alert mínimo: Rígido com prazo ≤14 dias → aviso. Começar só com Rígido; Flexível nunca vira alerta.

### 3. O Project Knowledge do Claude está desatualizado em relação ao Notion (clareza / drift)
Os docs 01–04 do Project são de 02/09. Todo chat do projeto lê isso primeiro. Divergências concretas:
- 04-Governance diz "mudança estrutural só no Building Odyssey"; o Notion diz "decisões estruturais no chat de Gestão de Projeto (PM), Building Odyssey é sala de máquinas"; e o Trust Boundary lista 3 chats Builder (Mayor, PM/Build, Building Odyssey). **Três versões de quem tem autoridade.**
- Nenhum doc do Project cita Trust Boundary, Capability Model ou a AI Crew.
- Playbook lista 6 Main Quests; o Backlog tem 8 (inclui "Long Term Contract" e "Procurar um Esporte").
Provavelmente é uma das causas do Bom Dia "desalinhado". **Proposta:** um passe de sincronização Notion → Project (Notion vence), com linha "sincronizado em DD/MM" no topo de cada doc, e decisão única sobre quem tem autoridade estrutural.

### 4. O Bom Dia chega às 11h30, não 9h30 — e roda num modelo antigo (automação)
O Task "Card Pull of the Day" usa cron `30 9 * * *` **sem fuso**, que roda em UTC → **11h30 em Madrid** (último disparo real: 11h39). A documentação diz 9h30. Ele também está fixado em `claude-sonnet-4-6` com prompt de 05/09 (anterior ao Discovery Quiz e ao Capability Model).
**Proposta:** confirmar se 11h30 é intencional; se não, ajustar pra `CRON_TZ=Europe/Madrid`. Troca de modelo e prompt entram na revisão do Bom Dia que já está em curso — decisão sua, não minha.

### 5. idealista está conectado e ninguém usa (conector com impacto 🔺)
O conector do idealista está disponível nesta conta. Os critérios de busca de casa já existem (estão no Parking Lot da Governance: até €1600, El Born/Sarrià, 2 quartos ou 1+escritório, contrato longo pra empadronamiento, aceita pet = bônus). Isso serve direto ao item Rígido de 22/10.
**Proposta:** The Keymaster usa o idealista pra uma busca sob demanda com esses critérios; se funcionar, avaliar um Task semanal enquanto o contrato não sair. Critérios saem do Parking Lot e viram o Tenant Profile (Source of Truth que a AI Crew já cita mas ainda não existe como página).

---

## 🎭 Narrativa e experiência

- **Página raiz tem dois manifestos.** Abre com "Chaos isn't the enemy" + Design Principles + Success Metrics, e só no rodapé vem "Soul & System Principles — Canonical" (a alma real). "❤️ The Soul of Odyssey" aparece duas vezes. Success Metrics não cita **alívio**, que virou a métrica central. **Proposta:** reordenar — Alma no topo, navegação logo abaixo, manifesto antigo condensado.
- **"Research Backlog & Open Decisions" na raiz** ainda pergunta "como a gamificação funciona na prática?" e "qual é o MVP?" — já respondidas. Arquivar.
- **"+15 XP" no Mini Side Quest do Bom Dia.** O Playbook diz que o Memory Log é a progressão e XP "nunca é o ponto"; o Discovery Quiz rejeita mecânica decorativa. Vale perguntar se o XP ainda significa algo pra você ou se sai.
- **Odyssey Signals inbox está vazia** desde 24/09, com 9 Personas como Signal Scouts. Pode ser o limiar funcionando (bom) ou o protocolo não disparando (ruim). Não construir nada — só olhar no próximo Weekly Pit Stop.
- **Player Sheet parada desde 22/08:** "O que recarrega vs. drena" vazio, Mood Vocabulary "mais por vir". Não criar formulário — deixar Lorekeeper/Recap alimentarem via Signals.

## 🧭 Usabilidade e clareza da informação

- **Categoria do Backlog mistura áreas da vida com tipo de quest.** "Main Quest" e "Side Quest" são opções de Categoria, mas o campo Tipo já separa Obligation/Quest. O Codex diz que Categoria é área da vida e pode ser múltipla; no schema é seleção única. "Financeiro" em português entre categorias em inglês. → Mudança de schema passa pelo Change Protocol; **primeiro passo seguro são views**, sem tocar schema.
- **Views que faltam / quebradas:** a view "Quests" não tem filtro (mostra tudo). Não existe view "Hoje/Esta semana", "🔺 Legal" nem "Aguardando Terceiros".
- **Duplicatas de página:** "Diário Pessoal (Registro Ad Hoc)" e "Diário Pessoal (Log Ad Hoc)" coexistem em Skills/Workflows.
- **Skills, Workflows and Automations está defasada:** lista Google Calendar como "planejado" (já conectado), traz perguntas abertas de julho, não reflete o Capability Model. Candidata a virar o inventário vivo da Capability Audit.
- **Sources of Truth espalhadas:** Perfil de Entretenimento e Perfil de Viagem em Resources; Corpo & Vitalidade em Skills; critérios de casa no Parking Lot da Governance; Radar de Shows em Resources. **Proposta:** a lista de Sources of Truth da AI Crew vira índice com link direto pra cada página (sem mover nada).
- **Resources** diz "deve ficar quase vazia" e tem 4 seções vazias — mas hoje abriga Sources of Truth. Renomear ou limpar as seções vazias.
- **Página do Bom Dia tem ~54 mil caracteres, incluindo CSS completo.** A própria Governance diz que código mora em artefato/GitHub e Notion documenta em prosa. Cada run lê a página inteira. Separar spec (prosa) de template (artefato) deixa a rotina mais leve e mais fácil de manter.
- **Parking Lot: "palavras-chave/nomes de rotina demais".** O Capability Model + Treasure Chest já respondem a isso. Dá pra fechar o item com um ponteiro.

## ⚙️ Automação

- **Manutenção diária só faz auto-revival.** A regra do Codex "Flexível atrasado ~2x o intervalo → escala como cuidado" não é aplicada por ninguém. Extensão silenciosa proposta: marcar em "Notas do Claude" (sem notificar) itens Flexíveis com 2x de atraso e mensagens pontuais com mais de 7 dias, pra aparecerem como pergunta na próxima triagem.
- **Deadline Alert** — ver Top 5 #2.
- **Weekly Pit Stop não tem Task.** Um Task "ponte" na segunda de manhã poderia preparar o briefing (vencidos, próximos 7 dias, Signals pendentes) sem notificar; ela abre quando quiser.
- **Aniversários dos Amigos** não tem Task agendado próprio (só existem 3 Tasks na conta). Se o Bom Dia já cobre isso, ok; se não, é uma lacuna silenciosa da regra 11 do GM Charter.

## 🔌 Conectores — conectados e ainda sem uso no Odyssey

| Conector | Quem se beneficia | Uso concreto |
|---|---|---|
| **idealista** | Keymaster · 🔺 | Busca de contrato longo com os critérios já definidos |
| **Ticketmaster + Fever** | Bard · Catalan Corsair | Já estão anexados ao Task do Radar de Shows, mas o prompt não os usa — scan mais confiável que abrir link por link. (Ticketmaster falhou ao conectar hoje; conferir.) |
| **Spotify** | Bard | Soundtrack do Bom Dia pode virar playlist real salva, não só sugestão |
| **Booking / Expedia / Tripadvisor / Trivago** | Navigator | Viagem pra Andaluzia em outubro; Main Quest Finlândia |
| **Google Drive** | Art Direction · Chatty | Assets visuais da Crew já moram no Drive — ponte pra imagens do Chatty sem passar pelo Notion |
| **Glovo** | Supplies | Da lista de compras pro pedido (sempre com confirmação dela) |

Lacunas que continuam: WhatsApp (seguir via Claude in Chrome) e Flo (sem conector; data do ciclo segue manual na Player Sheet).

**Higiene de conectores nos Tasks:** os 3 Tasks têm ~10–20 conectores anexados cada, incluindo BigQuery, Wix, ClickUp e Economic Index, que não têm relação com o Odyssey. Pelo princípio de fronteira externa protegida, cada Task deveria ter só o que usa.

## 🚀 Otimização

- Bom Dia fixado em modelo antigo (Sonnet 4.6) enquanto os outros Tasks usam Sonnet 5 — decisão sua, dentro da revisão do Bom Dia.
- Bom Dia lê ~54k caracteres por run — separar template reduz custo e tempo.
- Pré-voo SQL do Bom Dia (Status=Ativo nos registros) é um bom padrão — vale replicar em qualquer Task novo.

---

## 🚫 O que NÃO fazer a partir desta auditoria
- Não criar banco novo, Persona nova nem Treasure novo.
- Não mexer no schema do Backlog antes da triagem e de uma decisão no Decision Log.
- Não deletar nenhum item do Backlog sem ela ver — arquivar/pausar primeiro.
- Não trocar modelo de Task sem pedido explícito dela.

## Sequência sugerida
1. Corrigir os dois 🔺 + confirmar horário do Bom Dia (5 min, sem risco).
2. Triagem do Backlog com ela + Boss "Temporada de Consultas".
3. Keymaster + idealista (busca sob demanda).
4. Sincronização Notion → Project Knowledge + decisão única sobre autoridade estrutural.
5. Views novas no Backlog (sem schema).
6. Resto entra na Capability Audit, que já é a próxima fase aprovada.
