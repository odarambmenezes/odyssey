---
name: piloto-night-shift-implementacao-2026-09-28
description: Implementação da Fase 1 do piloto Night Shift + Crew Noticeboard (Keymaster ↔ Corsair) — o que existia, o que mudou, IDs, teste ponta a ponta, rollback com prompt original do Bom Dia, e prompt de setup da Lorekeeper.
sources: [chat]
---

# Piloto Night Shift — Implementação Fase 1 (28/09/2026)

Autoridade de implementação: Mayor (Structure & Systems). Narrativa/experiência: Operating Model (Odara + ChatGPT).

## IDs e links
- Página do piloto: https://app.notion.com/p/3e9107b19b49810ab115d6001db98ce7
- ⚓ Crew Noticeboard (banco): https://app.notion.com/p/83149997446e449885da37b4837bfccb · data source `collection://7cba836a-a6e5-48bf-b8fa-0468fee673d2`
- 📥 Entrada da Noite: https://app.notion.com/p/3e9107b19b4981d9bb88cddd29e07c42
- 🌙 Night Shift Log: https://app.notion.com/p/3e9107b19b498193bb34fbbceccb85d9
- Task Night Shift: `trig_01KBn9jigKXf8sCt9UdT9PES` — `CRON_TZ=Europe/Madrid 0 5 * * *`, sem push, aprovação automática
- Task Bom Dia (alterado): `trig_01EC7E7Uf5AapZV4gmHpM3dZ` ("Card Pull of the Day")

## Decisões de arquitetura
| Requisito | Decisão | Por quê |
|---|---|---|
| Night Shift | Novo Task às 05:00 | Nenhum Task existente cobre isso; a Manutenção é backlog-only e silenciosa por contrato. Sem conflito de horário (Manutenção 08:00, Bom Dia 11:30). |
| Crew Noticeboard | Banco pequeno novo (12 campos) | Mesa do Time não serve: é lida pelo Chatty (proíbe conteúdo pessoal), é texto livre e depende de "olha a Mesa". Bom Dia precisa filtrar por data/status via SQL. |
| Entrada da noite | Página nova | Diário Pessoal não é usado desde 09/09 e é íntimo; Lorekeeper não escrevia nada no Notion. Página com anexo no fim = operação mais robusta para um chat. |
| Night Shift Log | Página nova | Observabilidade legível, não precisa de SQL. |
| Handoff protocol | Campos do Noticeboard + regras no prompt do Task | Sem cartão por Persona ainda (só 2 Personas no piloto). |
| Keymaster ↔ Corsair | O Task "veste" as duas Personas lendo as páginas delas | Chats não acordam sozinhos. |
| Bom Dia | Bloco opcional/fail-safe no prompt | Menor ponto de integração: mesmo padrão do pré-voo SQL. |
| Modo sombra | Callout ⏸️ no Radar de Lares + limites no prompt | A autorização de contato do Keymaster (27/09) estava ativa. |
| Command Center preview | **Adiado** | CC é HTML estático; mostrar dado vivo exigiria republicar produção toda noite ou uma capability nova. Nada para mostrar antes de 2–3 noites reais. |

## Teste ponta a ponta (28/09, 14:40)
Entrada [TESTE] com contexto real: Be Casa Sant Cugat como ponte, medo de voltar tarde, rua viva, 🔺 empadronamiento.
Resultado:
- Roteamento: Keymaster + Corsair; Mayor não (nada estrutural); nada íntimo.
- 🔑 Clau: preço (€1.346 tudo incluído), pet ok, prédio em zona de escritórios com uso hoteleiro, empadronamiento não confirmado publicamente (❓), padrón seria em Sant Cugat e não Barcelona, perguntas para a visita. → ⏳
- 🏴‍☠️ Jaume: hipótese de rua morta à noite (escritórios + shopping), vida real no centro histórico, FGC S1 zona 1, volta tarde a confirmar, roteiro de visita-teste às 21h. → 🔧
- Conflito material preservado em linha própria 🔴 "Clau × Jaume", sem escolher por ela.
- Log completo; Entrada esvaziada; segunda execução mostrou "turno silencioso" + leitura de continuidade corretamente.
Falhas de desenho encontradas e corrigidas: Bom Dia só lia a noite atual (🔴 sumiria) → passou a ler também 🔴 abertos; nada fechava um 🔴 → Night Shift agora registra decisões da Odara que chegam pela Entrada.

## Limitações honestas
- Conectores de um Task não podem ser restringidos pela ferramenta: o Gmail vem anexado. "Não enviar" é por instrução.
- A Lorekeeper só escreve na Entrada depois do setup único (abaixo). Conversa que não vira entrada não chega ao Night Shift.
- Decisões da Odara só fecham um 🔴 se chegarem pela Entrada (via Lorekeeper). Decidir em outro chat não fecha automaticamente.
- Limpeza automática da Mesa do Time continua não implementada (achado anterior).

