# Bom Dia Claude (Rotina Matinal Completa)

> Rotina matinal completa, disparada quando ela diz "bom dia"/"oi" no chat dedicado **"Bom dia Claude"**. Entregue como **artefato HTML** (um "diário de bordo" visual), não texto puro de chat.
>
> **Mirror of Notion.** Source of truth: https://app.notion.com/p/3af107b19b49811eab20ef076172f85d — manual backup, may be stale.
>
> Last synced from Notion: 2026-09-01

## 🎯 Objetivo

Ela abre um chat só, uma vez de manhã, e sai sabendo tudo que precisa — mas também sente um pouco de surpresa/diversão no processo, não só informação seca. Uma "pitada de caos" pedida por ela.

## 🎨 Identidade Visual (design tokens — versão 2, 2026-08-23)

Direção: **mesa de tarot mística**, fundo quase preto, dourado em linework fino, blocos de conteúdo como "cartinhas pousadas na mesa".

- **Paleta:** fundo quase preto `#100D0B`, ouro velho `#C9A227`, vinho `#6B1F2A`, veludo `#3B1F3D`, mar profundo `#16303B`, pergaminho `#E8DCC3` (texto principal sobre fundo escuro)
- **Tipografia:** Cinzel (títulos/display) + Cormorant Garamond itálico (frases/citações) + Karla (corpo) + IBM Plex Mono (labels/datas)
- **Cabeçalho**: card de saudação escuro no topo ("Bom dia, Odara", bússola + selo dourado, tagline fixa "Colecione experiências. Escreva sua lenda."), seguido de uma linha discreta de clima+data (`BARCELONA · 23°C / 29°C ☀️ · DOMINGO, 23/08` — **nunca coordenadas geográficas**), depois o título "Odyssey / A Carta do Dia"
- **Títulos de seção**: formato "TÍTULO ···········" (linha tracejada dourada) — **sem numeração**
- **Blocos de conteúdo** ("table-cards"): cada bloco é uma cartinha independente com moldura dourada dupla, levemente inclinada (rotação `-0.6°` a `0.5°`), cor alternando entre vinho/veludo/mar profundo — **sempre cores diferentes entre cards vizinhos na mesma linha**
- **Ilustrações**: navio dourado (marca d'água no card "Hoje") e **amuleto simbólico em SVG puro** no card do Flo (lua crescente + olho + conchas + correntinha — **nunca uma figura de mulher/cigana literal**, por diretriz do sistema de design)
- **Mobile-first, sempre.**

## 🃏 A Carta do Dia (substitui "Frase do Dia" — não coexistem, não duplicar)

Em vez de só mostrar uma frase, ela **tira uma carta** todo dia.

- **Fica fechada por padrão** (verso escuro, verde+dourado, linework de lua/**estrelas de 4 pontas** — nunca bolinhas simples, texto "toque para tirar sua carta") — **só revela quando ela clica**, com animação de virar em 3D (CSS `rotateY`, `transform-style:preserve-3d`)
- **Frente revelada**: fundo gradiente quente (âmbar→laranja→vinho→escuro), número romano, símbolo em linework dourado, nome da carta, significado/frase do dia
- **Baralho próprio do Odyssey** (não tarot genérico): O Corsário, A Cigana, A Bússola, A Maré, O Tesouro, A Taverna, O Mapa Aberto, A Lua, O Sol, A Âncora, A Estrela-Guia, O Grimório, O Espelho, As Chaves
- **Conecta com o motor de Side Quests**: quando a carta tiver ligação com holofote de Main Quest, mostra uma linha extra "↳ hoje o holofote cai sobre: [Main Quest]"
- **Sem tom clínico/preditivo real** — biscoito da sorte com identidade, não horóscopo de verdade

## ⚠️ Bug conhecido: onclick inline bloqueado pela CSP do iframe

Handlers `onclick="..."` inline são **bloqueados silenciosamente** quando o artefato roda dentro do iframe da conversa (não publicado como URL própria). Regra fixa: **nunca usar onclick inline em nada** — sempre `id`/`data-*` + `addEventListener` no `<script>`. Exemplo:

```javascript
// ERRADO (bloqueado pela CSP no iframe):
// <div onclick="flipCard()">...</div>

// CERTO:
document.getElementById('cardScene').addEventListener('click', function(){
  document.getElementById('cardFlip').style.transform = 'rotateY(180deg)';
});
```

## 🔁 Trigger

Ela diz "bom dia" ou "oi" dentro do chat **"Bom dia Claude"**.

## 📋 Ordem exata da página (sem duplicar nada)

**⚠️ Não reintroduzir**: um "banner ilustrado ODYSSEY/Daily Summary" (gradiente com ondas) ou uma "Frase do Dia em 2 colunas" separada — ambos foram descartados em favor da Carta do Dia.

1. Card de saudação escuro
2. Linha de clima+data
3. Título "Odyssey / A Carta do Dia"
4. A carta em si (flip 3D) — a única "frase do dia"
5. Flo + Hoje lado a lado
6. Word of the Day + Soundtrack lado a lado
7. Mini Side Quest

### Flo (🩸)

Card lado a lado com Hoje. (a) quantos dias faltam pra menstruação, só mostrado se **dentro de 5 dias antes**; (b) sintomas rápidos, direto, sem foco em nome de fase. Fora da janela: mensagem leve tipo "ciclo tranquilo, nada previsto ainda" (variando a frase). Link pro app Flo direto no título: `https://apps.apple.com/es/app/mi-calendario-menstrual-flo/id1038369065`.

**Confirmação de período:** quando a data prevista chegar/passar sem confirmação, o card Flo vira uma pergunta divertida no tom diário-de-bordo (ex: *"Blood Moon Started? (Day 1)"*), nunca listando várias opções juntas. Botão "🩸 Register" com o mesmo link do app. Quando ela confirmar em qualquer chat, atualizar o início do ciclo na Player/Character Sheet e passar a contar "Dia X do período" nos dias seguintes.

### Word of the Day (esquerda) + Soundtrack (direita)

- **Word of the Day**: palavras/expressões úteis, majoritariamente espanhol, catalão com menos frequência. Botão "🔄" cicla opções pré-geradas no navegador (JS puro).
- **Soundtrack** (nome fixo — nunca "Trilha do Dia"): skew pra energia de acordar, não dramático/balada. Puxa do perfil musical dela. Nome + botão "Play", sem descrição extra.

### Mini Side Quest

Pode trazer uma imagem opcional, só se ajudar a visualizar a quest de verdade — nunca só decoração, nunca espaço vazio reservado.

## 📋 Tasks & Obligations

**Abas: Hoje / Semana / Mês**

- **Hoje**: tudo que vence hoje ou já venceu, **independente de Rigidez** — ela decide se posterga.
- **Semana**: semana atual (segunda a domingo).
- **Mês**: janela mais ampla, principalmente Flexíveis.

Ordenado por Rigidez primeiro (🔺 Rígido no topo), depois Flexível, por data dentro de cada grupo.

**Calendar Check**: lista única (`<ul><li>`), sem abas.
- **Fortis Early Meeting** sempre primeiro bullet, só se houver reunião antes das 16h Barcelona time, linkado ao evento real (`htmlLink`, funciona mesmo em modo busy/free).
- Eventos pessoais (`odarambmenezes@gmail.com` + `tacomigoencomendas@gmail.com`) em seguida.
- Lista vazia → frase divertida variada (ex: "Mar calmo hoje, capitã — nenhum compromisso à vista no horizonte"), nunca texto literal "nada marcado".

**Próximos feriados** (15 dias): só Barcelona/Espanha. Bloco só aparece se tiver algo real.

Cada item tem checkbox "✓ já fiz". Título linka pra página Notion **só se ela tiver conteúdo real** (não linkar páginas vazias).

**Autoridade de escrita**: só atualiza Backlog mediante confirmação dela na conversa (ver Codex, Completion Protocol).

## 📤 Feedback Acumulado

Toggle/colapsável (`<details>`/`<summary>`), fechado por padrão.

Limitação técnica real: HTML estático não fala com Claude em segundo plano. Solução: checkboxes + campo de texto livre + botão "Enviar atualizações" que monta um resumo e abre `https://claude.ai/new?q={resumo}&surface=cowork&composer=mini` (abre uma conversa NOVA, não a mesma thread — mas o seed identifica o contexto). **A data de geração vai embutida no resumo**, essencial pro cálculo de recorrência.

Eventos ganham botão "+ favorito" com o mesmo mecanismo.

## 📋 Awareness

Abas clicáveis, JS vanilla, sem dependências externas.

### 📰 Notícias do Dia

Três abas: **Mundo** (3-5 manchetes + "saiba mais"), **Espanha/Barcelona** (2-4 manchetes), **Brasil** (2-4 manchetes, **"saiba mais" sempre pro g1.com.br**). Título de cada manchete é link clicável pra matéria original.

### 🎭 Eventos

Três abas:
1. **Local (Barcelona)** — cobertura ampla (filme, teatro, musicais, shows, festivais). Fontes: Fever + Ticketmaster + busca na web + sempre checar Eventbrite Espanha, Guia BCN, entradas.com, Ticketmaster.es.
2. **Games** — lançamentos/descontos baseados no perfil de jogos dela (roguelike/roguelite, ARPG, builder — Dave the Diver, Terraria, Slay the Spire, Diablo 4, Ravens Watch). Sem FPS/mira precisa.
3. **Europa** — só cidades de conexão fácil (Madri, Paris, Londres, Amsterdã) OU itens da lista "Favoritos que valem viagem mais longa" (Perfil de Entretenimento, seção Música).

**Regra de frequência**: evento comum só aparece dentro de 3-4 dias do acontecimento. Evento tier Favoritos aparece uma vez quando descoberto, some, resurge ~2 semanas antes e ~3 dias antes.

**Eventos Dispensados**: se ela disser "remove isso", adicionar nome+data numa lista de exclusão, checada antes de incluir qualquer evento.

**Aprendizado sem vigilância**: sem tracking silencioso de padrões de aceitação — só trazidos em conversa (Recap Session) pra ela validar.

## 🔗 Regra geral de links

Sempre que fizer sentido, colocar link direto — pra ela poder fazer follow-up sem pedir.

## 🚫 O que essa rotina NÃO faz

- Não vira sessão de notícias aprofundada por padrão
- Não substitui o Ad Hoc Check-in
- Não envia e-mail sem confirmação
- Mini Side Quest nunca vira Obligation

## 🛡️ Resiliência

Cada bloco de dado é independente — falha de um não trava os outros. Falha aparece como linha discreta no estilo da página (ex: "🪨 Não consegui buscar isso agora"), nunca erro técnico cru. Backlog e busca na web são a espinha dorsal, não devem falhar silenciosamente.

**Botão de retry**: link pra `https://claude.ai/new?q={seed}&surface=cowork&composer=mini` (abre sessão nova, não atualiza o artefato antigo no lugar).

## ⚙️ Automação

Via Claude Cowork Scheduled Tasks, todo dia às 11h30, roda na nuvem. Fallback por bloco:
- **Backlog/Notion** e **busca na web** — nunca pulam.
- **Google Calendar / Spotify / Ticketmaster** — se não conectar, pulam silenciosamente.

**Modo reduzido aceitável**: se os conectores ao vivo não funcionarem de forma confiável via Scheduled Task, a versão automática roda só com Backlog + Awareness, e ela complementa manualmente quando quiser o resto.

## 📊 Status

Redesenhada 2026-08-22 até 2026-08-30 (visual completo, Carta do Dia, ilustrações, interatividade). Prompt da Scheduled Task não deve invocar o skill genérico "morning" — deve ler esta página (e o template de referência completo, que vive apenas no Notion por ora — este arquivo é um resumo funcional, não pixel-perfeito).
