# [ARCHIVE] Bom Dia Claude (Rotina Matinal Completa)

> 🧭 **EXPERIENCE SPEC APROVADO — 28/09/2026**
> 

> A experiência do Bom Dia Cláudio foi consolidada e aprovada. A especificação detalhada está na página filha **Bom Dia Cláudio — Experience Spec v0.1 (Aprovado 28/09/2026)**. Esta página continua sendo o repositório da rotina, template, registries e histórico de implementação; a nova página é o contrato de experiência aprovado para a próxima implementação.
> 

> 
> 

> [[ARCHIVE] Bom Dia Claude — Experience Spec v0.1 (Aprovado 28/09/2026)](%5BARCHIVE%5D%20Bom%20Dia%20Claude%20(Rotina%20Matinal%20Completa)/%5BARCHIVE%5D%20Bom%20Dia%20Claude%20%E2%80%94%20Experience%20Spec%20v0%201%20(A%203e9107b19b4981c1b079c0241c174426.md)
> 

> 
> 

> **Importante:** o Golden Run de 28/09/2026 é referência comportamental, não substituto do spec. Não copiar desvios de implementação do run sem decisão explícita.
> 

> 
> 

> ---
> 

> Rotina matinal completa, disparada quando ela diz "bom dia"/"oi" no chat dedicado **"Bom dia Claude"**. A partir de 2026-08-22, entregue como **artefato HTML** (um "diário de bordo" visual), não mais texto puro de chat. Ainda leve no espírito do [Bom Dia (Daily Light Touch)](https://app.notion.com/p/3aa107b19b498099b7fffbcf87b857f2?pvs=21) do Playbook, agora com identidade visual própria.
> 

## 🎨 Sistema de Temas (novo, 2026-09-02)

Quatro temas visuais aprovados (gerados pelo Chatty), registrados no banco [🎨 Registro de Temas](https://app.notion.com/p/38ff8a5679304531af0ed5e4a0d4bd2c?pvs=21): **Alquimista Celeste** (místico/roxo), **Carta Náutica** (marinho/teal), **Sussurros da Noite** (oculto/escuro+vermelho), **Diário do Capitão** (quente/aconchegante). Cada um define cor base/acento/secundária, aplicadas via CSS custom properties (`body[data-theme="..."]`).

**Regra de seleção atual: aleatório entre os temas com Status=Ativo**, sorteado uma vez na geração do dia (não muda depois de gerado). **Evolução futura planejada**: conectar a seleção ao Mood dela ou a elementos do mundo real (clima, estação do ano) — campo "Regra de Seleção" no banco já prevê essas opções, só não implementadas ainda.

Mais temas podem ser adicionados ao banco a qualquer momento, sem precisar mudar código — só popular uma nova linha com Status=Ativo.

## 📋 Cartas ativas (v5, 2026-09-05)

**4 mini cards definitivos**: Flo, Word of the Day, Soundtrack, Mini Side Quest (chamado "Side Quest" na v5). **"Hoje" foi aposentado de propósito** — seu papel de "resumo do dia" já é coberto pela Carta do Dia (splash). Ver [Registro de Cartas](https://app.notion.com/p/d0b4bec77b2f4297b25d1f2aed300072?pvs=21) pra status atualizado de cada widget.

## 📰 Nome oficial da seção de notícias

**"Notícias do Dia"** é o nome funcional/estrutural (usado em toda documentação). "A Gazeta"/"Odyssey Gazette" continuam válidos como apelido estilístico/kicker na tela — os dois convivem, não é renomeação real.

Ela abre um chat só, uma vez de manhã, e sai sabendo tudo que precisa — mas também sente um pouco de surpresa/diversão no processo, não só informação seca. Ela mesma pediu "uma pitada de caos" aqui.

## 🎨 Identidade Visual (design tokens — versão 2, 2026-08-23)

**Substitui a versão 1** (pergaminho claro + selo). Nova direção após várias iterações com referências reais (Pinterest + imagens geradas): **mesa de tarot mística**, fundo quase preto, dourado em linework fino, blocos de conteúdo como "cartinhas pousadas na mesa".

- **Paleta:** fundo quase preto `#100D0B`, ouro velho `#C9A227` (acento principal, bordas, textos de destaque), vinho `#6B1F2A`, veludo `#3B1F3D`, mar profundo `#16303B` (cores alternadas nos cards "pousados"), pergaminho `#E8DCC3` (texto principal sobre fundo escuro)
- **Tipografia:** Cinzel (títulos/display, elegante e com peso) + Cormorant Garamond itálico (frases/citações) + Karla (corpo) + IBM Plex Mono (labels/datas)
- **Cabeçalho**: **removido** (versão anterior tinha card de pergaminho com selo + frase "minha vida não é uma história..." — descartado). A página agora **começa direto** com uma linha discreta de clima+data (`BARCELONA · 23°C / 29°C ☀️ · DOMINGO, 23/08` — **nunca coordenadas geográficas**), seguida do título "Odyssey / A Carta do Dia"
- **Títulos de seção**: formato só "TÍTULO ···········" (linha tracejada dourada do lado) — **sem numeração** (01/02/03 foi removido)
- **Divisor entre a Intro Section e as demais seções**: linha pontilhada dourada com medalhão de estrela no centro (mesmo espírito visual da página, versão mais simples que o antigo divisor de corda)
- **Blocos de conteúdo** ("table-cards"): cada bloco (Flo, Soundtrack, Word of the Day, etc.) é uma cartinha independente com moldura dourada dupla, levemente inclinada (rotação sutil `-0.6°` a `0.5°`), cor de fundo alternando entre vinho/veludo/mar profundo — **sempre cores diferentes entre cards vizinhos na mesma linha**, nunca duas cartas próximas com a mesma cor (senão somem na mesa)
- **Ilustrações encaixadas**: navio dourado (marca d'água no card "Hoje", imagem gerada com fundo removido, base64) e **amuleto simbólico em SVG puro** no card do Flo (lua crescente + olho + conchas + correntinha — nunca uma figura de mulher/cigana literal, por diretriz do sistema de design). Reintroduzido em 2026-08-23: card de saudação escuro no topo ("Bom dia, Odara", bússola + selo dourado, tagline fixa "Colecione experiências. Escreva sua lenda.").
- **Mobile-first, sempre.**

## 🎴 Sistema de Widgets — Mesa de Tarot v3 (2026-09-01)

**Muda a experiência inteira**: em vez de rolagem vertical de blocos, a página agora é uma **mesa de tarot de verdade**. Estado inicial: **só uma carta central** na mesa (Odyssey + data, sem mais nada visível). Ela clica/vira essa carta → depois de virar, as outras cartas (Flo, Hoje, Word of the Day, Soundtrack, Mini Side Quest) **são "distribuídas" na mesa** com animação em cascata (cada uma chega com um pequeno atraso, tipo baralho sendo aberto), não aparecem todas de uma vez.

**Cada carta agora é um widget independente, registrado no banco [🃏 Registro de Cartas](https://app.notion.com/p/d0b4bec77b2f4297b25d1f2aed300072?pvs=21)** — antes de gerar o dia, checar esse banco: só gerar cartas com Status = Ativo (pular Inativo, tratar Experimental com cautela). Cada linha do banco define: cor de fundo, regra da frente (o que decide o símbolo/número/texto grande visível sem precisar virar), regra do verso (o que aparece ao clicar), e quais links/ações aparecem e quando.

**Princípio central: bater o olho e entender.** A frente de cada carta é o **resumo já útil sozinho** — um número, símbolo, ou palavra que muda dia a dia conforme o conteúdo real (nunca um ícone genérico fixo). O verso (só ao clicar) é onde mora o detalhe/contexto/links de ação.

**Mecânica técnica de cada cartão pequeno (Flo, Hoje, etc.):**

- Card inteiro (moldura + sombra + fundo) vira junto como uma peça só — não só o conteúdo de dentro. O container externo fica transparente/sem borda (classe `has-flip`), e as faces internas (`.mini-face`) carregam todo o visual (borda dourada, sombra, fundo)
- Transição rápida (~0.45s), sem sensação de atraso
- Clicar em qualquer lugar do card (fora de um botão de ação) alterna frente/verso livremente, nos dois sentidos
- Botões de ação (Play, Registrar) usam `e.stopPropagation()` pra nunca disparar o flip sem querer
- 3 por linha, tamanho fixo (~190x260px), levemente rotacionadas (`--rot`, entre -4° e 3°) pra parecer cartas soltas na mesa, não uma grade rígida

**Hover**: leve elevação + brilho na borda dourada, em qualquer carta.

**Protótipo aprovado**: gerado em 2026-09-01, testado e ajustado ao vivo (velocidade, tamanho, isolamento de cliques). Usar como referência de comportamento pras próximas gerações — igual fazemos com o template HTML.

## 🃏 A Carta do Dia

Adoção total do conceito de tarot: em vez de só mostrar uma frase, ela **tira uma carta** todo dia.

- **Fica fechada por padrão** (verso escuro, verde+dourado, linework de lua/**estrelas de 4 pontas** — nunca bolinhas simples, texto "toque para tirar sua carta") — **só revela quando ela clica**, com animação de virar em 3D (CSS `rotateY`, `transform-style:preserve-3d`)
- **Frente revelada**: fundo gradiente quente (âmbar→laranja→vinho→escuro), número romano, símbolo em linework dourado, nome da carta (ex: "A Bússola"), e o significado/frase do dia
- **Baralho próprio do Odyssey** (não tarot genérico), cada carta ligada a um tema real da vida dela: O Corsário, A Cigana, A Bússola, A Maré, O Tesouro, A Taverna, O Mapa Aberto, A Lua, O Sol, A Âncora, A Estrela-Guia, O Grimório, O Espelho, As Chaves
- **Conecta com o motor de Side Quests**: quando a carta tiver ligação com holofote de Main Quest (ex: A Bússola, A Taverna), mostra uma linha extra abaixo tipo "↳ hoje o holofote cai sobre: [Main Quest]"
- **Sem tom clínico/preditivo real** — é biscoito da sorte com identidade, não horóscopo de verdade

## 📎 Template de Referência (v5)

> ⚡ **PRÉ-VÔLO OBRIGATÓRIO** — executar 3 queries via `notion-query-data-sources` (SQL) ANTES de qualquer geração:
> 

> 
> 

> **1. Mini cards** → `SELECT Nome, "Regra da Frente", "Regra do Verso", "Cor de fundo" FROM "collection://049c4322-6c07-4726-9af3-72844974938e" WHERE Status = 'Ativo'` — só gerar os retornados, nunca hardcodar
> 

> 
> 

> **2. Poções** → `SELECT Nome, "Ícone/Emoji", "Prompt de disparo" FROM "collection://bd11c886-f95f-4d7e-bae8-d9914d57d9e5" WHERE Status = 'Ativo'` — cada linha = um botão .qa-btn com Ícone + Nome, href = [claude.ai/new?q={Prompt](http://claude.ai/new?q=%7BPrompt) de disparo}
> 

> 
> 

> **3. Tema visual** → `SELECT Nome, "Cor Base", "Cor Secundaria", "Cor Acento" FROM "collection://c793eef1-b59d-405c-b0c5-d6a5a69e040d" WHERE Status = 'Ativo'` — sortear aleatório, aplicar cores via body[data-theme]
> 

**✅ Atualizado em 2026-09-05** — versão v5 alinhada com o artefato em produção. Artefato de referência vivo (sempre atual): [https://claude.ai/code/artifact/5c3800d9-4362-428d-989f-7d97f32808c5](https://claude.ai/code/artifact/5c3800d9-4362-428d-989f-7d97f32808c5)

**Regras permanentes:**

- Nunca usar onclick inline — sempre addEventListener (CSP do iframe bloqueia onclick)
- Sempre que mudarmos o protótipo numa sessão, atualizar esse template no mesmo dia
- Nunca incluir a tela de abertura (introStage) no blob gerado — ela é montada pelo GM no template

**O que mudou na v5 (2026-09-05):**

- Carta splash: retrato fixo 230×330px (não mais horizontal→vertical), gradiente roxo, com data+tema embutidos na face da carta (.c-date e .c-theme dentro do .front)
- **4 mini cards** (não 5): Side Quest, Soundtrack, Flo, Palavra do Dia — mini card de Arcano removido
- **Tasks em tabs**: Hoje / Semana / Mês — classes .t-tab / .t-panel (escopo global, IDs tpanel-hoje/semana/mes)
- **3 blocos de journal**: A Gazeta (tabs Mundo/BCN/Brasil), Eventos (tabs Barcelona/Games/Europa), O Correio
- **Notícias com links**: cada headline é um <a> apontando para busca Google ou URL da publicação, com ↗
- **Task chips**: .task-lnk — chips clicáveis em cada task com links diretos (LinkedIn, Treatwell, Maps, etc.)
- **Mobile**: 2 cartas por linha em telas ≤520px (flex: 0 0 calc(50% - 5px))
- **Tabs de journal escopados**: cada .journal trata seus próprios .j-tab / .j-panel via event delegation, sem conflito entre blocos

**Paleta/CSS completo (cole no `<style>`):**

```css
:root{--pergaminho:#E8DCC3;--tinta:#E8DCC3;--latao:#C9A227;--vinho:#6B1F2A;--veludo:#3B1F3D;--mar:#16303B;--rosa:#7A2E5C;--bg-ink:#100D0B;}
body{margin:0;padding:0;background:var(--bg-ink);font-family:'Karla',sans-serif;color:var(--tinta);}
.stage{position:relative;max-width:720px;margin:0 auto;padding:40px 14px 60px;}
.header{text-align:center;margin-bottom:10px;}
.deck-wrap{display:flex;justify-content:center;margin:34px 0 8px;perspective:1400px;}
.deck-card{width:330px;height:230px;position:relative;cursor:pointer;transform-style:preserve-3d;transition:transform 0.6s,width 0.6s,height 0.6s;}
.deck-card.flipped{transform:rotateY(180deg);width:230px;height:330px;}
.face{position:absolute;inset:0;backface-visibility:hidden;border-radius:14px;overflow:hidden;box-shadow:0 0 0 1px var(--latao);}
.back{background:radial-gradient(circle at 50% 50%,#2C4A34 0%,#1F3326 70%);}
.front{transform:rotateY(180deg);background:radial-gradient(circle at 50% 40%,#E8A33D 0%,#C1502E 32%,#6B1F2A 62%,#2C1B29 100%);}
.dealt-area{display:flex;flex-wrap:wrap;justify-content:center;gap:16px 14px;max-width:614px;margin:40px auto 0;}
.table-card{width:190px;height:260px;flex:0 0 190px;background:#1C1712;border:1px solid var(--latao);border-radius:11px;padding:16px 14px;position:relative;overflow:hidden;opacity:0;transform:translateY(-70px) scale(0.4);transition:transform 0.45s,opacity 0.35s;}
.table-card.c-vinho{background:#3A1219;} .table-card.c-veludo{background:#331B35;} .table-card.c-mar{background:#10262E;}
.table-card.dealt{opacity:1;transform:translateY(0) scale(1) rotate(var(--rot,0deg));}
.table-card.draggable{cursor:grab;} .table-card.dragging{cursor:grabbing;z-index:50;}
.table-card.has-flip{background:transparent;border:none;overflow:visible;}
.mini-flip-wrap{perspective:900px;width:100%;height:100%;}
.mini-flip{position:relative;width:100%;height:100%;cursor:pointer;transform-style:preserve-3d;transition:transform 0.45s;}
.mini-flip.open{transform:rotateY(180deg);}
.mini-face{position:absolute;inset:0;backface-visibility:hidden;border-radius:11px;display:flex;flex-direction:column;align-items:center;justify-content:center;text-align:center;padding:14px;border:1px solid var(--latao);background:#3A1219;}
.mini-back{transform:rotateY(180deg);}
.big-num{font-family:'Cinzel',serif;font-weight:600;font-size:52px;color:#D488A8;}
.register-link,.play-btn{display:inline-flex;align-items:center;gap:5px;font-family:'IBM Plex Mono',monospace;font-size:9.5px;text-transform:uppercase;padding:5px 10px;border-radius:999px;text-decoration:none;margin-top:10px;}
.register-link{color:#fff;background:var(--rosa);} .play-btn{color:#100D0B;background:var(--latao);}
/* divisor */
.divider{text-align:center;padding:34px 0 18px;}
.divider .medallion{width:28px;height:28px;border-radius:50%;border:1px solid var(--latao);background:var(--bg-ink);display:flex;align-items:center;justify-content:center;margin:-19px auto 0;}
/* jornal (Notícias/Eventos) */
.journal{background:#E8DCC3;color:#2A2117;border-radius:4px;padding:26px 22px 30px;margin-top:6px;}
.journal-mast{text-align:center;margin-bottom:18px;}
.journal-mast h2{font-family:'Cinzel',serif;font-weight:600;font-size:22px;margin:2px 0 10px;}
.journal-mast .rule-double{height:3px;border-top:1px solid #2A2117;border-bottom:1px solid #2A2117;margin:0 auto;width:70%;}
.j-tab-btn.active{background:#2A2117;color:#E8DCC3;}
.j-news-head{font-family:'Cinzel',serif;font-weight:600;color:#2A2117;text-decoration:none;display:block;}
.j-mail-summary{font-family:'IBM Plex Mono',monospace;font-size:11px;text-transform:uppercase;text-align:center;opacity:0.75;margin-bottom:14px;}
.j-mail-list{list-style:none;padding:0;margin:0;} .j-mail-item{padding:10px 0;border-top:1px solid rgba(42,33,23,0.15);} .j-mail-item:first-child{border-top:none;}
.j-mail-head{font-family:'Cinzel',serif;font-weight:600;color:#2A2117;text-decoration:none;display:block;font-size:14px;} .j-mail-item p{margin:4px 0 0;font-size:12.5px;opacity:0.85;}
/* poções */
.quick-actions{margin-top:30px;text-align:center;}
.qa-btn{display:inline-flex;align-items:center;gap:7px;font-family:'IBM Plex Mono',monospace;font-size:11px;color:var(--tinta);background:#1C1712;border:1px solid var(--latao);padding:9px 16px;border-radius:999px;text-decoration:none;}
.qa-btn.planned{opacity:0.4;}
/* intro stage (splash) */
#introStage{position:fixed;inset:0;z-index:200;background:var(--bg-ink);display:flex;align-items:center;justify-content:center;transition:opacity 0.5s;}
#introStage.gone{opacity:0;pointer-events:none;}
.stage-content{opacity:0;transition:opacity 0.6s;} .stage-content.revealed{opacity:1;}
#restingCardSlot{width:230px;height:330px;margin:0 auto 8px;opacity:0;transition:opacity 0.4s;} #restingCardSlot.show{opacity:1;}
```

**Estrutura HTML (splash + carta + mesa):**

```html
<div id="introStage">
  <div class="deck-wrap" style="margin:0;">
    <div class="deck-card" id="deckCard">
      <div class="face back">
        <svg width="100%" height="100%" viewBox="0 0 330 230"><g stroke="#D4AF4E" fill="none" stroke-width="0.8" opacity="0.55"><circle cx="165" cy="105" r="60"/></g><g fill="#D4AF4E"><path d="M165 55 l4 12 12 2 -9 8 3 12 -10 -7 -10 7 3 -12 -9 -8 12 -2 z"/></g></svg>
        <div class="hint">toque para tirar sua carta</div>
      </div>
      <div class="face front" id="introFrontFace">
        <div class="num">[NUMERO ROMANO]</div>
        <div class="card-title">[NOME DA CARTA]</div>
        <div class="quote">"[SIGNIFICADO - gerado dinamicamente]"</div>
      </div>
    </div>
  </div>
</div>

<div class="stage">
  <div class="stage-content" id="stageContent">
    <div class="header">
      <div class="eyebrow">Odyssey</div>
      <div class="title">Daily Summary · [DD.MM]</div>
    </div>
    <div id="restingCardSlot"></div>
    <div id="cardConnect" style="text-align:center;opacity:0;">hoje o holofote cai sobre: [MAIN QUEST]</div>

    <div id="dealtArea" class="dealt-area"><!-- Flo, Hoje, Word, Soundtrack, Mini Side Quest aqui, ver seção de cada widget --></div>

    <div class="divider"><div class="medallion">✦</div></div>

    <div class="journal"><!-- Notícias + Eventos aqui --></div>

    <div class="quick-actions"><!-- Poções aqui --></div>
  </div>
</div>
```

**Flo (amuleto SVG) + Hoje (navio SVG), lado a lado:**

```html
<section style="display:grid;grid-template-columns:1fr 1fr;gap:12px;">
  <div class="table-card c-vinho">
    <svg class="illustration" width="100" height="100" viewBox="0 0 100 100" style="right:-8px;bottom:-8px;">
      <g stroke="#D488A8" fill="none" stroke-width="1">
        <path d="M55 30a16 16 0 1 0 0 32 20 20 0 1 1 0-32z" fill="#D488A8" stroke="none" opacity="0.9"/>
        <circle cx="52" cy="46" r="7" opacity="0.85"/>
        <circle cx="52" cy="46" r="2.3" fill="#D488A8" stroke="none" opacity="0.9"/>
        <path d="M45 46 Q52 41 59 46" opacity="0.7"/>
        <path d="M45 46 Q52 51 59 46" opacity="0.7"/>
        <path d="M52 53 L50 78 M52 53 L58 80" opacity="0.55"/>
        <ellipse cx="42" cy="86" rx="5" ry="3.2" opacity="0.7" transform="rotate(-20 42 86)"/>
        <ellipse cx="67" cy="86" rx="4.5" ry="3" opacity="0.7" transform="rotate(15 67 86)"/>
      </g>
    </svg>
    <div class="stat-label">Flo</div>
    <div class="stat-value">[STATUS DO CICLO]</div>
  </div>
  <div class="table-card c-mar">
    <svg class="illustration" width="110" height="90" viewBox="0 0 110 90" style="right:-10px;bottom:-6px;opacity:0.4;">
      <g stroke="#E4C466" stroke-width="1" fill="none">
        <path d="M55 15 L55 60"/>
        <path d="M55 20 L78 32 L55 42 Z" fill="#E4C466" opacity="0.7" stroke="none"/>
        <path d="M55 24 L36 34 L55 40 Z" fill="#E4C466" opacity="0.55" stroke="none"/>
        <path d="M20 62 L90 62 L78 78 L32 78 Z" fill="#E4C466" opacity="0.5" stroke="none"/>
        <path d="M10 62 Q30 55 50 62 T90 62 T110 60" opacity="0.6"/>
        <path d="M5 72 Q30 63 55 72 T105 70" opacity="0.4"/>
      </g>
    </svg>
    <div class="stat-label">Hoje</div>
    <div class="stat-value">[UMA LINHA SOBRE HOJE]</div>
  </div>
</section>
```

**Word of the Day + Soundtrack, Mini Side Quest, e as 3 seções finais:**

```html
<section style="display:grid;grid-template-columns:1fr 1fr;gap:12px;">
  <div class="table-card c-veludo">
    <div class="stat-label">Word of the Day</div>
    <div class="stat-value">[PALAVRA/EXPRESSAO]</div>
  </div>
  <div class="table-card c-mar">
    <div class="stat-label">Soundtrack</div>
    <div class="stat-value">[ARTISTA - MUSICA] + botao Play</div>
  </div>
</section>
<div class="table-card c-vinho">
  <div class="stat-label">Mini Side Quest</div>
  <div class="stat-value">[DESAFIO DO DIA - imagem opcional]</div>
</div>
<section class="table-card c-mar">
  <div style="font-weight:600;color:var(--latao);text-transform:uppercase;">Tasks and Obligations</div>
  <div>abas: Hoje / Semana / Mes -- Rigido primeiro depois Flexivel</div>
</section>
```

**Word of the Day + Soundtrack, Mini Side Quest:**

```html
<section style="display:grid;grid-template-columns:1fr 1fr;gap:12px;">
  <div class="table-card has-flip c-veludo"><!-- Word of the Day, mesmo padrao mini-flip --></div>
  <div class="table-card has-flip c-mar"><!-- Soundtrack, mesmo padrao mini-flip, botao play no verso --></div>
</section>
<div class="table-card has-flip c-vinho"><!-- Mini Side Quest, mesmo padrao mini-flip --></div>
```

**Notícias do Dia e Eventos (dentro do `.journal`):**

```html
<div class="journal-block">
  <div class="journal-mast"><div class="kicker">Odyssey Gazette</div><h2>Notícias do Dia</h2><div class="rule-double"></div></div>
  <div class="j-tabs"><!-- botoes Mundo / Espanha-BCN / Brasil, data-jgroup=news --></div>
  <!-- paineis .j-tab-panel com .j-news-item --></div>
</div>
<div class="journal-block">
  <div class="journal-mast"><div class="kicker">Odyssey Gazette</div><h2>Eventos</h2><div class="rule-double"></div></div>
  <div class="j-tabs"><!-- botoes Local / Games / Europa, data-jgroup=events --></div>
  <!-- paineis .j-tab-panel com .j-event-card --></div>
</div>
<div class="journal-block">
  <div class="journal-mast"><div class="kicker">Odyssey Gazette</div><h2>Correspondência</h2><div class="rule-double"></div></div>
  <div class="j-mail-summary">[N] newsletters arquivadas automaticamente hoje</div>
  <ul class="j-mail-list">
    <!-- um <li class="j-mail-item"> por e-mail que precisa de atencao real -->
    <!-- <li class="j-mail-item"><a class="j-mail-head" href="[link gmail]">[Remetente — assunto curto]</a><p>[frase de contexto/acao sugerida]</p></li> -->
  </ul>
</div>
```

**Poções (fim da página, fora do `.journal`):**

```html
<div class="quick-actions">
  <div class="qa-label">🧪 Poções</div>
  <div class="qa-row"><!-- ler do banco Registro de Ações Rapidas, Status=Ativo. Cada uma vira <a class="qa-btn" href="claude.ai/new?q=..."> --></div>
</div>
```

**JS — comportamento completo** (o Notion bloqueia blocos grandes de JavaScript bruto por segurança/WAF — o código exato deve ser puxado do **protótipo aprovado**, referenciado no repositório GitHub `odarambmenezes/odyssey`; isso aqui é o resumo funcional do que o código faz):

1. Clique na carta central → adiciona classe `flipped` no elemento (dispara o flip 3D via CSS + muda largura/altura de deitada pra em pé, tudo na mesma transição)
2. **~750ms depois**: clona o conteúdo da frente da carta pro slot de descanso no topo da página (resetando `transform` e `backface-visibility` do clone — senão ele renderiza invisível, bug já encontrado), esconde a tela de abertura, revela a página real
3. **~900ms depois**: cada carta em `#dealtArea` ganha a classe `dealt` com atraso escalonado de **90ms** entre uma e outra (efeito cascata) — **não 150ms**, isso foi acelerado numa iteração posterior
4. Depois disso: ativa o drag-and-drop nas cartas (Pointer Events unificando mouse+touch; threshold de 5px de movimento pra distinguir clique de arrasto; ao soltar sobre outra carta, troca as duas de posição no DOM)
5. Cada mini card (Flo, Hoje, Word of the Day, Soundtrack, Mini Side Quest) alterna frente/verso ao clicar em qualquer parte do card, exceto em botões de ação (que usam `stopPropagation` pra nunca disparar o flip)
6. Abas da seção jornal alternam painéis dentro do mesmo bloco (Notícias e Eventos têm grupos de abas independentes)

**Regra fixa de sempre**: nunca `onclick="..."` inline — sempre `addEventListener`, em tudo.

## 🔁 Trigger

Ela diz "bom dia" ou "oi" dentro do chat **"Bom dia Claude"**.

## 📋 Intro Section — ordem exata (sem duplicar nada)

**⚠️ Versão antiga removida em 2026-08-24**: havia aqui um "banner ilustrado ODYSSEY/Daily Summary" (gradiente teal→latão com ondas) E uma "Frase do Dia em 2 colunas" separada — **os dois foram descartados e substituídos pela Carta do Dia** (ver seção acima). Se qualquer geração futura reconstruir um banner grande tipo "ODYSSEY / Daily Summary" com ondas SVG, ou uma frase separada da carta, **isso está errado** — use o template anexado como referência exata.

**Ordem correta, sem duplicar:**

1. Card de saudação escuro ("Bom dia, Odara", bússola + selo, tagline fixa)
2. Linha de clima+data (`BARCELONA · 23°C / 29°C ☀️ · DOMINGO, 23/08`)
3. Título pequeno "Odyssey / A Carta do Dia"
4. A carta em si (flip 3D, ver seção 🃏 acima) — **essa é a única "frase do dia" que existe agora**, não tem outra em paralelo
5. Flo + Hoje lado a lado
6. Word of the Day + Soundtrack lado a lado
7. Mini Side Quest
- **Flo** (renomeado de "Flo Status", emoji 🩸) — **card lado a lado com Hoje** no grid de status: foco simplificado — (a) **quantos dias faltam pra menstruação**, só mostrado se estiver **dentro de 5 dias antes**; (b) **sintomas rápidos de esperar** naquele momento do ciclo, direto e fácil de entender; **não precisa focar em nome de fase**. **Quando não tem nada relevante pra mostrar** (fora da janela de 5 dias), a mensagem é sempre no mesmo tom leve/diário-de-bordo do resto do card — nunca genérica ou seca (ex: "ciclo tranquilo, nada previsto ainda", variando a frase entre gerações, mesmo espírito das frases de calendário vazio). Inclui **link pro app Flo** direto no título "Flo" — usar sempre `https://apps.apple.com/es/app/mi-calendario-menstrual-flo/id1038369065`. Dados em [Player/Character Sheet](https://app.notion.com/p/Player-Character-Sheet-3aa107b19b4981b192b1fc071711e4b0?pvs=21).

### 🩸 Confirmação de período (regra nova)

Quando a data prevista de menstruação chegar (ou passar sem confirmação), o card Flo **substitui completamente** seu conteúdo padrão por uma pergunta **divertida e no tom do diário de bordo**, sempre incluindo o dia específico previsto de um jeito natural na frase — não precisa ser texto fixo tipo "Day 1?". Claude tem liberdade criativa aqui, exemplos do espírito certo: *"Blood Moon Started? (Day 1)"*, *"A Maré Vermelha está chegando (Day 2)"*. **Não** listar várias opções juntas — sempre um único dia, o que fizer sentido pra aquela data específica. Botão ao lado com label **"🩸 Register"** (não existe emoji oficial do logo do Flo no Unicode, então usa a gotinha 🩸 já estabelecida como ícone do Flo em todo o design), mesmo link de sempre pro app Flo, pra ela registrar lá também. Quando ela confirmar em qualquer chat ("tô no dia 1", "chegou hoje", etc.), o Claude deve:

1. Atualizar o **início do ciclo** na [Player/Character Sheet](https://app.notion.com/p/Player-Character-Sheet-3aa107b19b4981b192b1fc071711e4b0?pvs=21) (data de hoje menos os dias que ela informar, se não for exatamente dia 1)
2. A partir daí, o card Flo passa a contar **"Dia X do período"** nos dias seguintes, até ela sinalizar que acabou (ou até passar a duração típica do período, ~5 dias, sem confirmação em contrário)

Mesma regra de autoridade de escrita de sempre: só atualiza mediante confirmação dela na conversa, nunca por dedução.

- **Word of the Day** — **card à esquerda**, lado a lado com Soundtrack (cor veludo). Palavras/expressões úteis, majoritariamente espanhol, catalão com menos frequência. Botão "🔄" cicla opções pré-geradas direto no navegador (JS, sem chamar o Claude de novo).
- **Soundtrack** (nome fixo — nunca "Trilha do Dia"/"Trilha de Hoje") — **card à direita**, ao lado de Word of the Day (cor mar profundo): skew pra energia de acordar, não pra dramático/balada. Puxa do [perfil musical dela](https://app.notion.com/p/Perfil-de-Entretenimento-Filmes-S-ries-Jogos-M-sica-3af107b19b4981848caee3cfed043b2c?pvs=21). Nome da música + botão "Play" (ícone Spotify aproximado), sem descrição extra.
- **Mini Side Quest** — continua como estava, **mais uma regra nova**: pode trazer **uma imagem opcional**, se ajudar de verdade a visualizar a quest (ex: uma referência de cor, still de filme/série, capa de álbum). Só inclui imagem quando for genuinamente útil pra entender a quest — nunca só por decoração, e nunca deixa espaço vazio reservado quando não tiver imagem relevante.

## 📋 Seção 2 — Tasks & Obligations (renomeado de "Obligations")

**Formato: abas Hoje / Semana / Mês**

- **Hoje**: tudo que vence hoje ou já está vencido, **independente de Rigidez** (Rígido ou Flexível) — ela quer ver tudo e decidir ela mesma se posterga ou não, sem eu pré-filtrar por Flexível
- **Semana**: semana atual (segunda a domingo), como já era
- **Mês**: janela mais ampla — principalmente os Flexíveis que ainda têm folga, dando visão do mês inteiro

Ordenado por **Rigidez** primeiro em qualquer aba (🔺 Rígido sempre no topo, urgência real), depois Flexível (tom de janela/sugestão — ver Codex, campo Rigidez), dentro de cada grupo por data.

**Obligations vencidas sem confirmação**: aparecem separado, mesma lógica de Rigidez pro tom.

**Calendar Check** (renomeado de "My Calendar"): eventos do Google Calendar, **visão única, sem abas**, **formato de lista com bullet points de verdade** (`<ul><li>`, não divs separadas parecendo título):

- **Fortis Early Meeting sempre é o primeiro bullet da lista**, quando existir: se tem reunião antes das 16h Barcelona time (horário da daily fixa da equipe), aparece como **"💼 Fortis Early Meeting: 14:45, 24/08"**, linkado pro evento (`htmlLink`, funciona mesmo em modo só busy/free — abre no app do Google Calendar do celular). Se não tiver reunião antes das 16h, esse bullet simplesmente não entra na lista.
- **Eventos pessoais** (`odarambmenezes@gmail.com` + `tacomigoencomendas@gmail.com`) entram como os bullets seguintes, mesmo formato de lista, título + horário + link.
- **Se a lista toda estiver vazia** (nem Fortis Early Meeting nem eventos pessoais), aí sim mostra só a frase divertida de "nada marcado" (ver abaixo) — sem lista nenhuma nesse caso.

**Próximos feriados (janela de 15 dias)**: **só Barcelona/Espanha** (não mapeia Brasil aqui — isso ficou só uma exploração inicial, não vale). Fonte: calendário público `en.spain#holiday@group.v.calendar.google.com`, mais busca na web pra feriados locais específicos da Catalunha/Barcelona que esse calendário nacional pode não pegar. **Bloco só aparece se tiver algo real** dentro da janela — se não tiver feriado nenhum vindo, o bloco inteiro fica oculto, não mostra "sem feriado" como texto vazio.

Se ela compartilhar mais calendários de outras contas pessoais no futuro, entram automaticamente. **Estado vazio (sem eventos pessoais) é sempre uma frase divertida e variada**, no espírito diário de bordo — nunca o texto literal "nada marcado em [email]". Claude varia a cada geração, exemplos do tom certo: *"Mar calmo hoje, capitã — nenhum compromisso à vista no horizonte"*, *"Agenda tão vazia quanto um domingo de verão"*, *"Bandeira branca hasteada, zero reuniões no radar"*, *"Página em branco hoje — escreve nela o que quiser"*. Sem separar por manhã/tarde/noite, só listar com horário + link direto pro evento quando houver algo.

**Cada item tem checkbox "✓ já fiz"** — ver seção de Feedback Acumulado abaixo pra como isso vira ação real.

**Cada título de Obligation é um link direto pra sua página no Notion** — mas **só quando essa página tem conteúdo real pra ver/interagir** (ex: "Conferir assinaturas recorrentes" tem uma tabela rica de assinaturas, vale linkar). Se a página não tem nada além dos campos padrão (Descrição/Notas vazias), **deixa sem link** — não adianta linkar pra uma página vazia.

**Autoridade de escrita**: mantém a regra já existente — Claude só atualiza o Backlog mediante confirmação dela na conversa (Última vez feito, Próximo Deadline recalculado, Status vira Feito (Ciclo) ou Done conforme Recorrência — ver Codex, Completion Protocol).

## 📤 Feedback Acumulado (novo — interatividade)

**Formato: toggle/colapsável** (`<details>`/`<summary>` no HTML) — fica fechado por padrão, só abre se ela clicar. Não ocupa espaço vertical constante na página.

**Limitação técnica real**: um HTML estático não consegue se comunicar com o Claude em segundo plano — não existe ponte ao vivo. A solução usa a mesma técnica do botão de retry (link pra `claude.ai/new`), só que acumulando mais contexto:

- **Checkboxes** em cada Task/Obligation ("✓ já fiz")
- **Campo de texto livre** pra "novo favorito" (música/evento) ou "nova obligation/lembrete"
- **Botão "Enviar atualizações"** no rodapé: via JS, monta um resumo estruturado de tudo que foi marcado/preenchido e abre `https://claude.ai/new?q={resumo}&surface=cowork&composer=mini` — isso abre uma conversa nova onde o Claude processa e aplica as mudanças de verdade (marca Feito (Ciclo)/Done, cria Obligation, atualiza Favoritos). **A data de geração do artefato vai embutida no resumo** (ex: "Já feitos em 23/08/2026: X, Y. Atualizar Última vez feito = 23/08/2026") — essencial pro Claude na conversa nova saber exatamente qual data usar pro cálculo de recorrência, sem depender de assumir "hoje" (que pode já ser outro dia quando ela realmente clicar no botão).

**Botões de ação rápida na seção Eventos**: cada card de evento ganha um botão "+ favorito" — clicar registra interesse naquele evento específico via o mesmo mecanismo de link (`claude.ai/new`), e o Claude pode trazer mais detalhes/acompanhar aquele evento depois. ⚠️ Limitação honesta: não existe forma de o link reabrir literalmente a mesma thread do chat "Bom dia Claude" — cada clique abre uma conversa NOVA. O que garante que funciona do mesmo jeito: o seed do link identifica explicitamente que é feedback do Bom Dia Claude e aponta pros mesmos dados do Notion, então o resultado é equivalente na prática, mesmo não sendo a mesma thread.

## 📋 Seção 3 — Awareness

**Formato: abas clicáveis, não lista vertical única** — evita o HTML ficar gigante, e já deixa mais interativo (implementado com JS vanilla simples dentro do próprio artefato, sem depender de nada externo).

### 📰 Notícias do Dia (renomeado de "Ao Redor"/"Mundo")

Três abas:

1. **Mundo** — 3-5 manchetes globais + link "saiba mais" (aponta pra fonte/agregador usado naquela rodada), inclui também destaques sem ligação direta com Brasil/Espanha (pílula de conhecimento)
2. **Espanha / Barcelona** — 2-4 manchetes locais + "saiba mais" (fonte usada naquela rodada)
3. **Brasil** — 2-4 manchetes (esse tab tinha sumido do escopo ao longo das edições anteriores — restaurado aqui de propósito, fazia parte do design original) + **"saiba mais" sempre aponta pro [g1.com.br](http://g1.com.br)** (regra fixa, não varia)

Cada manchete: **o título em si é um link clicável pra matéria original** (não só texto estático), + uma frase de contexto, curto.

### 🎭 Eventos

Três abas:

1. **Local (Barcelona)** — cobertura ampla, não só o que Fever/Ticketmaster capturam: inclui estreia de filme que ela provavelmente vai gostar (baseado no [Perfil de Entretenimento](https://app.notion.com/p/Perfil-de-Entretenimento-Filmes-S-ries-Jogos-M-sica-3af107b19b4981848caee3cfed043b2c?pvs=21) — sem terror de susto/sobrenatural), teatro, musicais em cartaz, shows, festivais. Fontes: Fever + Ticketmaster (conector) + busca na web (pra cobrir cinema/teatro que os conectores não pegam), incluindo sempre checar: [Eventbrite Espanha](https://www.eventbrite.es/ttd/spain/), [Guia BCN](https://guia.barcelona.cat/es/), [entradas.com Barcelona](https://www.entradas.com/city/barcelona-371/), [Ticketmaster.es Barcelona](https://www.ticketmaster.es/discover/barcelona), [Planes en Barcelona](https://linktr.ee/planesenbarcelona) (agregador semanal de eventos, festas, rotas gastronômicas e descontos pra residentes — fonte de ideias, sempre confirmar data/preço no site oficial; adicionada em 28/10 a pedido da Odara) e a newsletter **Barcelona Expat Daily** (chega no Gmail da Odara, remetente `hello@barcelona.expat-daily.com`; foco em expats — avisos práticos como greves e alertas, além de eventos; ler na varredura do Gmail, buscar por `from:hello@barcelona.expat-daily.com`, e usar pra Eventos > Local e pra avisos de dia)
2. **Games** (novo) — lançamentos de jogos ou semanas de desconto relevantes, baseado nos gêneros/títulos favoritos dela no [Perfil de Entretenimento](https://app.notion.com/p/Perfil-de-Entretenimento-Filmes-S-ries-Jogos-M-sica-3af107b19b4981848caee3cfed043b2c?pvs=21) (roguelike/roguelite, ARPG de farm, builder com ação — referências diretas: Dave the Diver, Terraria, Slay the Spire, Diablo 4, Ravens Watch). Inclui DLC novo, sequência, ou desconto forte em algo da lista de favoritos/gêneros amados. Sem FPS/mira precisa (bloqueador dela). Fonte: busca na web (não tem conector dedicado de games/Steam ainda).
3. **Europa** — mais filtrado, só coisas que valeriam um deslocamento:
    - Cidades com **conexão fácil** a partir de Barcelona (ou de onde ela estiver no momento) — ex: Madri, Paris, Londres, Amsterdã, sem lista fixa
    - OU em qualquer lugar, se for algo da lista de **"Favoritos que valem viagem mais longa"** — ver [Perfil de Entretenimento](https://app.notion.com/p/Perfil-de-Entretenimento-Filmes-S-ries-Jogos-M-sica-3af107b19b4981848caee3cfed043b2c?pvs=21), seção Música. Lista começa com Nightwish, Epica, Kamelot (bandas formativas dela) e cresce aos poucos conforme ela confirmar outros nomes/festivais/estilos

### 📨 Correspondência (restaurado, 2026-09-03)

Terceiro bloco do jornal (Odyssey Gazette), no `.journal`, **entre Eventos e as Poções** — mesmo estilo visual dos outros dois blocos (fundo pergaminho, título Cinzel, `rule-double`). Retoma o antigo Morning Message Sweep (que existia antes do artefato virar HTML) — agora dentro da página em vez de texto solto no chat.

- Varre e-mails não lidos da caixa de entrada logo na geração.
- **Newsletters/promoções conhecidas** (Wetaca, Timeleft, HousingAnywhere, Amazon "sugestões", SHEIN, etc.): arquivadas automaticamente + rotuladas com a label Gmail **Newsletters** — não aparecem individualmente na página, só um resumo tipo "12 newsletters arquivadas hoje".
- **Itens que precisam de atenção real** (confirmações de compromisso tipo AEAT/Cl@ve, alertas de segurança/phishing tipo Revolut, pacotes chegando, threads administrativas importantes): listados individualmente, cada um com uma frase de contexto curta + link direto pro e-mail quando possível — mesmo espírito "bater o olho e entender" do resto da página.
- **Threads sensíveis/administrativas** (ex: processos em andamento tipo o do PATNASCIEF): nunca resolvidas ou resumidas em detalhe aqui — só sinalizadas como "tem novidade, dá uma olhada", mesma regra de sempre.
- **Sem tracking** de quantos e-mails ela abre, ignora ou demora pra responder — só o resumo do dia, sem virar métrica.
- Estrutura HTML: mesmo padrão `.journal-block` dos outros dois, com `.j-news-item`-like rows (remetente + assunto curto + ação sugerida). Não precisa de abas (differente de Notícias/Eventos) — lista única.

### ⏰ Regra de frequência de exibição (nova, 2026-08-24)

Problema identificado: sem essa regra, um evento tipo "30/08" aparecia **todo santo dia** da semana anterior até a data — cansativo. Duas lógicas diferentes, dependendo do tipo de evento:

- **Evento comum** (não está na lista de Favoritos): só aparece se estiver acontecendo **dentro dos próximos 3-4 dias**. Fora dessa janela, nem mostra ainda — evita popular a página com coisa longe demais pra ser relevante hoje.
- **Evento tier Favoritos** (nomes da lista em Perfil de Entretenimento, tipo os que precisam de planejamento com antecedência — viagem, ingresso cedo, etc.): aparece **uma vez quando descoberto** (pra ela saber que existe), depois fica quieto, e **só resurge em dois momentos**: por volta de **~2 semanas antes** (lembrete de planejamento) e de novo **~3 dias antes** (lembrete final) — nunca todo dia no meio disso.

### 🚫 Eventos Dispensados (nova, 2026-08-24)

Se ela disser algo tipo "remove isso"/"não quero ver esse evento de novo" em qualquer chat (principalmente no Bom Dia Claude), o Claude adiciona o nome do evento + data nessa lista abaixo. **Antes de incluir qualquer evento na página, sempre checar essa lista primeiro** — se bater (mesmo nome/data), pula esse evento, independente da janela de datas acima.

**Lista atual:**

- *(vazia por enquanto — adicionar aqui conforme ela pedir pra remover algo)*

### 📚 Aprendizado sem vigilância

Mesma filosofia do motor de Side Quests (ver Playbook): **sem tracking silencioso** de o que ela ignora ou aceita nessas seções. Padrões reais observados ao longo do tempo são trazidos em conversa (Recap Session) pra ela validar — nunca usados pra ajustar filtro sozinho, sem ela saber.

## 🔗 Regra geral de links

**Sempre que fizer sentido e for fácil, colocar link direto** — pra ela conseguir fazer follow-up em qualquer sessão sem precisar pedir. Vale pra todo o artefato: eventos, notícias, apps, o que for. Não deixar texto "pelado" quando existe uma URL óbvia associada.

## 🚫 O que essa rotina NÃO faz

- Não vira uma sessão de notícias aprofundada por padrão — só se ela pedir explicitamente
- Não substitui o Ad Hoc Check-in (Cadence Queue completa + Wildcard)
- Não envia e-mail sem confirmação (regra padrão do Morning Message Sweep)
- A Mini Side Quest nunca vira Obligation nem entra no Backlog — perderia a graça

## 🛡️ Resiliência (falha parcial não trava tudo)

**Regra geral:** cada bloco de dado (Google Calendar, Spotify, Ticketmaster, notícias) é independente. Se um falhar, os outros continuam normalmente — nunca travar a geração inteira por causa de uma fonte.

**Como marcar falha:** o bloco que falhou aparece com uma linha discreta no mesmo estilo visual da página (ex: *"🪨 Não consegui buscar isso agora"*, em itálico, tom neutro — nunca pedaço de erro técnico cru, nunca mensagem de pânico). Backlog (Notion) e busca na web são a espinha dorsal e não devem falhar silenciosamente — se algum desses falhar, vale destacar mais, já que é mais sério.

**Botão de retry:** discreto, canto do artefato, label tipo "↻ Tentar de novo". Como um HTML estático não consegue re-executar Claude sozinho, o botão é um **link** pro formato `https://claude.ai/new?q={seed com o pedido de regenerar o brief}&surface=cowork&composer=mini` — mesma técnica que o skill "morning" genérico já usa pros próprios botões dele. Isso abre uma sessão nova que gera um artefato novo (não atualiza o antigo no lugar, mas é um clique só).

## ✅ Histórico de resolução (2026-08-22 a 2026-08-26)

A Scheduled Task chegou a invocar o skill genérico "morning" do Claude em vez do formato Odyssey. Corrigido reescrevendo o prompt da task pra nunca mencionar "morning skill" e apontar direto pra esta página + o Template de Referência acima.

## ⚙️ Automação (rodar sozinha às 11h Barcelona)

**Já configurada** via Claude Cowork Scheduled Tasks ("Bom dia Claude", todo dia às 11h30, roda na nuvem). Prompt da task deve incluir lógica de fallback por bloco, pra um conector falho não quebrar a rotina inteira:

- **Backlog/Notion** — sempre deve funcionar, é a espinha dorsal, nunca pula
- **Busca na web** (notícias, e Ticketmaster se der erro) — geralmente disponível em qualquer contexto
- **Google Calendar / Spotify / Ticketmaster** — se não conectar na nuvem, pula esse bloco silenciosamente (sem erro visível) em vez de travar a geração inteira

**Modo reduzido aceitável:** se testes mostrarem que Calendar/Spotify/Ticketmaster não funcionam de forma confiável via Scheduled Task, a versão automática roda só com Backlog + Awareness (sempre firme), e ela complementa manualmente aqui ou no chat dedicado quando quiser as partes que dependem de conector ao vivo. Preferível a um sistema que quebra tentando ser 100% automático.

**Próximo passo:** rodar manualmente uma vez (botão de execução manual na task) pra ver o que realmente retorna antes de confiar 100% na versão agendada.

## 🧪 Seção Poções (ações rápidas/macros, nova 2026-09-01)

Seção final da página — batizada de **"Poções"** (não "Ataque Rápido"). **Antes de gerar os botões, sempre consultar o banco [Registro de Ações Rápidas](https://app.notion.com/p/e07163015bd3472f943aa2ef3f0bc815?pvs=21) e usar exatamente os itens com Status = Ativo de lá — nunca inventar botões novos por conta própria.** Cada botão dispara uma automação real via link `claude.ai/new`, usando o "Prompt de disparo" já escrito em cada linha do banco. Conceito visual ainda pendente do Chatty (prompt já enviado — uma das ideias sugeridas foi prateleira de frascos/poções, que bate exatamente com o nome escolhido).

## 📐 Passada de composição (2026-09-03) — fase 1 do prompt do Claude Code

Seguindo o prompt ("corrigir composição antes de mais decoração"), fiz só layout/espaçamento/agrupamento, nada de novos assets:

- Fundo atmosférico sutil (radial-gradients vinho/veludo/mar) em vez de preto chapado
- "Seu Dia em Foco" virou um painel de verdade (fundo levemente diferenciado + borda + label), agrupando Flo/Hoje/Word/Soundtrack/Quest como um bloco coérente em vez de cards soltos
- Mini cards reduzidos (190x260→180x225) pra cortar espaço vazio excessivo em cards só-texto
- Header/clima com respiro mais enxuto

Autovalidado via screenshot renderizado (Playwright), não só no código. Próximas fases (só depois que ela aprovar essa), na ordem do próprio prompt: backgrounds tematizados, ilustrações por carta, estilo Gazette (pergaminho), visual das poções (já adiantado), decoração final, animação/interação física.

## 🔍 Observação sobre o log de execução real (2026-09-03)

Odara mandou prints do log de ferramentas do run de hoje. Confirma bastante coisa útil:

- O run realmente faz várias buscas/fetches de notícias em paralelo (Barcelona, mundo, Espanha) e 3 fetches diretos falharam (La Vanguardia, El Periódico, AP News — provável bloqueio 403). **Não quebrou o resultado final** — ele buscou outras fontes (Euronews etc.) e entregou 3 notícias reais. Resiliência funcionando como documentado, não é bug.
- Confirma de novo que os nomes/rótulos das mini cards mudam a cada run (hoje: Ciclo/Agenda/Espanhol/Soundtrack/Mini Missão, com labels em português, diferente do template em inglês) — reforça o diagnóstico já registrado de que a geração reinventa conteúdo a cada dia em vez de seguir um template fixo.

## 🚨 Incidente 2026-09-03 — "não consigo flippar a carta"

**Diagnóstico**: testei o clique programaticamente no arquivo real que rodou hoje (`bom-dia-0903.html`) — funciona mecanicamente (flip + reveal + dados corretos). Hipótese principal: ela pode estar tocando no **PNG estático** (screenshot enviado junto) em vez do **HTML interativo** — os dois chegam juntos via SendUserFile, e o PNG não responde a toque nenhum por ser só imagem. Aguardando confirmação dela.

**Bug real encontrado e corrigido** (independente da hipótese acima): a carta fechada nascia com dimensões invertidas (330x230 paisagem, só corrigia pra 230x330 retrato DEPOIS do flip) — isso fazia a carta fechada parecer um banner largo, não uma carta de tarot, o que sozinho já podia desencorajar o toque.

**Correções aplicadas no arquivo de hoje**:

- Dimensões do card fechado corrigidas (sempre retrato)
- Bind de clique robustecido (`click` + `touchend`, com `preventDefault`)
- Link de escape "não consigo virar a carta · pular" adicionado — nunca mais fica travada, seja qual for a causa

**⚠️ Isso só conserta o arquivo de HOJE.** A rotina agendada continua gerando do zero a cada dia (não lê nosso template com confiabilidade — problema já registrado antes). Sem resolver o acesso de escrita no GitHub, esse mesmo bug (ou outro parecido) pode voltar amanhã. Acão pendente continua sendo a mesma: liberar escrita no GitHub pro Claude Code sincronizar o template corrigido como fonte real.

## 🎨 Comparação com mockup do Chatty + ajustes de maior impacto (2026-09-03)

Chatty mandou um mockup completo (4 temas lado a lado) com direcionamento claro: preservar arquitetura, só ajustar visualmente pro que tiver mais impacto. Comparação:

**Já alinhados** (não precisou mexer): mobile-first, hierarquia geral (Carta → mini cards → Gazette → Poções), paleta escura+dourada, tom "objeto mágico".

**Implementado nessa rodada** (os 2 de maior impacto visível):

- **Carta do Dia com muito mais presença**: aumentei o card (220→250px), moldura dupla de verdade (anel dourado + gap + borda, como no mockup), label "CARTA DO DIA" com estrelinhas ladeando, dentro do próprio card (antes ficava só como título solto acima)
- **Poções com as garrafinhas de verdade**: troquei os botões de texto por 4 dos ícones reais do Chatty (Inbox Sweep, Agenda Check, Tasks Scroll, Notes Ink), extraídos com transparência real da prancha de assets. O 5º botão (Check-in Completo) não tinha garrafinha equivalente, mantém estilo pill

**Identificado mas NÃO implementado ainda** (mudança maior, fica pra discutir/agendar):

- O mockup mostra "Odyssey Gazette" como card único estilo pergaminho/editorial (fundo claro, texto escuro, uma matéria com imagem) — bem diferente do nosso bloco atual de abas Notícias/Eventos em fundo escuro. Upgrade real, mas mexe na estrutura de conteúdo, não só estilo.
- "Seu Dia em Foco" no mockup é uma grade compacta de ícones (Ciclo, Som, Palavra, Sorte, Tarefas, Notícias, Eventos) em vez das mini cards com flip que temos hoje — é uma mudança de interação, não só visual, então não mexi.
- Barra inferior fixa (Hoje/Diário/Mapa/Porto) é conceito de navegação multi-página — não se aplica ao nosso modelo de artefato HTML estático gerado por dia; fica como referência conceitual, não implementável do jeito que o sistema funciona hoje.

## 🔍 Nota importante sobre visualização (2026-09-03)

O arquivo HTML abre direto na **splash screen** (só a carta fechada) — as mini cards (Flo, Hoje com o navio, etc.) só aparecem depois de **clicar na carta pra virar**. Se abrir o arquivo e não ver nada além da carta, isso é esperado, não bug — só falta o clique. Rendericei via Playwright pra confirmar visualmente que o navio e o amuleto aparecem certinho, e ajustei: navio (opacity .24→.4, tamanho 150→220px) e amuleto (52→78px + geometria redesenhada pra não parecer bonequinho).

## ✅ Artes do Chatty recebidas e plugadas (2026-09-03)

Chegaram 3 pranchas do Chatty: (1) Ícones/poções/cartas/emblema Gazette, (2) o navio dourado em alta resolução + mockup do card "Hoje" nos 4 temas, (3) prancha completa de background/molduras/selos/objetos por tema.

**Já implementado no template v5:**

- **Navio dourado**: a imagem do Chatty já veio com transparência real (não precisou de tratamento extra) — recortei, otimizei pra WebP (~35KB) e embuti como base64 direto no HTML, marca d'água sutil (opacity .24) no canto do card "Hoje".
- **Amuleto do Flo**: virou SVG puro de verdade (lua crescente + olho + conchas + correntinha, dourado/rosa, sem figura literal) — esse nunca dependeu de arte do Chatty, só estava faltando escrever o código.

**Ainda não plugado (fica pra próxima rodada, não bloqueia nada):**

- Prancha 2 mostra o mockup real do card "Hoje" aplicado nos 4 temas com moldura/canto/textura próprios de cada um — minha implementação atual dos temas só troca cor de fundo/acento, não replica ainda a moldura/textura de cada tema. Upgrade visível disponível se quiser ir mais fundo depois.
- Os ícones das 7 Poções (garrafinhas lindas na prancha 1) ainda não substituíram os botões de texto simples atuais.
- Selos/carimbos (Intuição Ativa, Rumo Alinhado, etc. na prancha 3) — possível uso futuro em badges de conquista/marco.

## ✅ Sessão de correção 2026-09-03 — Template v5 (rodada 2)

Mais 3 correções, todas já no arquivo entregue:

- **Sistema de 4 Temas implementado de verdade** — puxei os hex codes reais do Registro de Temas (todos já preenchidos, não precisava de imagem nenhuma) e criei os 4 blocos `body[data-theme="..."]` + sorteio aleatório na carga da página, entre os 4 (todos Status=Ativo). **Correção do meu próprio diagnóstico anterior**: eu tinha marcado isso como bloqueado por falta de arte do Chatty — estava errado, só faltava código.
- Ajuste mobile na carta de abertura (`#cScene`), que não tinha breakpoint próprio
- Datas hardcoded (`02/09/2026`) trocadas por placeholder `[DD/MM/AAAA]` no título da página e no JS de feedback, já que o arquivo virou template reutilizável

**Ainda pendente de verdade (agora só isso 2 coisas)**:

- Ilustrações do navio + amuleto (imagens, essas sim precisam do Chatty)
- Campos de imagem nos bancos (crio quando as imagens chegarem)

## 🚧 Ação pendente da Odara (2026-09-03)

**GitHub sem permissão de escrita.** Tentei subir o template corrigido (v5) pro repositório `odarambmenezes/odyssey` e recebi 403 (token só leitura). Preciso que você libere escrita nesse conector, ou eu sigo entregando as versões como arquivo direto no chat (funciona, só não fica sincronizado automaticamente).

## ✅ Sessão de correção 2026-09-03 — Template v5

**Mudança de abordagem**: em vez de reconstruir a página a partir da descrição em texto (causa raiz de vários desvios), passamos a usar o **artefato HTML que rodou de verdade em 02/09** como base real, corrigindo bugs em cima dele.

Corrigido nessa sessão:

- Delay do cascade das mini cards: 150ms → 90ms (valor correto documentado)
- Medalhão do divisor: era só texto solto "· · · ✦ · · ·", agora é um círculo dourado de verdade sobre uma linha
- Splash screen: implementada do zero (não existia) — carta em tela cheia (`#introStage`) → ao virar, clona a frente pro `#restingCardSlot` no topo da página → esconde a splash → revela o resto
- Drag-and-drop nas mini cards: implementado do zero (não existia) — Pointer Events, threshold de 5px pra distinguir clique de arrasto, troca de posição no DOM ao soltar
- Correspondeência: virou um bloco de verdade (`#sMail`) com dados reais do dia, entre Eventos e Feedback/Poções — não só um botão-link

Ainda pendente (bloqueado por falta de arte, não por código):

- Sistema de 4 Temas (Registro de Temas) — aguardando mockups do Chatty antes de implementar a troca
- Ilustrações do navio + amuleto — aguardando arquivos do Chatty
- Campos de imagem nos bancos Registro de Temas / Registro de Cartas — vou criar assim que as imagens chegarem, pra não criar campo vazio sem uso

**Achado importante**: os bancos Registro de Cartas / Ações Rápidas / Temas nunca são de fato consultados pela rotina agendada hoje — as mini cards e Poções estão hardcoded no HTML. O sistema "extensível por banco" é aspiracional ainda, não real. Fica registrado como dívida técnica pra revisar depois que a base visual estiver estável.

## 📊 Status

Redesenhada em 2026-08-22 a 2026-09-01 (design completo: mesa de tarot, Carta do Dia, sistema de widgets independentes). **Já rodou com sucesso** tanto manualmente quanto via Scheduled Task — desvio da página 26/08 foi corrigido (era contradição na própria documentação do Notion, não bug de geração). Desvio 2 (02/09) também corrigido — Template de Referência estava desatualizado, agora na v4. Próximo passo: rodar de novo com o template atualizado e confirmar que bate com o protótipo aprovado.

[[ARCHIVE] Bom Dia Claude — Experience Spec v0.1 (Aprovado 28/09/2026)](%5BARCHIVE%5D%20Bom%20Dia%20Claude%20(Rotina%20Matinal%20Completa)/%5BARCHIVE%5D%20Bom%20Dia%20Claude%20%E2%80%94%20Experience%20Spec%20v0%201%20(A%203e9107b19b4981c1b079c0241c174426.md)

---

- 📥 Personal data used by this routine · moved from the Player / Character Sheet, 2026-11-04
    
    <aside>
    📦
    
    Moved word for word. To be reviewed when we reach this page. Sensitive data: it stays inside Odyssey and is used only by the routine it serves.
    
    </aside>
    
    **✨ Dados Pessoais**
    
    - **Nascimento:** 21/06/1991, 20h, Rio de Janeiro
    - **Signo solar:** Câncer (o Sol entrou em Câncer às 18h25 horário do Rio naquele dia — ela nasceu ~1h35 depois, então é Câncer bem cedinho no grau)
    - Usado pro "Frase do Dia" da rotina Bom Dia Claude — mistura de horóscopo real com invenção livre
    
    **🥺 Ciclo (Flo)**
    
    - **Último ciclo registrado:** início 15/08/2026, duração do período ~5 dias
    - **Duração média do ciclo:** ~29-31 dias (baseado no histórico do app Flo, jan-ago 2026)
    - Usado pro **Flo Status** da rotina Bom Dia Claude — calculado a partir dessa data, apresentado como fase (folicular/ovulatória/lútea/menstrual) em uma frase curta, nunca em tom clínico ou de diagnóstico
    - **Odara deve atualizar a data de início sempre que um novo ciclo começar**, pra manter o cálculo certo — senão o Claude vai estimar com base na média, que pode ir desalinhando com o tempo
    - Dado sensível: fica só aqui e só é usado nessa seção específica, nunca mencionado fora de contexto
    
    **🎭 Mood Vocabulary**
    
    Initial list (more to come):
    
    - **Borocochô** — low motivation, sluggish, messy/unmotivated state
    - **Animada** — energized, up for more
    - **Modo exploratório** — wants to discover/try something new
    - **Modo compra** — shopping mode
    - **Modo relax** — wants to unwind, low-key

## Rules of this routine

These rules apply to Bom Dia Claude and to any check-in. The rules for the whole Crew are in [Game Design](%5BARCHIVE%5D%20Game%20Design%20413107b19b49819897a5d525d14a093c.md); the Side Quest recipe and engine are in [Side Quest On-Demand](https://app.notion.com/p/Side-Quest-On-Demand-Rotina-R-pida-3af107b19b4981db9741f76170308953?pvs=21).

**Mood only when she offers it (G5).** The AI doesn't ask "how are you feeling?" as a default step at every check-in. When she does share it, respond immediately and adapt the mix. The Mood Vocabulary is in the personal data section of this page.

**Proportional flourish (G7).** A routine daily check-in doesn't need paragraphs of narration. Save narrative weight for Main Quest beats, Boss moments and milestones. For tone by type (quests narrative, obligations direct), see Tone Preferences in the Player / Character Sheet.

**Flavor Layer (optional, toggleable).** Flavor is the tone of narration only (for example "give this week a gothic or vampire vibe"). It never changes mechanics (Cadence Queue, Wildcard, Mood), never introduces a fictional setting, and never requires remembering lore. Switched on by request, switched off by request. No persistence across sessions unless she asks. Default, with no Flavor requested: plain, warm, grounded narration rooted in her actual life.