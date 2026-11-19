---
name: bom-dia-versions
description: URLs dos Artifacts do Bom Dia Claude — live (iterável) e snapshots congelados para rollback + decisões de design
sources: [cowork]
---

## Versão Live (evolui com cada sessão)

**URL:** https://claude.ai/code/artifact/5c3800d9-4362-428d-989f-7d97f32808c5

Republique sempre nesse URL. É o que a Odara abre no dia a dia.

⚠️ **Status em 28/09/2026:** implementação v6 iniciada (Fase 1). Antes de qualquer alteração, snapshot v5 Golden Run foi congelado (ver seção Snapshots abaixo). v6 segue o **Bom Dia Claude — Experience Spec v0.1** (autoridade funcional) e o **Implementation Brief / Claude Handoff** (instrução de execução) — em caso de conflito entre os dois, o Spec prevalece.

⚠️ **A casca v6 (Fase 1) NÃO foi publicada neste URL.** Ela está num artefato de revisão separado (ver seção "v6 — Casca / Fase 1" abaixo), aguardando aprovação da Odara. O live continua sendo a v5.

---

## Filosofia de Geração — Decisões Chave

### Carta do Splash — O Biscoito da Sorte

A carta grande que aparece no splash (e fica repousada no topo depois do flip) tem **dois campos gerados frescos a cada dia**:

- **O arcano em si** (número, símbolo, nome) → sorteado com base na data, quests ativas, e contexto geral
- **A frase/quote** → NÃO é o significado canônico do arcano. É o **biscoito da sorte do dia** — gerado com base em:
  - O que está acontecendo nas Main Quests ativas (especialmente as de alta prioridade)
  - Horóscopo ou ciclo lunar do dia (quando relevante)
  - Notícias / eventos que afetam a Odara diretamente
  - Fase do ciclo menstrual (Flo)
  - Energia geral do dia (dia da semana, temperatura, etc.)

A frase muda todo dia, mesmo que o arcano sorteado seja o mesmo. Ela é poética, curta, pessoal — não uma definição de tarô.

### Mini Cards no Grid (4 cards, não 5)

Após decisão em 05/09/2026, a mini card de "Arcano · Hoje" foi **removida** porque duplicava a carta do splash sem distinção clara. Os 4 mini cards ativos são:

1. Side Quest (sorteada do Registro de Cartas)
2. Soundtrack (baseada no mood + energia do dia)
3. Flo (fase do ciclo — contador só nos 5 dias pré-período)
4. Palavra do Dia (espanhol coloquial, com pronúncia e exemplo)

**v6:** este contrato de 4 mini cards se mantém. Mudança v6: campo Flo mostra "dado indisponível" se a fonte estiver stale — nunca inventa fase do ciclo sem dado confiável (Player Sheet última atualização 15/08/2026, fonte canônica ainda não identificada).

### Tabs de Tasks (v5 → v6)

- **v5:** Tasks em 3 abas: **Hoje / Semana / Mês** — classes `.t-tab` / `.t-panel`, IDs `tpanel-hoje`, `tpanel-semana`, `tpanel-mes`
- **v6 (Spec v0.1):** Hoje + Semana **juntos** numa lista única; Overdue tratado **separadamente** (não é mais uma aba "Mês"). Ver Experience Spec para o contrato exato.
- Cada task de Hoje pode ter `.task-links` com chips `.task-lnk` apontando para links diretos (LinkedIn, Treatwell, Google Maps, etc.)

### 3 Blocos de Journal (v5) → Notícias 5 abas (v6)

- **v5:** A Gazeta (Mundo/BCN/Brasil) + Eventos (Barcelona/Games/Europa) + O Correio (Gmail)
- **v6 (Spec v0.1):** bloco único de Notícias com 5 abas: **Mundo / Espanha / Barcelona / Brasil / Coisas Boas**. "Eventos" e "O Correio" como blocos próprios saem do escopo de Notícias (Gmail Sweep passa a ser Treasure em Quick Actions, não bloco de journal).

### Tabs de Journal — escopadas por bloco

Cada `.journal` trata seus próprios `.j-tab` / `.j-panel` via event delegation (não querySelectorAll global). Painéis identificados por `data-panel` + `id="panel-{nome}"`.

### Carta do Splash — Estrutura v5

