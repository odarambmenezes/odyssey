---
name: inventario-bases-2026-11-11
description: Inventário de todas as databases do Odyssey com collection IDs verificados, o que cada skill puxa, e as duplicidades encontradas na Shopping List, no Backlog e entre Skills Mapping e Ações Rápidas
sources: [chat]
---

# Inventário de bases — 11/11/2026

Levantado a partir das skills: cada fonte que alguma skill lê ou escreve. **Os collection IDs abaixo foram verificados nesta sessão** e são o que as skills devem usar — busca por nome falha e já custou o prazo do Empadronamiento.

## Operacionais — dados vivos da Odara

| Base | collection:// | Nota |
|---|---|---|
| Odyssey — Backlog de Tarefas | `a4f2dc93-71ae-44c6-8049-b2cd8f752220` | 74 linhas. **Dentro de 🗂️ Archive / To be trashed** |
| Odyssey — Shopping List | `82b934c9-c166-4e0f-9f32-7da065f8efae` | 19 linhas, 18 Pendente |
| Odyssey — Diário Pessoal (Mood, Decisões & Highlights) | `73eca438-a657-4c46-bdb4-f51699213312` | Mora dentro da página de Lori, The Keeper |
| **Grab & Go** | `d9baf9a3-2d3f-41be-8fdd-152d8ee1fd91` | Backlog de **construção do projeto**, 8 sprints. Não estava em nenhum mapeamento de skills |
| Trip History | `403107b1-9b49-802d-9c7b-000b50fd1234` | Usada pelo Cap's Journey |

## Widgets do Bom Dia — as três estão no topo do workspace, fora de Project Odyssey

| Base | collection:// | Conteúdo |
|---|---|---|
| Registro de Cartas | `049c4322-6c07-4726-9af3-72844974938e` | Nome, Regra da Frente, Regra do Verso, Cor de fundo, Tema/Categoria, Status |
| Registro de Temas | `c793eef1-b59d-405c-b0c5-d6a5a69e040d` | 4 temas, todos Ativo |
| Registro de Ações Rápidas | `bd11c886-f95f-4d7e-bae8-d9914d57d9e5` | 5 ações: 3 Ativo, 2 Planejado |

Estar fora do Project Odyssey é a causa dos dezenas de "Registro de Cartas inacessível" no Registro de Runs.

## Estruturais — o projeto sobre si mesmo

| Base | collection:// |
|---|---|
| Skills Mapping | `3fe107b1-9b49-80fe-8401-000b3da753cf` |
| Crew Mapping | `3fe107b1-9b49-80b4-bab3-000b9c907c0f` |
| ⚓ Crew Noticeboard | `7cba836a-a6e5-48bf-b8fa-0468fee673d2` |
| Odyssey - Architecture Overview (os 5 pilares) | `3fe107b1-9b49-8063-81e6-000b78bf6c2f` |
| **Session Log - Odyssey** | `3fe107b1-9b49-80b1-b1bf-000b79ba6ea0` |

**Session Log** tem protocolo próprio que nenhuma skill menciona: "Log is the bridge between agents, not a Source of Truth. At the start, read the latest entry and verify the pages it affected. At the end, record what was done." Campos: Number, Name, Status, Last Edited By (ChatGPT / Claude / Odara), Start Date, End Date.

## Legado

- **Odyssey - AI Notice Board** (antigo) — página `3fe107b19b498099b4ebfd9470924462`, em To be trashed, com 3 entradas Unread.

## Fora do Odyssey, mas alimentam skills

- **Agências do Radar** `f623507b4fac43c4a8fd29cd51805924` e **Anúncios do Radar** `999eebfa7d0e4d008c24eb98bb24d0b1` — busca de apartamento, sob PERFIL DE INQUILINA.
- Google Calendar "Odara (Pessoal)" (`tacomigoencomendas@gmail.com`) e Fortis via busy/free.
- Gmail.

## O que NÃO é database, mas as skills tratam como se fosse

