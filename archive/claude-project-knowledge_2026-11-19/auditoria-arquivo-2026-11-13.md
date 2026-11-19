---
name: auditoria-arquivo-2026-11-13
description: Auditoria de 13/11/2026 das páginas candidatas a arquivo/deleção, o mapa de quebras se a remoção fosse hoje, e a proposta de pente fino — inclui o achado do Game Design com 8 regras vivas dentro do lixo
sources: [chat]
---

# Auditoria de arquivo e mapa de quebras — 13/11/2026

**Pedido da Odara:** achar todas as páginas candidatas a arquivo ou deleção, marcá-las com `[ARCHIVE]` no título, e depois reler o projeto para identificar o que quebraria se a remoção acontecesse hoje.

**Estado da execução:** o Notion passou a devolver 503 em toda escrita no meio das renomeações. **Duas entraram** (`[ARCHIVE] Governance & Guardrails` e `[ARCHIVE] Codex (página legada do Notion)`); **treze falharam** e precisam ser refeitas. Uma chamada única também falhou, então é o serviço, não excesso de paralelismo.

---

## 🔴 O achado que muda o trabalho

### `Game Design` tem oito regras vivas e está dentro do `To be trashed`

Caminho real: `Project Odyssey / Architecture Overview / 05 A Jornada / To be trashed / Game Design`

Conteúdo: **G2, G3, G4, G11, G12, G13, G14, G17**, mais o Quest Engine completo, o glossário do projeto (Obligation, Quest, Boss, Wildcard, Cadence Queue, Rigidez, Pontual, Mood, Memory Log, Diário Pessoal) e os Game Paths.

Entre elas:

- **G11** — *"'o que tá pendente' sempre significa três fontes, checadas juntas"*. É a regra que eu citei a sessão inteira de 11/11 como "regra 11 do GM Charter" e que me fez corrigir a skill O que tá pendente.
- **G13** — nunca virar app de produtividade.
- **G12** — registrar no Diário proativamente, sem pedir permissão.
- **G17** — Modo Survival × Modo Fluxo, com o gatilho de saúde/segurança/integridade.
- **G14** — consciência contextual do Backlog em qualquer chat.

**O ciclo:** o `Game Design` diz que as regras de rotina moram na página do Bom Dia; a página do Bom Dia dizia que as regras do Crew moram no `Game Design`. As duas estão no lixo, as duas se citam, e as duas têm regra viva dentro.

**Como aconteceu:** o ledger do `Reconciliation needed` registra, em 09/11, que *"Crew-wide rules went to the new Game Design page in 01 A Bússola"*. A página foi criada mas nunca chegou na Bússola — ficou no `To be trashed`.

**Consequência:** essa página **não leva `[ARCHIVE]`**. Ela precisa ser resgatada para `01 A Bússola`, como o Backlog foi resgatado em 11/11.

**Bônus:** o próprio `Game Design` carrega um aviso dizendo *"G11 e G14, o Quest Engine e o Obligation Path ainda citam o antigo Task Backlog e seus campos. Essa database está arquivada"* — o que é **falso desde 11/11**, quando o Backlog saiu do lixo para o 02 O Navio.

---

## Inventário: as candidatas

### Dentro de `To be trashed` — decisão da Odara já registrada em 09/11

| Página | Marcada | Por quê |
|---|---|---|
| Governance & Guardrails | ✅ | Nome de autoridade, substituída pelo Manual |
| Codex (página legada) | ✅ | Mesmo nome do doc vivo no Project Knowledge |
| G8 · Priority override: legal status in Spain | ❌ 503 | **Diz que a regra do 🔺 está arquivada; a regra 8 está em vigor** |
| 00 - AI Usage, Instructions & Automations | ❌ 503 | Página 00 legada |
| Odyssey Operating Model — Leadership, Crew & Communication | ❌ 503 | Modelo operacional legado |
| Odyssey Organizational & Communication Structure — Experimental | ❌ 503 | Estrutura experimental |
| AI Crew — Architecture & Persona Mapping | ❌ 503 | Referência histórica de arquitetura |
| Resources / Knowledge base | ❌ 503 | Página-doca vazia; 6 itens vivos já migraram para as Personas |
| Moved out of the Operating Manual and the Bússola | ❌ 503 | Regras já redistribuídas |
| Theme: Pirate Ship Mistiquinho | ❌ 503 | Rascunho vazio |
| Archive: C-Staff and platform-independent command | ❌ 503 | Hierarquia antiga; a viva é a Crew Tree |
| Archive: Treasure Chest six-item MVP and Supplies spec | ❌ 503 | Conceito Treasure aposentado |
| Bom Dia Claude (Rotina Matinal Completa) | ❌ 503 | Arquivada em 12/11, já destilada |
| Bom Dia Claude — Experience Spec v0.1 | ❌ 503 | Contrato da versão substituída. **Nunca foi lido** |
| Odyssey - AI Notice Board (database) | — | Entradas migradas para o Crew Noticeboard |

