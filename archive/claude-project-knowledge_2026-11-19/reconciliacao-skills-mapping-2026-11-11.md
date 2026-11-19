---
name: reconciliacao-skills-mapping-2026-11-11
description: Reconciliação do Skills Mapping em 11/11/2026 — schema novo (Workflow, Access, Trigger, Part of, Used by), 30 linhas, taxonomia de 3 tipos, as 4 skills de produção com IDs fixos e os pontos que ficaram para a Odara decidir
sources: [chat]
---

# Reconciliação do Skills Mapping — 11/11/2026

Database: https://app.notion.com/p/3fe107b19b4980d788f3dfea3689fbb5 (inline em 04 AI Crew & Skills)

## O problema que existia

O Skills Mapping tinha 15 linhas e o sistema real tinha 26 coisas. Rotinas inteiras, documentadas e em uso, não apareciam em nenhum mapeamento: Bom Dia, Weekly Pit Stop, GM Check-in, Meal Routine, Shopping List, Diário Pessoal, Recap Session, Cap's Journey, Birthday Alert, Manutenção Diária do Backlog, Deadline Alert. Várias linhas estavam com Mission vazia ou com uma letra só.

## Decisões estruturais

**Taxonomia reduzida a três tipos.** O tipo `Routine` foi removido (tinha 0 linhas e se sobrepunha a Workflow):

- **Skill** — um método, o átomo. Invocada sob demanda.
- **Workflow** — encadeia duas ou mais skills numa experiência só.
- **Scheduled Task** — o relógio que dispara algo sem ela.

**Skill não tem dono obrigatório** (decidido pela Odara em 11/11). Em vez de afunilar um owner, a regra inverteu: tudo é aberto por padrão e só se registra a restrição quando ela existe.

- `Access` (select): **Open** (qualquer agente, persona, tarefa de fundo, ou a Odara direto) · **Restricted** (só a persona em Used by, ou o GM) · **Sensitive** (mexe em dado protegido, G22: só leitura, nada sai do projeto sem aprovação dela).
- `Used by` (relation → Crew Mapping): vazio quer dizer aberta. Como a relation é de duas mãos, a página da persona ganha o backlink de graça.

**Campos novos:**

- `Trigger` — o que ela diz para acionar, ou o horário. Responde literalmente à pergunta que ela mesma tinha deixado no Gmail Sweep: "o que falar pra AI entender q é essa skill q quero usar?"
- `Part of` / `Steps` (self-relation) — é o que torna o Bom Dia construível como Workflow: as skills que ele chama aparecem em Steps.
- `Documentação` (URL) — **vazio significa que o conteúdo completo mora na própria linha**; preenchido aponta para a página real quando a documentação vive fora.

## A descoberta que mudou a prioridade: os IDs

