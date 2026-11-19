---
name: command-center-versions
description: URL do Artifact do Command Center + vocabulário de "blocos", roster da AI Crew, arquitetura de dados, decisões técnicas e pendências
sources: [chat]
---

## Versão Live (única URL — todo republish é em cima dela)

**URL:** https://claude.ai/artifact/6N4uHqSf4wMghTXE5YjSc9

Versão atual: **v19** (2026-09-26) — Treasure Chest ganhou City Radar/Local Lens e The Ticket como capabilities próprias, mantendo a mesma arquitetura de dados da v18.

---

## Snapshots congelados

### v18 — 2026-09-26
**URL:** https://claude.ai/artifact/CbgVNcREnuWSB3gQUvgHJ7

Snapshot congelado antes de iniciar a evolução do Command Center pedida no brief "Full Project Re-Context" (26/09). Cópia exata do HTML + avatares da v18 (Lorekeeper corrigido, arquitetura data/render em camadas, Treasure Chest com 7 itens, Radar data-driven).

### v16 — 2026-09-25
**URL:** https://claude.ai/artifact/D2zGLhH82Lrnop6up5HDM3

Snapshot retroativo (feito só na virada pra v17, porque a mudança de avatares não tinha sido congelada antes). Cópia do HTML da v16: primeira versão com os 9 avatares reais da AI Crew (arte enviada pelo ChatGPT via brief "Avatar Asset Implementation", 2026-09-25), mas ainda com a Prateleira de Poções antiga, Radar/AI Crew hardcoded no HTML/JS (sem separação de dados), e o nome errado "Logkeeper".

### v15 — 2026-09-24
**URL:** https://claude.ai/artifact/3Aw5QdFTgxDMuHgZhNMAwV

Cópia exata do HTML da versão live no momento do snapshot: mapa das ilhas com popup rico, Diário de Bordo das Rotinas, AI Crew em Medalhão com o roster antigo pré-reconciliação (emoji, sem avatar real), Prateleira de Poções com 10 atalhos, chip "30 amanheceres registrados" hardcoded.

**Regra:** nunca publicar em cima de nenhum desses URLs. Só abrir pra ler/copiar se a versão live quebrar.

---

## Como fazer rollback

1. Abrir o snapshot URL acima
2. Copiar o HTML completo (+ pasta `avatars/` se aplicável)
3. Colar num novo chat e pedir pra republicar na versão live

**Regra permanente**: sempre que uma mudança estrutural relevante for feita na versão live, criar um novo snapshot antes (mesmo padrão do `claude/bom-dia-versions.md`) — não deixar a versão live ser o único registro que existe.

---

## Vocabulário — "Blocos"

Cada seção da página é um "bloco": header, info rápida, mapa das ilhas, AI Crew, treasure chest, diário de bordo das rotinas, radar (no seu radar + reservado), footer. Labels "bloco · X" no topo de cada seção são temporários — combinado que somem na versão final.

## Arquitetura de dados (v17, mantida na v18/v19)

O JS é organizado em camadas explícitas, seguindo o princípio DATA → STATE → COMPONENTS → THEME → INTERACTIONS pedido nos briefs "Command Center v17 — Visual + Architecture" e "AI Crew Avatar v1 Implementation":

- **`PERSONAS`** (array) + **`PERSONAS_MAP`** (lookup por id) — fonte única de verdade pra AI Crew, usada tanto pelos cards quanto pelo modal. Cada Persona tem `id, title, avatar, status ('active'|'recruit'), blurb, text, origin, link, visualState`. `visualState` é ponto de extensão pra futuras Crew Animations — hoje sempre `'static-portrait'`, sem efeito visual ainda. **Importante**: esse objeto guarda só copy de UI (blurb curto pra card/modal) — identidade, papel, missão, personalidade e comportamento completos de cada Persona continuam vivendo só nas páginas individuais do Notion, nunca duplicados aqui.
- **`renderCrew()`** — gera os cards da coluna AI Crew e o conteúdo do modal a partir de `PERSONAS`.
- **`TREASURE_ITEMS`** — Treasure Chest. Cada item tem `id, label, sub, icon, state ('available'|'dim'), badge, link`. `state` e `badge` são pontos de extensão (glow, contador, "new") ainda não implementados visualmente.
- **`RADAR_ITEMS`** — Radar. Cada item tem `title, description, priority, source, status, dueDate, relatedQuest, relatedPersona, action`. Estático hoje, estruturado pra migrar pra Notion depois sem tocar no render.
- **`isles`** (mapa das ilhas) — mantido como estava (SVG desenhado à mão + objeto de conteúdo por ilha), só ganhou o campo `state` (`'active'|'stable'|'blocked'|'paused'|'hub'`) como metadado estrutural pra uma futura Island Evolution — não renderizado visualmente ainda.