Mais **~10 blocos de conteúdo** dentro da própria página `To be trashed` (Gamification Mechanics v1, Progression, Active Main Quests, Boss Path, Project Arcs, Check-in Types ×2, 02 O Navio V1, dois blocos vindos do 04 AI Crew). São conteúdo, não páginas: não dá para marcar, vão junto com a página.

### Fora do `To be trashed` — candidatas que ninguém tinha listado

| Página | Por quê |
|---|---|
| `Reconciliation needed` | **Está concluída.** 15 das 16 linhas dizem "Archived/Moved/Done 09 Nov (Odara's decision)". É um ledger terminado posando de área de espera, e ocupa linha no banco dos pilares com `Select = To Reconcile` |
| `AI Chats / Efforts Mapping (1)` (database) | Roster legado, com aviso "do not use as the current primary roster". Substituído por Crew Mapping + Skills Mapping. Vive inline dentro do Reconciliation needed |
| `⚓ Crew Noticeboard & 🌙 Night Shift — Pilot` | Piloto encerrado em 06/11. A tarefa agendada foi apagada em 13/11 |
| `📥 Entrada da Noite` | Input do piloto do Night Shift |
| `🌙 Night Shift Log` | Observabilidade do piloto |
| `[ARQUIVADO] Perfil de Voz da Odara (Mensagens)` | Já consolidada na skill Odara's Voice. Prefixo antigo, unificar para `[ARCHIVE]` |
| `[ARQUIVADO - duplicata] Diário Pessoal (Log Ad Hoc)` | Duplicata literal de 03/08 |
| `🎨 Referências Visuais — Bom Dia Claude (Chatty)` | A própria Paisagem diz "não aplicar como canon global" |
| `🧭 Odyssey Capability Model — Skills · Treasures · Workflows · Tasks` | Usa a taxonomia antiga com Treasure; substituída pelos 3 tipos do Skills Mapping |

### Nem viva nem arquivo: reconciliar

**`🏢 Odyssey Organization & Capability Ownership`** (em 02 O Navio) — **não marcar.** Metade é vivo e bom:

- o **teste da linha** em 5 pontos (operacional × estrutural), que é um critério útil e não existe em outro lugar
- a tabela de escalação (quando sobe para a Odara × para os Builders)
- o **orçamento de interrupção** — "o canal padrão para chegar na Odara é o Bom Dia"
- a nota canônica de que "The Quartermaster" era nome provisório da futura Persona de Finance e hoje é do Gibbs

E metade é velho: cita o piloto do Night Shift como ativo, trata o `AI Chats / Efforts Mapping` como o registro de capacidades, tem Fase D marcada para "fim de outubro", usa "Lore" e "Poção", e descreve Monthly Area Reports e Captain's Council que nunca aconteceram. Tem uma filha, `⏳ Schedule Task Governance v1`, no mesmo estado misto.

---

## Mapa de quebras: o que rompe se a remoção fosse hoje

### 🔴 Quebra catastrófica

**1. As oito regras do `Game Design` desaparecem.** Nada mais no projeto as guarda. O Playbook do Project Knowledge tem um resumo do Quest Engine, mas **não tem G11, G12, G13, G14 nem G17**. Não é quebra para consertar: é página para resgatar.

**2. O G21 do Manual aponta para o nada.** *"Delete anything → Never. Move it to the archive in 05 A Jornada."* Se o arquivo sai do projeto, o guardrail de topo manda guardar num lugar que não existe. (Já decidido hoje que essa regra muda.)

### 🟡 Páginas vivas que passam a exibir links mortos

**3. `03 A Paisagem` — quatro referências no mesmo toggle.** O bloco "Referências do Bom Dia Claude" cita a página do Bom Dia, o Experience Spec e as Referências Visuais do Chatty — as três são candidatas. E diz que o `Theme: Pirate Ship Mistiquinho` está "mantida em Reconciliation needed", quando está no `To be trashed`.