## Prompt de setup da Lorekeeper (colar UMA vez no chat dela)
```
Lorekeeper, a partir de hoje você faz parte do piloto 🌙 Night Shift (28/09 → 03/10), definido pelo Mayor na página ⚓ Crew Noticeboard & 🌙 Night Shift — Pilot (https://app.notion.com/p/3e9107b19b49810ab115d6001db98ce7).

Seu papel novo, além de tudo que você já é: sempre que eu te contar algo que outra parte do Crew deveria saber pra trabalhar melhor (moradia, bairro, burocracia, uma decisão minha sobre algo que o Crew preparou), anexe UMA linha no FIM da página 📥 Entrada da Noite (https://app.notion.com/p/3e9107b19b4981d9bb88cddd29e07c42), no formato:
- [DD/MM HH:MM] (Lorekeeper) Assunto — contexto em 1–4 linhas, nas minhas palavras quando possível. Marcadores: 🔺 legal · ❓ precisa confirmar · 🔴 eu quero decidir

Regras:
- Não me pergunte se pode registrar; faça em silêncio, só confirme curto ("anotado pro turno").
- Só o que outra Persona precisaria. O que é íntimo fica com você — não vai pra Entrada.
- Quando eu decidir algo sobre um item do Crew Noticeboard, registre a decisão na Entrada citando o item.
- Você não roteia nem contata ninguém: às 05:00 o Night Shift lê a Entrada, distribui e prepara. Você não muda estrutura do Odyssey.
- No modo noturno ("turno noturno"/"night shift"), respostas curtas e objetivas, como combinamos.
```

## Rollback
1. Desativar `trig_01KBn9jigKXf8sCt9UdT9PES`.
2. Restaurar o prompt do `trig_01EC7E7Uf5AapZV4gmHpM3dZ` para o original abaixo.
3. Remover o callout ⏸️ do Radar de Lares.
4. Artefatos podem ficar como histórico.

### Prompt ORIGINAL do "Card Pull of the Day" (antes de 28/09)
```
Este é um run agendado sem ninguém presente — não sugira conectores nem peça setup interativo.

⚡ PRÉ-VÔLO OBRIGATÓRIO — executar esses 3 passos ANTES de qualquer geração (via notion-query-data-sources, modo SQL):

1. MINI CARDS → SELECT Nome, "Regra da Frente", "Regra do Verso", "Cor de fundo" FROM "collection://049c4322-6c07-4726-9af3-72844974938e" WHERE Status = 'Ativo'
   Só gerar os cards retornados, na ordem da query. Nunca hardcodar nomes ou inventar cards.

2. POÇÕES → SELECT Nome, "Ícone/Emoji", "Prompt de disparo" FROM "collection://bd11c886-f95f-4d7e-bae8-d9914d57d9e5" WHERE Status = 'Ativo'
   Cada linha vira um botão .qa-btn: label = Ícone/Emoji + Nome, href = claude.ai/new?q={Prompt de disparo urlencoded}. Nunca inventar botões.

3. TEMA VISUAL → SELECT Nome, "Cor Base", "Cor Secundaria", "Cor Acento" FROM "collection://c793eef1-b59d-405c-b0c5-d6a5a69e040d" WHERE Status = 'Ativo'
   Sortear um aleatoriamente. Aplicar as cores via body[data-theme="..."] no CSS. Nunca usar paleta fixa hardcoded.

Só depois dos 3 passos acima, ler a página completa da rotina no Notion:
https://app.notion.com/p/3af107b19b49811eab20ef076172f85d

Usar o artefato de referência vivo como esqueleto exato (copiar estrutura e CSS, substituir só os [COLCHETES] com conteúdo do dia — não reconstruir do zero):
https://claude.ai/code/artifact/5c3800d9-4362-428d-989f-7d97f32808c5
(se esta URL estiver desatualizada, a versão atual está na seção "📎 Template de Referência" da página Notion acima)

Outros dados: Task Backlog (Notion), Google Calendar, Spotify, perfil musical/jogos https://app.notion.com/p/3af107b19b4981848caee3cfed043b2c, Player/Character Sheet https://app.notion.com/p/3aa107b19b4981b192b1fc071711e4b0

Resiliência: falha de conector = mensagem discreta nesse bloco específico, nunca trava tudo.

📝 LOG DO RUN — após entregar o artefato, inserir uma linha na tabela desta página:
https://app.notion.com/p/3d2107b19b4981b9821fc82913095797
Formato: | YYYY-MM-DD | [Nome do tema sorteado] | [Cards ativos, separados por vírgula] | [Poções ativas, separadas por vírgula] | — |

Screenshot antes de entregar, envie via SendUserFile.
```