**Deliberadamente fora do escopo**: estados visuais dinâmicos das ilhas, animações da Crew, contadores/badges reais no Treasure Chest, temas (dia/noite/estação), Radar puxando do Notion em tempo real, variantes de avatar, personagens novos. A arquitetura de dados já comporta essas evoluções sem reescrever a página — só falta implementar, e só depois de validar o que já existe em uso real.

## Bloco Header / Info Rápida / Mapa das Ilhas

Sem mudanças. Chip "30 amanheceres registrados" continua hardcoded (pendência antiga). Mapa intacto por instrução explícita ("mesma alma agora, estruturar backend pra depois").

## Bloco AI Crew

**Roster canônico confirmado fresh no Notion em 2026-09-25 (AI Crew — Architecture & Persona Mapping) e implementado no artifact — 9 Personas:**
- The Navigator — ativo, avatar real. **Decisão (26/09): fica só "The Navigator" no artifact**, sem o sufixo "/ Expedition Concierge" (o nome completo é canônico no Notion, mas não precisa aparecer na interface)
- The Catalan Corsair — ativo, avatar real (ex-Claude Catalão / City Radar, Persona canonizada em 25/09)
- The Clothmaster, The Keymaster, **The Lorekeeper**, The Merchant, The Bard, The Beastmaster, The Healer — todos "a recrutar", avatar real, sem chat dedicado ainda

**Correção feita na v18**: o nome exibido era "The Logkeeper" (v16/v17) — **corrigido para "The Lorekeeper"**, nome canônico confirmado no Notion (evolução de Melhor Amiga/Best Friend). O arquivo de avatar já se chamava `The_Lorekeeper.webp`, então a correção alinhou nome e arte sem precisar trocar nenhum asset.

**✅ Resolvido (26/09) — divergência arte↔nota canônica (Healer, Merchant, Clothmaster, Bard)**: a arte final aprovada é autoritativa, não a nota escrita anterior no Notion — não é mais pendência.

**Removidos do artifact (v16→v17)**: Concierge e Comunicadora — sem Persona canônica correspondente.

## Bloco Treasure Chest

**9 itens agora (v19, decisão de 26/09)**: Supplies, Bom Dia Claude, Side Quest Aleatória, Gmail Sweep, Task Backlog, Player Sheet, Agenda Check, **City Radar / Local Lens** (novo), **The Ticket** (novo).

City Radar/Local Lens e The Ticket entraram como capabilities próprias — não duplicam a Persona Catalan Corsair, seguem o modelo Treasure → capability → resource/workflow subjacente. Nenhum dos dois tem chat dedicado ainda, então usam o mesmo padrão de prompt-launcher (`claude.ai/new?q=...`) já usado por Side Quest/Gmail Sweep/Agenda Check — não é um link inventado, é um atalho real que abre uma conversa nova já com o pedido pronto.

Runas circulares, sem garrafinha de poção.

## Bloco Diário de Bordo das Rotinas / Radar / Footer

Sem mudanças.

---

## Pendências (aguardando input dela ou decisão)

- Links reais dos chats "a recrutar" (Clothmaster, Keymaster, Lorekeeper, Merchant, Bard, Beastmaster, Healer) — nenhum tem `link` ainda
- Chip "30 amanheceres registrados" — continua hardcoded
- Testar de fato as rotinas 🌸 (Rotina de Alimentação, Diário Pessoal, Recap Session) com a Odara participando ao vivo — Side Quest On-Demand já validada (25/09)
- Eventual representação do Signal Scout / Odyssey Signals inbox no Command Center — só quando uso real justificar, não antecipar
- Fases futuras já estruturalmente possíveis mas não implementadas: estados visuais das ilhas, animações da Crew, badges/contadores reais no Treasure Chest, temas dia/noite/estação, Radar live do Notion — usam os campos de extensão (`state`, `visualState`, `badge`) já presentes
- Passe geral de polimento visual — segue adiado até a estrutura fechar e o uso real validar o que existe
