# ⚓ Crew Noticeboard — ponteiro (atualizado 11/11/2026)

O Crew Noticeboard (antes chamado Mesa do Time, "a Mesa") é a linha principal de comunicação entre chats, modelos (Claude/ChatGPT), Personas e Builders. **A fonte de verdade é o Notion, não este doc.** (O nome do arquivo continua mesa-do-time.md por histórico.) A página no Notion foi **fechada pela Odara em 11/11/2026**.

- **Protocolo + quadro vivo:** página "Crew Noticeboard" (antes Shared Notice Board), em 02 O Navio — https://app.notion.com/p/410107b19b4981009b2ada911ec304fb
- **Banco:** ⚓ Crew Noticeboard — https://app.notion.com/p/83149997446e449885da37b4837bfccb (views: Default · 📬 Abertos · Discuss with Odara · 👥 Por destinatário · 🔥 Needs attention · 📊 Board by status · 📦 Resolved & Archived · 🆕 New by arrival · 💬 Sent Back · 🗣️ To Discuss · 🧹 Lore queue)
- **Main page do projeto:** view vinculada do banco, com a primeira aba **👁️ On my radar** (o que a Odara precisa saber: To Discuss, Critical e Discuss Live com Odara, sem Resolved/Archived, ordenado por Prioridade e depois pela mais antiga), seguida de 🔥 Needs attention, 📊 Board by status e 📦 Resolved & Archived.
- **O link antigo (3e8107b1…) aponta para uma página apagada. Não usar.**

## Quando usar
- **Leitura automática:** início de todo chat de trabalho do Odyssey (passo 4 do Operating Manual, que agora inclui o stale check) e a cada transfer de persona no chat ativo.
- **Gatilhos da Odara:** "deixa na Mesa", "anota pro Cap", "olha a Mesa do Time", "confere os recados" (os apelidos antigos continuam valendo como atalho).
- **Postar:** um registro por assunto (buscar abertos antes), com De, Para, Prioridade, título e corpo no formato abaixo. Dizer à Odara só o que de fato foi postado; um recado postado não prova que alguém leu.

## O que a persona faz ao pegar o quadro
1. Verifica o board quando é invocada por um chat novo ou por transfer de persona. Também procura as próprias notas que voltaram (De = ela, Status 💬 Sent Back).
2. Lê as notas atribuídas a ela (Para = ela ou Todos), página inteira e Origem.
3. Verifica a própria página e SoT para ver o que a nota mudaria para ela.
4. Traz para a Odara que recebeu a nota e o que recomenda fazer. Depois roda o stale check.
5. Alinham ao vivo e a persona aplica o combinado.
6. Posta a conclusão na seção final (Answer) da página da nota, marca Lido por e atualiza o Status: 💬 Sent Back (resposta rápida para quem postou), 🗣️ To Discuss (tudo feito, falta só a conferência da Odara) ou ✅ Resolved (fechada). Quem marca ✅ Resolved escreve também a Resposta, uma linha só, como referência rápida e arquivo.
- **O quadro é só comunicação, não projeto.** Se algo precisar de mais trabalho, processo ou projeto, vira conteúdo de outra página (SoT, backlog, página da persona) e a nota só aponta para ela. Não vira registro de coisas importantes.
- **Nota endereçada à persona errada:** quem abre não reatribui nem fecha por conta própria. Pergunta à Odara primeiro (ela pode ter escolhido aquela persona de propósito). Só troca o Para depois que ela confirmar.

## Formato da nota
- **Título:** uma linha clara, em inglês, que resume a página. Nunca o remetente nem o destinatário (De e Para já dizem), sem emoji nem tags tipo [TESTE]. Verbo quando há algo a fazer ou decidir.
- **Corpo da página, nesta ordem:** Context (detalhes relevantes) · Request (problema identificado e o que queremos mudar, propor ou investigar) · Output (resultado esperado, se já estiver claro; se não, a persona pensa) · Resources (links e qualquer info que faça diferença). Quem responde acrescenta uma seção Answer no fim.

