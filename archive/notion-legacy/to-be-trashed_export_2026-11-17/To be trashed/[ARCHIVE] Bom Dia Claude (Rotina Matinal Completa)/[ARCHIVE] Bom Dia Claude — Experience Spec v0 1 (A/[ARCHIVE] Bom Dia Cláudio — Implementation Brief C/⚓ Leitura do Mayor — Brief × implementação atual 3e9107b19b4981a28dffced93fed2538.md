# ⚓ Leitura do Mayor — Brief × implementação atual

> **Status:** 🟡 Preparação (28/09, 19:50). Leitura, auditoria e registro — **nada do comportamento canônico do Bom Dia foi alterado**. A coluna do piloto Night Shift é completada depois do primeiro Bom Dia real (29/09).
> 

> 
> 

> **Regras desta leitura:** Experience Spec = autoridade funcional. Golden Run = referência de sensação. Implementation Brief = instrução de execução. **O Spec não é ajustado para caber no código atual** — conflitos são apontados e levados à Odara.
> 

> 
> 

> Fontes lidas: Experience Spec v0.1, Implementation Brief, prompt agendado do "Card Pull of the Day", página da rotina (template v5), Registro de Cartas, Registro de Poções, Registro de Runs (05/09→28/09), Codex (Completion Protocol). **Não lido ainda:** o artefato do Golden Run 28/09 em si.
> 

# 0. O que depende do Night Shift e o que não depende

> O Night Shift **não é dependência** do Bom Dia. Noite sem atividade = estado válido, não bloqueio.
> 

| Parte do Spec | Depende do piloto? | Pode validar/aprovar/implementar agora? |
| --- | --- | --- |
| §2 Abertura e mesa | Não | Sim |
| §3–6 Widgets como Skills, contratos, Regenerate | Não | Sim |
| §8 Radar / Agenda | Não | Sim |
| §9 Task Backlog — exibição e recorrência | Não | Sim |
| §9 Task Backlog — reação da Odara | Parcial (só se passar pela Lori/Night Shift) | Sim, se a reação gravar direto no Notion (ver §5) |
| §11–13 Notícias, Coisas Boas, Treasures | Não | Sim |
| §14–15 Resiliência e publicação | Não | Sim (P0) |
| §16 Arquitetura (estado fora do HTML) | Não | Sim |
| §7 Night Shift Report — **estrutura e estado vazio** | Não | Sim |
| §7 Night Shift Report — **conteúdo real e curadoria** | **Sim** | Depois do piloto |
| §10 Scheduled Task → Lori | Parcial | Teste técnico simples independe do piloto (ver §5) |

# 1. O que o piloto validou

*A completar em 29/09 com o turno real.*

O que o teste de 28/09 (execução manual, marcada [TESTE]) já mostrou: roteamento correto só para quem importa, contexto adaptado por Persona, conflito preservado como 🔴 com as duas visões, leitura de continuidade e "turno silencioso" funcionando.

# 2. O que pode precisar mudar no Spec (só apontado — não alterado)

1. **Onde aparecem as decisões pendentes (🔴).** O §7 registra decisões tomadas, mudanças e trabalho feito — não "coisas que esperam a Odara". O piloto gera exatamente esse tipo de item. O Spec não diz onde ele vive.
2. **Estado vazio do Night Shift Report.** O §14 ("nunca desaparecer silenciosamente") trata de falha. Para "noite sem novidade" o Spec é silencioso: mostrar uma linha calma ou omitir?
3. **Onde a reação da Odara grava** (✓/✕ da Side Quest, "fiz essa", "move pra semana que vem"). O Spec diz "Lori processa"; tecnicamente há caminho mais direto (§5). Pode mudar o desenho do fluxo.

# 3. Divergências e bugs da implementação atual (o Spec vence; corrigir na implementação)

| # | Tema | Spec | Hoje | Correção |
| --- | --- | --- | --- | --- |
| 1 | XP na Side Quest | proibido | "+15 XP" (27/09) | remover |
| 2 | Side Quest virando obrigação | proibido | 28/09: "agendar consulta atrasada" | regra explícita no gerador + teste positivo/negativo |
| 3 | Soundtrack aberto | frase do Bard + ícone Spotify + avatar + Regenerate | registro: "só botão Play" | atualizar contrato no registro |
| 4 | Word of the Day fechado | ícone + palavra | registro: "sem ícone" | atualizar |
| 5 | Side Quest fechada | categoria/título curto ("Health Quest") | registro: só ícone do tipo | atualizar |
| 6 | Flo | ícone do Flo sempre no aberto | botão só entre −4 e −1 | atualizar |
| 7 | Flo — dado de origem | estado confiável | último ciclo registrado 15/08; runs se contradizem (27/09 "+13 dias" × 28/09 "dia ~14, folicular") | ver decisão §6.8 |
| 8 | Widget Registry | Skill, persona dona, avatar, ações, Ativo/Pausado | tem frente/verso/cor/links/status (Ativo/Inativo/Experimental) | acrescentar campos (Fase 2) |
| 9 | Treasures | por enquanto só Gmail Sweep | 3 ativas (Calendar Check, Gmail Sweep, O que tá pendente?) | pausar 2 no registro — ver §6.2 |
| 10 | Notícias | Mundo · Espanha · Barcelona · Brasil · Coisas Boas | Mundo · BCN · Brasil + Eventos (BCN/Games/Europa) + O Correio | faltam Espanha e Coisas Boas; Eventos e Correio → §6.1 |
| 11 | Task Backlog | Hoje+Semana juntos com data exata, Mês separado, Overdue como filtro | abas Hoje / Semana / Mês | reorganizar |
| 12 | Resiliência (P0) | Normal → Retry → Plano B → erro visível | "mensagem discreta"; registro mostra Gmail/Spotify offline recorrentes e "Backlog 0 itens" (19/09) / "indisponível" (21/09) | implementar a escada por seção |
| 13 | Publicação (P0) | link que abre + smoke test de interação | screenshot; quando a publicação foi bloqueada (07/09, 16/09) virou arquivo enviado | pipeline gerar→validar→corrigir→publicar; tratar bloqueio como erro visível |
| 14 | Bloco Night Shift (meu, 28/09) | depois das cartas; log estilo MMO (avatar + nota); "Ver log completo →" | "logo depois da Carta do Dia"; agrupado por status; some quando vazio | alinhar ao Spec |
| 15 | Bom Dia manual | mesma rotina dos dois gatilhos | o bloco Night Shift só existe no prompt agendado | mover regras para a fonte que os dois leem |

**Não é divergência:** tema sorteado entre os ativos (o Spec proíbe aleatoriedade só na **composição** dos widgets). Nomenclatura "Claudio Catalão" no Spec = Catalan Corsair (Jaume) — só nome.

# 4. O que o Brief já resolve

- Ordem das seções, contratos de cada widget e fim sem mensagem artificial.
- Lista "não regredir" cobre os itens 1, 2, 12, 13 acima.
- Critérios de aceite (§20) e ordem de implementação em 6 fases.
- **Recorrência a partir da conclusão real já existe** no sistema: é o Completion Protocol do Codex (Última vez feito = hoje → próximo prazo pela Recorrência). Só falta o Bom Dia disparar isso.

# 5. Achado técnico que muda o "como"

Um artefato publicado pode declarar **capacidades de runtime**. Três delas resolvem pontos do Spec que pareciam depender de chat:

| Capacidade | O que habilita no Bom Dia | Atenção |
| --- | --- | --- |
| **mcp** (conectores da Odara, com a credencial dela) | ✓ Fiz / ✕ Não fiz, "fiz essa", "move pra semana que vem" gravam **direto no Notion** a partir da própria página — respeita "HTML é interface, estado no Notion" | consentimento na primeira vez; página fica privada (ok) |
| **sample** (a página pergunta ao Claude na hora) | **Regenerate de verdade**, inclusive "realinhamento" | custo por clique; 5–60s de espera |
| **artifact** (a página salva o próprio estado) | contador de 3 regenerações/dia sem repetir conteúdo | — |

**A validar antes de adotar:** (a) se uma execução **agendada** consegue publicar artefato com capacidades — o histórico mostra publicação bloqueada em runs automáticos (07/09, 16/09); (b) o fluxo de consentimento no celular.

**Alternativa sem capacidades:** 3 variações pré-geradas por widget (confiável, mas sem realinhamento real) e reações via conversa.

**§10 Scheduled Task → Lori — hipótese técnica:** responder dentro da sessão do Bom Dia (que tem Notion) poderia aplicar o Completion Protocol direto no Backlog, ou anexar na 📥 Entrada da Noite para a Lori. **Teste simples, independente do piloto:** a Odara responde uma frase na sessão do Bom Dia de 29/09 e vemos se a sessão age.

# 6. Decisões que voltam para a Odara antes de implementar

1. **Eventos e O Correio** existem hoje e não estão no Spec: saem, ou entram no Spec?
2. **Calendar Check e "O que tá pendente?"**: pausar, como o Spec indica ("por enquanto: Gmail Sweep")?
3. **Decisões pendentes (🔴)**: onde aparecem — dentro do Night Shift Report, no Task Backlog, ou numa linha própria?
4. **Noite sem novidade**: uma linha calma visível, ou omitir a seção?
5. **Reações (✓/✕, backlog)**: gravar direto no Notion pela página, ou sempre passar pela Lori? *Recomendação do Mayor:* status do Backlog direto (o Completion Protocol já existe); Lori só quando precisa de roteamento ou conversa.
6. **Regenerate**: ao vivo (sample, custo por clique, realinha) ou 3 variações pré-geradas? *Recomendação:* ao vivo, com as pré-geradas como Plano B.
7. **Modelo** da execução agendada do Bom Dia (hoje Sonnet 4.6).
8. **Flo**: quem mantém a data do ciclo em dia (hoje manual na Player Sheet, parada desde 15/08)?

# 7. Plano de implementação (Mayor), seguindo as fases do Brief

- **Antes de tudo:** snapshot da versão atual (prompt agendado + template v5) com rollback documentado.
- **Fase 1 — casca da experiência:** pode começar assim que as decisões 1 e 2 saírem. Não depende do Night Shift.
- **Fase 2 — estado e arquitetura:** Widget Registry com os campos do Spec; regras movidas para a fonte que os dois gatilhos (agendado e manual) leem.
- **Fase 3 — camadas operacionais:** Radar, Backlog e reações; Night Shift Report com estrutura e estado vazio já prontos, conteúdo validado pelo piloto.
- **Fases 4–6:** notícias, resiliência, validação — como o Brief manda.
- Cada fase: validar → publicar → observar um Bom Dia real → só então a próxima.