O 📓 Registro de Runs (https://app.notion.com/p/3d2107b19b4981b9821fc82913095797) tem o histórico de ~40 runs reais do Bom Dia. Os mesmos erros repetem:

- **"Registro de Cartas inacessível"** / "data source not found" — dezenas de runs. Causa: as três databases de widget estão no **topo do workspace**, fora de Project Odyssey, e a run procurava por nome.
- **"Task Backlog collection não encontrada"** (3×), "Backlog indisponível" — mesma causa: o Backlog está em **🗂️ Archive / To be trashed / Codex**.
- Consequência real: nos dias antes de 22/10, **o Empadronamiento não apareceu como tarefa ativa**. O prazo passou.
- Também recorrente: Flo sem fonte desde 15/08 · Spotify não funciona em sessão agendada · notícias indisponíveis (R4) · Gmail intermitente e erro 400 · Artifact bloqueado em sessão agendada na nuvem · context compaction no meio da run.

Por isso as skills de produção abaixo trazem os **IDs verificados fixados na página**, em vez de deixar a run buscar por nome.

### IDs verificados em 11/11/2026

| Fonte | ID |
|---|---|
| Task Backlog | `collection://a4f2dc93-71ae-44c6-8049-b2cd8f752220` · pág. `c72071d037784ba5b6308c82a5a36d07` |
| Registro de Cartas | `collection://049c4322-6c07-4726-9af3-72844974938e` · pág. `d0b4bec77b2f4297b25d1f2aed300072` |
| Registro de Temas | `38ff8a5679304531af0ed5e4a0d4bd2c` |
| Registro de Ações Rápidas | `e07163015bd3472f943aa2ef3f0bc815` |
| Shopping List | `collection://82b934c9-c166-4e0f-9f32-7da065f8efae` · pág. `9adfc4b8cd10447d94cc7754a1c0231c` |
| Diário Pessoal | `8479aaff21b5456abc2deb61df7ce8fa` |
| Crew Mapping | `collection://3fe107b1-9b49-80b4-bab3-000b9c907c0f` |
| Skills Mapping | `collection://3fe107b1-9b49-80fe-8401-000b3da753cf` |

## As 4 skills novas de produção (escritas em 11/11, primeiro teste em 12/11)

Cada uma é runbook executável, não ponteiro. Todas Active, Access Open.

1. **Cadence Queue (o que está pendente)** — o motor. Lê o Backlog pelo ID, aplica o auto-revival **na leitura**, ordena por consequência (🔺 → Rígido vencido → Rígido chegando → Flexível fora da janela), e ajusta o tom pela Rigidez: Rígido é parede, Flexível é centro de janela e nunca recebe a palavra "atrasado".
2. **Fechar item do Backlog (Completion Protocol)** — os três passos sempre juntos, com a tabela de recorrência → próximo prazo, calculado a partir de hoje e não do prazo velho. É a correção do bug que travou 17 recorrentes desde setembro.
3. **Triage (capturar tarefa nova)** — o portão de entrada. Nunca cria Obligation sem Recorrência; se for única, é Pontual, nunca vazio. Roteia compra para a Shopping List e percepção para o Diário. Busca duplicata antes de criar.
4. **Carta do Dia (tema + arcano + biscoito)** — a assinatura do Bom Dia, com a regra C1 determinística e os IDs dos três Registros. Plano B explícito em vez de carta inventada.

**Preenchidas com runbook executável:** Side Quest Generator (engine completo, incluindo gravar o holofote depois do sim dela — passo que nunca rodou) e Gmail Sweep (lotes de 5, prioridade para 🔺/moradia/banco/saúde, rascunho no tom dela, nunca envia).

**Bom Dia Claude** passou a Active em duas trilhas: a **versão conversa** tem runbook pronto na página, com IDs fixos e as skills em Steps; a **casca visual v6** segue parada e continua na lista Em curso.

## Estado final: 30 linhas

| Tipo | Active | On Draft | Paused | Archived |
|---|---|---|---|---|
| Skill | 9 | 8 | 0 | 1 (template) |
| Workflow | 2 | 4 | 0 | 0 |
| Scheduled Task | 0 | 1 | 2 | 3 |

Nenhuma linha com Mission, Use Cases, Trigger, Access, Type, Status ou Recurrency vazios.

**Steps do Bom Dia:** Carta do Dia · Birthday Alert · Cadence Queue · Side Quest Generator · Gmail Sweep · Diário Pessoal · Fechar item · Card Pull of the Day.

**Views:** 📋 Tudo · 🟢 Em uso · 🛠 Para construir · 📅 Roda sozinho · 🔒 Acesso · 🌅 Dentro do Bom Dia · 📦 Arquivo.

## Arquivados nesta sessão

- **Good Time Radar** — Mission era "R", página vazia, zero menção em todo o workspace. Ideia registrada e nunca construída. Pela regra do Em curso, matar vale como terminar.
- **Perfil de Voz da Odara (Mensagens)** — conteúdo consolidado na skill Odara's Voice. A página virou ponteiro.
- **Diário Pessoal (Log Ad Hoc)** — duplicata literal de "Diário Pessoal (Registro Ad Hoc)", criadas com minutos de diferença em 03/08/2026.

## Achados que viraram pendência real

1. **A database do Backlog está dentro de 🗂️ Archive / To be trashed.** É a causa raiz dos erros de leitura nas runs. Mover é mudança estrutural (G21), então é decisão da Odara.
2. **Manutenção Diária do Backlog desligada desde 02/10.** Religar é seguro: hoje viraria só 4 linhas domésticas (ver `claude/auditoria-task-backlog-2026-11-11.md`).
3. **Gmail Sweep estava Paused** apesar de a página registrar teste OK em 28/07 e a v6 manter essa ação. Mudado para Active, a confirmar.
4. **Card Pull of the Day** é o braço agendado do Bom Dia, não uma skill separada. Seu destino está amarrado à decisão da v6.
5. **Meal Routine diz rodar "domingo, dentro do Weekly Pit Stop"**, mas o Pit Stop é segunda-feira pelo Playbook.
6. **Lore x Lori.** O Crew Mapping diz "Lori, The Keeper"; a skill de limpeza do noticeboard dizia "Lore". Nome alinhado ao Crew Mapping.
7. **The Quill / Message Writer** não é skill separada: é nome antigo da Odara's Voice. Registrado como alias.
8. **Mission e Use Cases ainda misturam português e inglês** entre linhas. Só Recurrency foi normalizado.
9. **O holofote das Main Quests nunca rodou** — as 8 linhas têm "Última Side Quest Recebida" vazia. O Side Quest Generator agora grava esse campo quando entrega uma quest ancorada.

## O que NÃO entrou no Skills Mapping, de propósito

Páginas que estão sob "Skills, Workflows and Automations" mas são Source of Truth e não skills: Corpo & Vitalidade, Barcelona & Catalonia Discovery, Regras do Odyssey Travel Calendar, Referências Visuais (Chatty). Deveriam viver com suas personas, não no mapeamento de skills.