## Status (decidido 11/11): "de quem é a vez?"
| Status | Significado | Vez de |
|---|---|---|
| 🆕 New | Postada, ninguém agiu ainda | Destinatário |
| 💬 Sent Back | Destinatário respondeu rápido (uma linha em Resposta) e devolveu a quem postou, sem envolver a Odara | Quem postou |
| 🗣️ To Discuss | Tudo feito, falta só a Odara conferir antes de fechar (não confundir com a Prioridade Discuss Live with Odara, que diz que a nota nasce como conversa) | Odara |
| ✅ Resolved | Fechada, com a Resposta de uma linha. Fila da Lori | Lori |
| 📦 Archived | A Lori conferiu e tirou de circulação; as views de trabalho escondem | Ninguém |

Os status antigos (Novo, Preparado, Aguardando, Resolvido) foram removidos. Migração: Novo → New, Aguardando → To Discuss, Resolvido → Resolved (nenhuma nota estava em Preparado). A nota de Málaga foi para New, a vez da Cap.

## Modelo atual (Prioridade em vez de Tipo/Urgência)
- Colunas: Note · Prioridade · De · Para · Status · Posted in · Origem · Lido por · Resposta (uma linha, preenchida por quem fecha) · Days open (a fórmula foi reescrita em 11/11 para ignorar Resolved e Archived).
- Prioridade e prazo máximo sem leitura: **Critical** (status legal, segurança ou data fixa próxima: evento que ela comprou, se comprometeu ou quer ir, ou prazo) 3 dias · **Action Needed** 5 dias · **Discuss Live with Odara**, **Announcement** e **FYI** 7 dias. Em Discuss Live, o Para é a persona que vai trabalhar o tema com a Odara.
- Sem data de expiração. Contagem a partir de Posted in. Não lida = nota 🆕 New em que um destinatário do Para está fora de Lido por (Todos = toda persona Active). Notas 💬 Sent Back esperam quem postou, que confere no início da sessão; notas 🗣️ To Discuss esperam a Odara; nenhuma das duas entra na regra. Notas endereçadas à Odara ficam fora da regra, pois ela fala direto com as IAs.
- **Stale check:** Lori e qualquer chat ativo da Odara, ao abrir o quadro. Aplica o limite de cada nota (3, 5 ou 7 dias). Por nota, trazer: de quem era, para quem era, link e resumo de 2 linhas; perguntar se ataca agora ou se aciona/transfere para a persona.
- **Notas para Todos atrasadas (Announcement/FYI):** ninguém espera cada persona ser ativada só para marcar "lido". A Lori entra na página de cada persona que falta em Lido por, entende o contexto e decide: (1) pouco ou nenhum impacto: ela marca como lido em nome da persona, com uma linha em Resposta; (2) impacto real: ela volta para a Odara com a situação e recomenda transferir para a persona ou trabalharem juntas (Odara e Lori) para identificar o que muda para ela. Se couber, a Lori fecha a nota geral como ✅ Resolved e deixa só notas específicas para quem precisa. Pergunta à Odara por persona, não por nota.
- **Caso outstanding** (persona nova, sem página AI Crew ou não Active): endereçar à Lorekeeper, que decide e age.
- Limitação conhecida: persona não ativada não lê; falta um mecanismo para acordá-la quando mencionada.
- **Limpeza quinzenal pela Lori** — skill "Noticeboard Clean-up (quinzenal, Lori)" no Skills Mapping, On Draft, **processo escrito em 11/11/2026** (5 passos: sincronizar as listas · arquivar o que terminou pela view 🧹 Lore queue · fechar o que está pronto e juntar duplicatas · cobrar o que travou · reportar à Odara). Access = Restricted, Used by = Lori, The Keeper. A fila dela são as notas ✅ Resolved. Passo fixo: conferir as listas De, Para e Lido por com o Crew Mapping e atualizá-las quando a Crew mudar. A testar na reativação das personas.
- Tipo, Urgência, Expira em e campos antigos estão ocultos, não apagados. O status "🔴 Decisão da Odara" foi removido (11/11); a fila dela é a view On my radar.