**4. `02 O Navio` — "Legacy sources still worth checking"** aponta para o Codex legado e para uma segunda página que **já retorna 404** (o Playbook do Notion, deletado). Um link morto e um por morrer, numa página marcada como Reconciliada.

**5. `05 A Jornada` — o callout 📦 está errado em dois pontos.** Diz que o AI Notice Board, o Memory Log e o Governance & Guardrails estão em `Reconciliation needed` — estão no `To be trashed`, e o Memory Log foi para o fim da página da Lori em 09/11.

**6. `04 AI Crew & Skills`** descreve corretamente que Codex, Operating Model, Org & Comm e Architecture & Persona Mapping foram arquivados. Texto histórico, sobrevive — mas vai passar a ler "[ARCHIVE]" no meio da frase, o que é exatamente o efeito desejado da marcação.

**7. `Reconciliation needed` vira uma lista de links mortos.** Dezesseis menções, quase todas para candidatas. Mas ela própria é candidata, então isso se resolve removendo-a junto.

### 🟢 Fora do Notion, e por isso o mais difícil

**8. O prompt da tarefa `Card Pull of the Day`** (desligada) manda *"ler a página da rotina"* com a URL da página arquivada do Bom Dia. Está dentro do trigger, não no Notion.

**9. As instruções do projeto** continuam apontando para a página antiga do Bom Dia. **Só a Odara alcança esse campo** — é a assimetria que ela nomeou, e a razão da regra de desenho abaixo.

---

## Proposta de pente fino

### Antes de qualquer remoção

1. **Resgatar o `Game Design` para `01 A Bússola`** e corrigir o aviso interno que diz que o Backlog está arquivado. Sem isso, a remoção apaga oito regras em vigor.
2. **Reescrever o G21** no Manual pelo protocolo de três passos (destilar → cortar links de entrada → Odara decide guardar fora ou deletar).
3. **Decidir o destino do "teste da linha"** e da tabela de escalação, hoje presos na página mista de Organization & Capability Ownership. Candidato natural: o Manual.

### Consertos de referência, um por página

4. **`03 A Paisagem`** — o toggle de referências do Bom Dia passa a apontar para a caixa nova do workflow e para o destilado, e a linha do Mistiquinho é corrigida ou removida.
5. **`02 O Navio`** — tirar o link morto do Playbook e o ponteiro para o Codex legado.
6. **`05 A Jornada`** — corrigir o callout: o que está onde, e que o Memory Log está com a Lori.
7. **Aposentar o `Reconciliation needed`** depois de mover as 4 perguntas abertas do Manual que ainda vivem nele (organização da documentação, onde mora o Decision Log, se o GitHub é o terceiro nível do G16, e o destino das regras movidas).

### Regra de desenho que nasce disso

**As instruções do projeto só devem fixar pontos de entrada que nunca serão aposentados** — o Manual e os pilares. Todo o resto se alcança navegando. Cada link extra ali é uma página que não pode ser aposentada sem a Odara entrar nas configurações.

### Estado final desejado do banco dos pilares

Hoje tem **8 linhas**: os seis pilares mais `Ship's Logs` e `Reconciliation needed`, nenhuma das duas com valor em `Pillar` — e o banco é renderizado inline na main page sob o título "Our Pillars". Deveria ter **6**.

---

## O que esta auditoria NÃO cobriu

Para não dar a impressão de completude que não existe. Não abri, e podem conter mais candidatas:

- As **11 páginas de Persona** (Lori, Cap, Jaume, Calê, Lola, Bardim, Yaikes, Clau, Marty, Beastmaster, Gibbs)
- **Grab & Go** (8 sprints de construção) e **🌊 Future Horizons**
- **`⏳ Schedule Task Governance v1`**, **`🧭 Odyssey Capability Model`**, **`Memory Log`**
- Os scripts legados sob `Skills, Workflows and Automations`: **`Morning Message Sweep (v1)`**, **`GM Check-in Script (v1)`**, **`Weekly Pit Stop Script (v1)`** — os três provavelmente substituídos por linhas do Skills Mapping, mas não verifiquei
- **`Side Quest On-Demand`**, **`Corpo & Vitalidade`**, **`Barcelona & Catalonia Discovery`**, **`Regras do Odyssey Travel Calendar`**, **`Shopping List Workflow`**, **`Meal Routine`**, **`Diário Pessoal (Registro Ad Hoc)`**

É um segundo passe, e é o lugar natural para o Chatty entrar como segundo par de olhos.