- **Memory Log** — é só uma *página de design*, movida para o fim da página de Lori. **Não existe lugar para guardar entrada.** O Codex chama de "o verdadeiro sistema de progressão, não XP", e as skills Side Quest, GM Check-in e Fechar item dizem "a foto vai pro Memory Log". Existe nota aberta no Noticeboard: "Decide where Memory Log entries are stored after its move".
- **Aniversários dos Amigos** `3af107b19b4981959168f487a7dca9ee` — a lista de 30 nomes é uma *tabela dentro de página*. Não dá para filtrar nem ordenar, e a filtragem pendente depende disso.
- **Registro de Runs · Bom Dia Claude** `3d2107b19b4981b9821fc82913095797` — ~40 entradas em formato inconsistente: algumas linhas de tabela markdown, outras tabelas soltas, outras sub-páginas.
- **Player / Character Sheet** `3aa107b19b4981b192b1fc071711e4b0` — página. Parada desde 15/08/2026 (é o bloqueio da Flo).

## Duplicidades e defeitos encontrados

### Shopping List

1. **Maiô** (Alta, "estrear a DiR Tuset") × **Maiô de natação (Primark Catalunya)** — mesma coisa, duas linhas.
2. **Água oxigenada** × **Água oxigenada (oxidante)** — mesma coisa.
3. **Pão francês** × **Pão francês (estilo brasileiro)** — alguém tentou resolver marcando uma como **Comprado** com nota "duplicado". Isso mente: diz que ela comprou.
4. **"Flocos de arroz (tipo crunch) — pra brigadeiro/doce de leite..."** — linha quebrada: Tipo, Status, Prioridade e Adicionado em todos vazios. **Não aparece em nenhuma recuperação**, porque o agrupamento é por Tipo e o filtro é Status = Pendente. O nome do item carrega a frase inteira com o motivo.
5. **"Lojas de móveis e decoração (referência)"** — não é compra, é um post de Instagram com lojas. Está como Produto Específico.
6. 4 linhas sem Prioridade, 3 sem Adicionado em.
7. ~7 itens de mercado de 02/08 que eram de um cardápio específico ("salmão em cubos para wrap de terça", "milho para o molho da carne moída") — 3 meses parados.

### Tasks e Obligations — duas bases de tarefa

- O **Backlog** é a vida dela; o **Grab & Go** é a construção do projeto, com sprints de 01 Doc Review a 08 Live Testing.
- As **10 linhas `[Cap]`** no Backlog são tarefa de construção: estão na base errada, pertencem ao Grab & Go.
- Duplicatas internas do Backlog: passaporte brasileiro (2 linhas, mesmo prazo 14/03/2027), coral/canto (2 linhas).

### Skills Mapping × Registro de Ações Rápidas — registro em dois lugares

| Ação Rápida | Status no Registro | Skill correspondente | Conflito |
|---|---|---|---|
| Gmail Sweep | Ativo | Gmail Sweep (Active) | A Ação diz "blocos de 2-4"; o Mission da skill diz "lotes de 5" |
| O que tá pendente? | Ativo | Cadence Queue (Active) | A Ação roda **as 3 fontes** (regra 11); a Cadence Queue lia só o Backlog — **corrigido em 11/11** |
| Calendar Check | Ativo | nenhuma | Capacidade ativa sem skill registrada |
| WhatsApp Check | Planejado | nenhuma | Depende do Claude in Chrome |
| Outlook Check | Planejado | nenhuma | Depende de conector Outlook |

E a Spec v6 do Bom Dia diz que Calendar Check e "O que tá pendente?" estão **pausados** — mas o Registro diz Ativo.

### Registro de Temas × decisão C1

Os 4 temas têm **Regra de Selecao = Aleatorio**, e o campo ainda oferece "Conectado a Mood" e "Conectado a Clima". A C1 (fechada em 27/09) diz que a escolha é **determinística pela data** e proíbe explicitamente aleatoriedade, mood e clima. O campo contradiz a regra. A skill Carta do Dia agora instrui a ignorar o campo.

### Personas

Grab & Go usa "**Lore**" e "**Mayor**" no campo IA responsável. O Crew Mapping tem **Lori**, e **não tem Mayor** — mas o `em-curso.md` dá função ao Mayor ("avisa quando uma conversa está começando algo novo com item aberto").

## Correções aplicadas em 11/11 nas skills

- Cadence Queue: passou a checar as 3 fontes da regra 11, não só o Backlog.
- Carta do Dia: collection IDs de Temas e Ações Rápidas (antes só page ID) + aviso sobre o conflito com a C1.
- Diário Pessoal: collection ID correto (antes só page ID) + o Tipo "Check-up" que faltava.
- Bom Dia Claude: bloco de IDs atualizado.
