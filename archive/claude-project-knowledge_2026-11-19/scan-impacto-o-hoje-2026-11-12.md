---
name: scan-impacto-o-hoje-2026-11-12
description: Scan do projeto em 12/11/2026 — os 8 pontos da documentação que o novo pilar 06 O Hoje muda, mais 8 inconsistências achadas no caminho (G10 apontando para página arquivada, Decision Log inexistente, GitHub em débito, Ship's Logs)
sources: [chat]
---

# Scan de impacto — o pilar 06 O Hoje

**Data:** 2026-11-12
**Gatilho:** criação de `06 O Hoje` (https://app.notion.com/p/416107b19b4981f4beeeecc87e51b8bd), sexto pilar, com a narrativa delegada ao Chatty.
**Nada foi alterado neste scan.** Mexer no Manual e na estrutura de pilares é decisão da Odara (G21).

Lido: Project Odyssey (main page), Odyssey Operating Manual, 02 O Navio, 05 A Jornada, Ship's Logs, Architecture Overview (schema e linhas), Crew Mapping, Codex e Governance do Project Knowledge.

**Limitação:** a cota de consultas SQL do Notion estourou no meio do scan. O **Source of Truth Mapping** não foi lido linha por linha — fica pendente para confirmar se o Backlog e a Shopping List estão classificados lá (eu suspeito que sim, por erro meu em 11/11).

---

## Parte 1 — O que o O Hoje muda na documentação

Oito pontos, em ordem de impacto.

### 1. 🔴 Odyssey Operating Manual — a tabela de pilares

`https://app.notion.com/p/3aa107b19b4981079aaecf1f72b1bb98`

A tabela "Pillar / What lives there" tem cinco linhas. **É o primeiro documento que todo agente lê**, e é literalmente o mapa que manda um chat novo para o lugar certo. Enquanto ele diz cinco, O Hoje não existe para nenhum agente.

Linha a adicionar: *06 O Hoje — Where things stand right now: what is open, and the live bases the system reads and writes.*

Mudar o Manual é decisão da Odara pela própria tabela do G21 ("Change this Manual, the pillar structure or a persona main page → Odara decides. Builders execute").

### 2. 🔴 Main page — "5 interconnected pillars"

`https://app.notion.com/p/3aa107b19b49808bbf8cd2719803ed0d`

Texto atual: *"Odyssey is organized into 5 interconnected pillars. Together, they define how the world is built, experienced, brought to life, operated, and continuously improved."*

Dois ajustes: o número, e a lista de verbos — hoje ela cobre construir, experienciar, dar vida, operar e melhorar. Falta **onde a coisa está agora**, que é exatamente o buraco que motivou o pilar.

### 3. 🔴 Main page — "The Captain's Deck" é um O Hoje concorrente

Esta é a mais séria, porque não é um número desatualizado: é **dois donos para o mesmo assunto.**

A seção Captain's Deck se descreve como *"Odyssey's future interactive home base"* e promete mostrar *"who's aboard, what matters now, what needs attention and which tools can actually help"*. A tabela "What belongs on deck" lista Quick Navigation, Crew at a Glance, Ship's Progress, Radars & Scheduled Tasks, Quick Actions.

Isso **é** a descrição de trabalho do O Hoje. E a regra de design da própria seção diz "No duplicated records, competing dashboards or extra maintenance for the Captain" — ou seja, ela proíbe o que vai acontecer se as duas coexistirem como especificação.

A leitura que resolve, e que já foi dita na conversa de 12/11: **o Captain's Deck / Command Center é a janela do O Hoje**, não um pilar paralelo. Então a seção na main page vira ponteiro para o pilar, e a especificação de módulos passa a viver em um lugar só.

Decisão necessária da Odara. Até ela existir, o Chatty pode escrever o O Hoje sem saber que há uma segunda especificação do mesmo escopo a dois cliques de distância.

### 4. 🟡 05 A Jornada — a regra "Give it one home" não tem cláusula para dado vivo

Texto atual: *"active domain knowledge belongs to its Source of Truth; project-wide rules to the Odyssey Operating Manual or responsible pillar; session history to Session Log; displaced unresolved material to Reconciliation needed."*

Quatro destinos, e **nenhum é dado operacional vivo**. É a formulação exata do buraco: foi por isso que o Backlog acabou em `To be trashed` e as três bases do Bom Dia acabaram fora do projeto — não havia cláusula que as reclamasse.

Cláusula a adicionar: *live operational state to 06 O Hoje*.

### 5. 🟡 05 A Jornada — "Pillar connections" e a fronteira

O callout final lista os cinco pilares e o que cada um faz. Precisa do sexto. E vale escrever a fronteira **do lado da Jornada** também, não só do lado do Hoje: *o que fecha sai do Hoje e vira história aqui*. Fronteira escrita em um lado só é fronteira que apodrece.

### 6. 🟡 02 O Navio — a tabela "One concept, one home"

Sete linhas (propósito, regras universais, preferências da jogadora, arquitetura, visual, personas, história). Nenhuma para estado operacional.

Linha a adicionar: *Live state, obligations, shopping, birthdays → 06 O Hoje*.

### 7. 🟡 02 O Navio — o Backlog continua fisicamente lá

O database `Odyssey — Backlog de Tarefas` é o **último bloco** da página, depois de dez seções de arquitetura. Foi para lá em 11/11, quando saiu do `To be trashed`. Era o melhor parente válido na hora; não é o lugar certo.

Destino: O Hoje. É o primeiro movimento concreto depois de a página ter cara.

### 8. 🟢 O idioma do O Hoje já está decidido — e eu deixei em aberto por engano

O Manual diz, na seção Language and units: **"Project documentation is always written in English."**

Eu listei o idioma como pergunta aberta no briefing do Chatty. Não é: a página final vai em inglês. O briefing precisa dessa correção, senão o Chatty herda uma dúvida que a regra já resolveu.

---

## Parte 2 — Inconsistências achadas no caminho

Nenhuma delas tem a ver com o O Hoje. Apareceram porque o scan passou por cima.

### 9. 🔴 O G10 aponta para uma página arquivada — e o erro é meu

O G10 é guardrail não-negociável: toda mensagem escrita em nome dela segue o Perfil de Voz, automaticamente. O link no Manual é **`[ARQUIVADO] Perfil de Voz da Odara (Mensagens)`**.

Eu arquivei essa página em 11/11, depois de consolidar o conteúdo na skill Odara's Voice. Arquivei o destino e não consertei a regra que aponta para ele. Um guardrail que aponta para um arquivo é um guardrail que vai ser ignorado.

Conserto: o G10 passa a apontar para a skill Odara's Voice no Skills Mapping, ou para a Source of Truth nova, se a Odara decidir separar a base (pendência de 11/11). **Esse é o primeiro a arrumar**, e é dívida minha.

### 10. 🔴 O Decision Log não existe, mas duas regras dependem dele

- Governance, Change Protocol passo 3: *"Log the decision + reasoning in the Decision Log."*
- G20: *"The why and when of a change lives outside the live pages, in the Decision Log."*
- 05 A Jornada: *"a single canonical Decision Log was not verified during this audit. Do not claim it exists or create a competing database prematurely."*

Ou seja: o protocolo manda registrar em um lugar que a documentação diz que não foi confirmado existir. Isso morde **agora** — a decisão do O Hoje é estrutural e não tem para onde ir. Hoje ela existe só no corpo da página nova e no Session Log #2.

Não é para criar uma database por impulso. É para a Odara decidir: o Session Log cobre esse papel, ou o Decision Log precisa nascer de verdade?

### 11. 🟡 O GitHub está em débito e ninguém falou disso

Change Protocol passo 6: *"If the change is structural/durable, also regenerate the matching GitHub file(s) before considering the session's work done."*

Tivemos duas sessões estruturais seguidas — 11/11 (Skills Mapping, Backlog, 30 linhas, 10 páginas) e 12/11 (pilar novo) — e o repo `odarambmenezes/odyssey` não foi tocado em nenhuma. O conteúdo e a última atualização do repo seguem **não verificados** (o próprio 02 O Navio diz isso).

Duas saídas honestas: ou o passo 6 volta a ser cumprido, ou ele sai do protocolo e o GitHub é rebaixado a backup ocasional explícito. O que não serve é um protocolo que a gente descumpre sem notar.

### 12. 🟡 A database dos pilares tem duas linhas que não são pilares

`Odyssey - Architecture Overview` tem 8 linhas: os seis pilares mais **Ship's Logs** e **Reconciliation needed**, ambas com `Pillar` vazio.

Essa database é renderizada inline na main page, embaixo do título "Our Pillars". Então a lista de pilares da página principal mostra duas coisas que não são pilares.

Conserto possível sem mover nada: uma view filtrada por `Pillar` não vazio na main page. As duas linhas continuam onde estão e param de poluir.

### 13. 🟡 Ship's Logs é um O Hoje embrionário — e tem um problema de governança

`https://app.notion.com/p/413107b19b49802f9ab5f5bc593ea75c`

Purpose: *"A live view of what's left to build in Odyssey. It keeps the next tasks visible and lets the AI Crew move the next phases forward without waiting on Odara's approval."* É a casa do **Grab & Go**.

Duas coisas:

- **Isso responde à pergunta aberta sobre o Grab & Go.** A página já existe e já é "uma visão viva do que falta". Ou Ship's Logs passa a ser filha do O Hoje, ou o O Hoje a absorve. Mas isso é a construção do projeto, não a vida dela — vale decidir se o Hoje tem as duas faces (minha vida agora / o navio agora) ou só a primeira.
- **"without waiting on Odara's approval" contradiz o G21 e o G15.** Mudança estrutural é decisão dela; essa frase é uma pré-aprovação em branco escrita numa página de pilar. Ou a Odara confirma que quis dar essa autonomia para o Grab & Go especificamente, ou a frase sai.

### 14. 🟡 A tabela interna do "Pagar contas mensais" não é resetada desde 02/10

Governance, Known Technical Limitations: *"Maintenance Scheduled Task — a separate, lightweight daily task (before Bom Dia Claude) applies the auto-revival rule and **resets the monthly 'Pagar contas mensais' table**."*

Isso é a tabela dentro da página do Pagar contas, que a Descrição manda checar e que eu nunca abri. Dois efeitos:

- Minha suposição de 11/11 (manter a âncora no dia 1 em vez de contar de hoje) tem base documentada. Boa notícia.
- A Manutenção Diária está **desligada desde 02/10**, então essa tabela não é resetada há mais de um mês. Quando a skill voltar, isso faz parte do trabalho dela — e não está escrito na página da skill.

### 15. 🟢 Codex × schema do Backlog — agora com a fonte exata

O Codex lista 11 categorias e escreve **Finance**. O schema tem 13 e escreve **Financeiro**, e inclui **Main Quest** e **Side Quest**, que são tipo de item e já vivem no campo `Tipo`. O Codex também diz que uma task "can belong to more than one" categoria, e o campo é seleção única.

Já estava mapeado na auditoria de 11/11; o scan só confirma qual lado está certo: o Codex é a referência de *o que as coisas são*, então é o schema que está fora da regra, não o contrário.

### 16. 🟢 A regra do em-curso — aviso, não bronca

`claude/em-curso.md` registra o acordo de 13/10: **nada novo começa enquanto tem coisa parada em 90%**, e matar vale como terminar. O Mayor avisa; ela não precisa lembrar. Hoje há quatro itens abertos, e a gente começou um pilar novo.

Mas tem uma convergência que vale notar em vez de só apitar: o item que está **em execução** é "O cais — MVP v1", que é o Command Center — que acabou de ser definido como a janela do O Hoje. Construir a janela fecha dois dos quatro itens abertos (as ilhas ligadas nas Sources of Truth e o "30 amanheceres" hardcoded).

Então o O Hoje não é mais uma frente paralela: é o enquadramento que faltava para o item que já estava em curso.

---

## Parte 3 — Ordem recomendada

**Antes de qualquer coisa, dívida minha:** consertar o G10 (item 9). Guardrail apontando para arquivo, criado por mim ontem.

**Antes do Chatty entregar:** corrigir o idioma no briefing (item 8) e decidir o Captain's Deck (item 3). O segundo é o único que pode fazer o trabalho dele nascer errado.

**Depois que a página tiver cara:** Manual, main page, Jornada e Navio (itens 1, 2, 4, 5, 6) numa passada só, porque é o mesmo fato propagado — e aí sim mover o Backlog (item 7).

**Decisões dela, sem pressa:** Decision Log (10), GitHub (11), Ship's Logs e Grab & Go (13).

**Pequenos, fazer quando passar por perto:** a view filtrada dos pilares (12), a nota do reset na skill de Manutenção (14), o schema do Backlog (15).