- Retrato fixo 230×330px (sem flip de tamanho — só rotate)
- `.c-date` e `.c-theme` dentro do `.face.front` E dentro do `#restSlot`
- Gradiente roxo (#8C2F6A → #4A1545 → #241033)

### Template de Referência no Notion

Atualizado em 2026-09-05 (v4 → v5). A página do Notion tem a descrição estrutural das mudanças. O **artefato de referência vivo** (sempre o mais atual) é o URL live acima.

---

## v6 — Novidades da Spec v0.1 (implementação iniciada 28/09/2026)

Resumo das mudanças estruturais aprovadas por Odara (decisões completas no Implementation Brief / Notion):

- **Night Shift Report**: bloco novo, sempre visível (mesmo vazio → estado calmo, não desaparece)
- **⚓ À Sua Espera**: bloco novo, some quando não há nada pendente
- **XP removido do Side Quest**: nenhuma menção de XP nas mini cards (reforça C2 — ver Decisões Fechadas)
- **Quick Actions**: "Calendar Check" e "O que tá pendente?" pausados; mantém Gmail Sweep
- **Resiliência**: todo bloco segue Normal → Retry → Plan B → Erro visível — nunca desaparece silenciosamente
- **Regenerate**: capability `sample` ao vivo + Plan B pré-gerado como fallback
- **Fonte única**: versão manual e agendada do Bom Dia devem ler a mesma fonte para o bloco de Night Shift (gap conhecido do piloto — corrigido na Fase 2)
- **Flo**: nunca inventa dado — mostra "dado indisponível" se fonte stale

Ordem de implementação (Brief, 6 fases): Fase 1 = casca/estrutura → Fase 2 = fonte única + dados live → Fase 3+ = testes reais (A/B/C) e publicação.

---

## v6 — Casca / Fase 1 (28/09/2026) — FECHADA, em revisão, NÃO é o live

**URL de revisão:** https://claude.ai/artifact/WbNHnb4c3dUdBkirMKsFDz

Artefato **novo e separado**, publicado deliberadamente sem `url` para não tocar no live.

### Baseline utilizada

**Snapshot v5 — Golden Run 28/09/2026**, `https://claude.ai/artifact/URdEduVJvpzJLPPRQTFZ8A` (congelado antes de qualquer alteração). Continua sendo o rollback baseline. Estado dos três URLs depois desta entrega:

| URL | Papel | Tocado? |
|---|---|---|
| `5c3800d9-4362-428d-989f-7d97f32808c5` | live (v5) que a Odara abre todo dia | ❌ intacto |
| `URdEduVJvpzJLPPRQTFZ8A` | Golden Run 28/09, rollback baseline | ❌ intacto |
| `WbNHnb4c3dUdBkirMKsFDz` | casca v6 para revisão | ✅ novo |

### O que mudou na v6 (Fase 1 — só estrutura)

Casca completa da experiência descrita na Spec v0.1: splash + carta principal → board com Night Shift Report, ⚓ À Sua Espera, Radar, Task Backlog (Hoje+Semana / Overdue), Notícias em 5 abas e Treasures como última seção. Mesa com os 4 widgets do contrato, cada um como carta virável com persona dona, avatar e ações próprias. Contrato de resiliência (`Normal → Retry → Plano B → Erro`) implementado via `setState(secId, estado)` em todas as seções. Sem XP em lugar nenhum. Flo sem botão Regenerate (persona não-generativa).

### ⚠️ Limitação declarada: Fase 1 é estrutura, não conteúdo

**Todos os dados na casca são mock.** Nada vem do Notion, do Gmail ou do Calendar ainda. Em particular:

- As **notícias são placeholders explícitos**, não manchetes reais — nenhuma notícia foi inventada nem apresentada como verdadeira
- O **Widget Registry está embutido no JS do arquivo**, como stand-in. Migrar para o Notion é alvo da Fase 2
- A **Flo** ainda não tem fonte canônica de data de ciclo identificada — até lá o widget mostra "dado indisponível" em vez de inventar. Comportamento seguro mantido deliberadamente.

### Testes executados e resultado

Pipeline obrigatório do Spec §15 (`gerar → validar → corrigir → validar novamente → publicar → entregar`) executado por inteiro. Suite em `smoke-v6.js` (Playwright, Chromium headless). **Resultado final: 30/30 PASS.**

- **Teste A — desktop 1280×900 (16 checks):** sem erro de JS/console; splash visível; `#bussola` existe e vira; Report aparece; "Seguir para a mesa" leva ao board e o splash sai; exatamente 4 widgets; Flo sem botão Regenerate; nenhum "XP" em lugar nenhum; as 5 seções operacionais presentes; Task Backlog com 3 abas; Notícias com 5 abas; board termina em Treasures; **A16** — ações e avatar da persona visíveis em toda carta aberta.
- **Teste B — resiliência (5 checks):** `setState('s-radar','erro')` → seção continua visível, mensagem humana de erro aparece, resto do board intacto; estados `retry` e `planb` renderizam.
- **Teste C — mobile 390×844, isMobile+hasTouch (5 checks):** fluxo completo sem erro; board visível; sem scroll horizontal; mesa em 2 colunas; carta abre ao toque sem disparar ação.

Além dos testes automatizados: 5 screenshots mobile (DSF 2) do fluxo completo — splash, report, mesa, quest aberta, backlog.

### Bugs encontrados e corrigidos

Vale registrar porque justificam o pipeline: a casca passou **29/29 nos testes estruturais enquanto ainda violava o contrato de carta aberta**. Só o screenshot pegou.

1. **Avatar da persona cortado abaixo da borda da carta aberta.** Causa: `overflow-y:auto` na face inteira (`.mini-face.b`) combinado com `margin-top:auto` nas ações, que empurrava os botões para fora do corte. Correção: o scroll passou para `.mini-corpo` (`flex:1 1 auto;min-height:0;overflow-y:auto`) e as ações ganharam `flex-shrink:0`, ficando ancoradas no rodapé da face.
2. **Depois da correção, o avatar quebrava para uma segunda linha e o texto do corpo era cortado no meio da palavra** ("Veja o") numa carta de 168px — passava no teste, mas era ruim de usar. Correção: carta aberta passa a ocupar a largura da mesa no mobile (`grid-column:1/-1;aspect-ratio:auto;height:206px`) e 2 de 4 colunas no desktop (`grid-column:span 2;height:232px`).

### Regressões adicionadas

**A16 — "ações e avatar visíveis em toda carta aberta".** Abre cada carta da mesa, mede o retângulo de `.mini-acoes` contra o de `.mini-face.b` e falha se qualquer ação ficar fora dos limites da face; também falha se alguma carta aberta não tiver o avatar da persona. Guarda permanente do contrato de carta aberta da Spec, em vez de correção pontual.

### Limitações técnicas

- **Carta aberta exige altura em pixels explícita.** Como as faces são `position:absolute;inset:0`, o contêiner do flip **não pode** usar `height:auto` — colapsa para 0. Qualquer mudança de conteúdo nas cartas precisa revisar `height` de `.mini.open` nos dois breakpoints.
- **O `<title>` do próprio HTML sobrescreve o título passado na publicação** do artefato — o nome do artefato vem do documento, não do parâmetro.
- **Publicar sem `url` cria um artefato novo.** Foi o mecanismo usado aqui de propósito para proteger o live; é também o erro que gerou a Run Divergente de 27/09.
- Conector **Ticketmaster falhou em conectar** nesta sessão (erro de protocolo). Não era necessário para a Fase 1, mas precisa ser reconectado se voltar a ser usado.

### Decisões bloqueantes para a Fase 2

Adiadas deliberadamente para 29/09 — **não resolver sozinho**:

1. **Schema do Widget Registry no Notion.** Precisa dos campos Skill / persona dona / avatar / ações / Ativo-Pausado antes de a composição da mesa sair do JS embutido. Não criado hoje.
2. **Fonte canônica da data de ciclo da Flo.** Player Sheet parado desde 15/08/2026. Até a decisão, o comportamento seguro se mantém: dado indisponível → estado explícito, nunca inferir nem inventar fase do ciclo.

Também segue pendente da Spec: fonte única entre a versão manual e a agendada do Bom Dia para o bloco de Night Shift.

### Próximo passo

Aguarda revisão da Odara no URL de revisão. Promoção para o live é decisão conjunta, depois da revisão — não acontece automaticamente.

---

## Decisões Fechadas (GM + Odara)

Decisões que fecham ambiguidades identificadas em audit. Uma vez documentadas aqui, são canônicas para futuras runs.

### C1 — Seleção de Tema (fechado 27/09/2026)

**Regra:** Entre todos os temas com `Status = Ativo` no Registro de Temas, selecionar um tema usando a **data local de Barcelona como seed determinístico**. O tema selecionado permanece fixo para aquele dia calendário.

**Algoritmo:**
```
seed = data numérica sem separadores (ex: 20260927)
índice = seed % total_de_temas_ativos
tema = temas_ativos[índice]  (ordenados por ordem de aparição no Registro)
```

**Exemplo:** 20260927 % 4 = 3 → índice 3 → **Alquimista Celeste** (27/09/2026)

**Regras:**
- A mesma data sempre produz o mesmo tema (determinístico)
- NÃO usar: dia da semana, humor, clima, julgamento contextual do GM, ou qualquer outro sinal
- NÃO usar: aleatoriedade verdadeira (seria diferente a cada run do mesmo dia)
- Mudança no número de temas ativos muda o mapeamento → documentar quando acontecer

### C2 — XP nas Mini Cards (fechado 27/09/2026, reforçado na Spec v0.1)

**Regra:** Na versão atual do Bom Dia Claude, **não exibir XP dentro do card Mini Side Quest**. O verso do card deve conter apenas a `Descrição do desafio do dia` do campo correspondente no Registro de Cartas — nada mais.

**Contexto:**
- XP é uma camada opcional do Odyssey (conforme Playbook) — não está globalmente proibido
- O bug original era conteúdo hardcoded (`+15 XP`, `+40 XP`) que não vinha do banco de dados
- O contrato do card no estado atual: verso = Descrição do Registro de Cartas somente
- Para adicionar XP às cards no futuro: requer alteração deliberada ao contrato do card (campo novo no Registro de Cartas ou nova mecânica documentada), não pode ser hardcoded

---

## Snapshots congelados

### MVP v1 — 05/09/2026
**URL:** https://claude.ai/code/artifact/749b3624-56c5-4d14-85a6-ba99fd2ae836

O que tinha neste snapshot:
- Splash com flip de carta (IX — A Bússola, tema Alquimista Celeste)
- 5 mini cards com flip (incluía Arcano — já removido na versão live pós-MVP)
- Mobile fix: 2 cartas por fileira em telas ≤ 520px
- Backlog com abas Hoje / Semana / Mês
- 3 blocos journal separados: A Gazeta (Notícias) + Eventos (c/ fallback Ticketmaster) + O Correio
- Poções Rápidas + painel de feedback

**Regra:** nunca publicar nesse URL. Só abre pra ler/copiar se a versão live quebrar.

---

### Run Divergente — 27/09/2026
**URL:** https://claude.ai/artifact/8q6DdmpVMejAH3MFxcXDf1

⚠️ ARTEFATO FORA DA ESPECIFICAÇÃO — Publicado em URL errado (novo, não o live). Criado numa run automática com contexto resumido. Divergências documentadas no chat de auditoria de 27/09/2026.

Divergências estruturais principais: layout grid de 4 colunas (não mesa de tarot vertical), sem introStage, sem journal blocks, CSS variables incorretas, fontes erradas (Georgia), HTML de mini cards incorreto, XP mencionado no Side Quest, Poções inventadas (não lidas do Registro de Ações Rápidas), Flo com link errado, conteúdo hardcoded (PRÉ-VÔLO não executado de verdade).

**Regra:** não usar como referência. A versão live canônica continua sendo o MVP v1 URL acima até que uma versão corrigida e validada seja publicada no live URL.

### Run Corrigida — 27/09/2026 (Alquimista Celeste)
Publicada sobre o live URL canônico na sessão de auditoria de 27/09/2026.

Correções aplicadas vs. run divergente:
- URL: live canônico (5c3800d9) ✓
- Tema: Alquimista Celeste (#241033 / #8C2F6A / #C9A227) via C1 ✓
- Data: Domingo 27/09/2026 ✓
- Flo: 🌙 fase folicular dia 13 (fora da janela [-7,+5]) — sem Blood Moon ✓
- Side Quest: sem XP hardcoded (C2) ✓
- Poções: prompts exatos do Registro de Ações Rápidas ✓
- JS: addEventListener (sem onclick inline) ✓
- PRÉ-VÔLO executado de verdade ✓

### Snapshot v5 — Golden Run 28/09/2026 (FROZEN — baseline pré-v6)
**URL:** https://claude.ai/artifact/URdEduVJvpzJLPPRQTFZ8A

Cópia congelada do estado exato do live URL na manhã de 28/09/2026 (Golden Run, referência de feeling aprovada por Odara), capturada **antes** do início da implementação v6.

O que tinha neste snapshot:
- Tema: Diário do Capitão (vinho/dourado/mar)
- Splash: carta "A Bússola" (⚓), flip único
- 4 mini cards: Mini Side Quest (🩺 Health Quest), Soundtrack (Nemo — Nightwish), Flo (🌙 dia ~14 do ciclo), Word of the Day (Travesía)
- Journal: Agenda (pessoal + Fortis + alerta Meteocat) + Notícias 3 abas (Mundo/Esp+BCN/Brasil) + Task Backlog 3 abas (Hoje/Semana/Mês)
- Quick Actions: Calendar Check + Gmail Sweep + O que tá pendente?
- Dados hardcoded — sem query live ao Notion
- Sem Night Shift Report, sem À Sua Espera, sem resiliência (blocos desaparecem silenciosamente em falha)

**Regra:** este é o rollback baseline para a implementação v6. Se v6 precisar ser revertida, copiar este HTML e republicar no live URL (5c3800d9).

---

## Como fazer rollback

1. Abrir o snapshot URL acima
2. Copiar o HTML completo
3. Colar num novo chat e pedir pra republicar na versão live