## Regras que valem aqui
1. Recado não é ordem estrutural. Mudança de arquitetura, regra ou esquema do banco é decisão da Odara (Manual G21).
2. Contexto mínimo + link para a fonte; não copiar dado sensível para o quadro. Dado sensível só sai do Odyssey com aprovação específica (G22).
3. Ação que exige alguém tem destinatário nominal; "Todos" é só para Announcement e FYI.
4. Nunca apagar notas; fechar com ✅ Resolved. Arquivar (📦 Archived) é com a Lori.

## Pendências (movidas da página do Notion em 11/11, ao fechá-la)
- ~~Scheduled task semanal da Lore (trig_01PHhbemGXgAhGYeVA4aak3x)~~ — **pausada pela Odara em 11/11/2026.** A linha no Skills Mapping ("Mesa do Time — Weekly Board Clean-up") está Archived.
- Colunas antigas ocultas (Tipo, Urgência, Expira em, Contexto, Por que importa, Ação sugerida, Retorno esperado): apagar de vez só quando a Odara disser.
- **Agora liberado** (a revisão de skills terminou em 11/11): scheduled task quinzenal/semanal de obtenção de contexto externo para as personas, juntando vários radares num scan só (ex.: shows do Bard + voos/trens do Cap; futuro scan de vagas + novos apartamentos).
- Mecanismo para acordar uma persona quando mencionada (limite do projeto).
- Nomes antigos em De/Para (Night Shift e outros), depois da revisão do Crew Mapping.
- Bom Dia Claude está sendo reconstruído como **Workflow** (linha criada no Skills Mapping em 11/11, com as skills que ele chama em Steps); o bloco antigo do Night Shift sai com ele.
- Uma linha curta sobre o quadro nas instruções de projeto do Claude e do ChatGPT (não editável daqui).
- Aposentar páginas legadas pelo processo de documentação aprovado: docs do piloto Night Shift, o banco antigo AI Notice Board e os itens "Notice Board follow-up" nas páginas de Persona.
- Scan final: nomes de propriedades e status em PT/EN. No Skills Mapping, só o campo Recurrency foi normalizado em 11/11; Mission e Use Cases ainda misturam os dois idiomas. Tarefas antigas do Grab & Go que citam Mesa do Time / Notice Board ficam como histórico.
- Próximo passo combinado: revisar o que muda na documentação original (páginas de Persona, etc.).
- Testes ponta a ponta (Claude ↔ ChatGPT, persona ↔ persona, "Todos") ficam para a reativação das personas.

## Histórico
O quadro (então Mesa do Time) começou como convenção de notas em 27/09/2026, virou o piloto Crew Noticeboard em 10/10 e absorveu a antiga página 00 no início de novembro. Em 11/11/2026 a Odara trocou datas de expiração pela regra de não lidas, fundiu Tipo e Urgência em Prioridade, definiu o nome Crew Noticeboard e trocou os status antigos pelos cinco novos. Night Shift (rotina noturna) e a limpeza semanal foram aposentados; os docs de 28/09 sobre o piloto (revisao-arquitetura-crew, piloto-night-shift-implementacao) são histórico, não instrução atual.

## Estado das páginas do Notion
- Nome e status novos propagados: página Crew Noticeboard, Manual (glossário, passo 4 com stale check, G21), página principal do Odyssey, 02 O Navio, 04 AI Crew & Skills, skills Leave a Note, Hand Off e Noticeboard Clean-up, views do banco e da main page, descrição e fórmula Days open.
- **Skills Mapping reconciliado em 11/11/2026** — ver `claude/reconciliacao-skills-mapping-2026-11-11.md`. Leave a Note e Hand Off to Persona seguem On Draft (Access Open: são o mecanismo de comunicação entre personas, qualquer uma precisa poder usar). Noticeboard Clean-up (quinzenal, Lori) On Draft, Access Restricted. Weekly Board Clean-up **Archived**.
- **Lore x Lori:** o Crew Mapping é o roster oficial e diz "Lori, The Keeper". Os textos antigos que diziam "Lore" foram alinhados em 11/11; podem ainda existir menções soltas em páginas de Persona e notas históricas.
- Fica como está por enquanto: páginas de Persona com "Notice Board follow-up" e tarefas antigas do backlog (recalibrar quando as personas forem reativadas); páginas históricas.
