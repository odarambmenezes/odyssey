# [ARCHIVE] Bom Dia Claude — Experience Spec v0.1 (Aprovado 28/09/2026)

> **STATUS: APROVADO — 28/09/2026**
> 

> Esta página é a especificação de experiência aprovada para o Bom Dia Cláudio v0.1. Ela registra decisões tomadas na revisão do run de 28/09/2026 e orienta a próxima implementação antes de qualquer refinamento visual adicional.
> 

## 1. Propósito e experiência

O Bom Dia Cláudio é a primeira porta de entrada da Odara no Odyssey pela manhã, geralmente ainda na cama e antes de qualquer referência externa.

A experiência desejada é **descoberta + orientação**, com a sensação de:

> “Vamos ver o que o dia trouxe para mim.”
> 

Não deve começar como “vamos ver o que eu tenho que fazer hoje”. O Odyssey deve transmitir que trabalhou durante a noite e deixou o mundo um pouco mais organizado para ela. Obrigações e caos podem existir, mas dentro de um ritual que começa com curiosidade, frescor e possibilidade.

O Bom Dia é uma ponte para o restante do Odyssey. Se ele quebra ou entrega um link inutilizável, a confiança no projeto inteiro é afetada. Confiabilidade é requisito P0.

## 2. Abertura e mesa

A experiência começa com uma carta principal fechada. A Odara clica; a carta vira e se transforma no Report do Bom Dia Capitão. Em seguida, as cartas/widgets são distribuídas na mesa com a animação de cascade/dealing.

Essa revelação é parte do ritual, não apenas decoração.

Mobile é a experiência prioritária. Desktop pode adaptar a composição.

## 3. Widgets como Skills

Cada carta é um **widget**, e cada widget é uma manifestação visual de uma Skill do Odyssey.

O widget não existe apenas dentro do Bom Dia: a Skill correspondente também pode ser chamada independentemente durante o dia.

Cada widget possui:

- Skill;
- persona dona;
- contrato visual;
- ações próprias;
- estado ativo/pausado.

A composição da mesa é configurada explicitamente no Notion/Widget Registry. Não é aleatória. Claude não deve adicionar, remover ou trocar widgets por conta própria.

Os quatro Core Widgets atuais são:

- 🌙 Flo → Healer
- 🎵 Soundtrack → Bard
- 📜 Word of the Day → Claudio Catalão
- 🗺️ Mini Side Quest → Lore

Widgets futuros podem ser adicionados ou pausados explicitamente. Pausar não significa deletar.

## 4. Contrato visual dos widgets

Regra central:

> **Carta fechada = glanceable. Carta aberta = aprofundamento.**
> 

Fechada:

- bater o olho e entender;
- mínimo de texto;
- nenhum parágrafo;
- nenhuma explicação desnecessária;
- usar a linguagem visual/ícones já estabelecidos pelo widget.

Aberta:

- contexto curto;
- ações do próprio widget;
- avatar da persona dona;
- links externos;
- regenerate, quando suportado.

As ações ficam dentro da carta aberta.

O avatar da persona funciona como assinatura e porta de entrada para o chat da persona, idealmente já contextualizado com aquele widget.

## 5. Regenerate

Widgets generativos podem oferecer Regenerate.

- Primeira geração = sorte.
- Regenerate #1 = pedido de realinhamento.
- Regenerate #2 = última chance.
- Máximo de 3 resultados por widget/dia.
- MVP: apenas fade suave na troca.
- Não repetir conteúdo já apresentado naquele ciclo.

Regenerate é **agência sobre a sorte**, não correção do algoritmo.

## 6. Contratos dos quatro Core Widgets

### Soundtrack

Fechada: somente música + artista.

Aberta:

- one-liner do Bard explicando a escolha, com personalidade;
- ícone do Spotify;
- avatar do Bard;
- regenerate.

Não escrever “Abrir Spotify” se o ícone já comunica isso.

### Word of the Day

Fechada: ícone + palavra, sem subtítulos acumulados.

Aberta:

- tradução;
- contexto/uso;
- regenerate;
- opção de regenerar em catalão;
- avatar do Claudio Catalão.

### Mini Side Quest

Fechada: categoria/título curto, ex. “Health Quest”.

Aberta: missão concreta, actionable e curta; pode ser um pouco mais textual que os demais widgets, mas não deve virar parágrafo.

Teste positivo:

> Uma Side Quest correta faz a pessoa querer jogar o dado e ver o que acontece.
> 

Teste negativo:

> Se parece “mais uma coisa que eu não posso esquecer”, está errada.
> 

Uma quest pode nascer de sinais do backlog/vida, mas precisa ganhar forma de quest: abertura, exploração ou possibilidade de surpresa. Não pode virar obrigação disfarçada.

Ações:

- regenerate;
- avatar da Lore;
- ✓ Fiz;
- ✕ Não fiz.

Quests feitas podem ser encaminhadas à Lore com contexto/comprovante e futuramente alimentar Memory Log/narrativa anual.

### Flo

Não é generativo.

Fechada:

- estado visual simples;
- fora da janela deve ser neutro, ex. 🌙;
- não despejar fase/explicação na frente.

Aberta:

- poucos bullets sobre o que a fase pode significar/sugerir para a Odara naquele momento;
- linguagem prática, não artigo;
- ícone do Flo para abrir Flo;
- avatar Healer para conversa contextualizada.

Sem Regenerate.

A carta deve ajudar a Odara a se orientar consigo mesma, sem transformar o widget em texto clínico ou em afirmações categóricas.

## 7. Night Shift Report

Depois das cartas entra **NIGHT SHIFT REPORT**.

Não é resumo da conversa. É o handoff operacional da Lori após o encerramento do Night Shift.

Visual:

- inspirado em chat/log de MMO;
- entradas em sequência;
- avatar/ícone da persona + nota;
- não precisa repetir o nome da persona.

Exemplo:

> ◉ Clau — Perfil de inquilino atualizado: terraça adicionada como requisito.
> 

Registrar apenas:

- decisões;
- mudanças;
- encaminhamentos;
- descobertas;
- trabalho efetivamente realizado.

Não registrar atividade por atividade.

O Bom Dia mostra um **log curado**. Deve existir “Ver log completo →”, levando ao registro operacional no Notion, que funciona como um ticket system: pedido → encaminhamento → responsável → ação → resultado → estado.

## 8. Radar do Dia / Agenda

Depois do Night Shift vem a agenda, mas ela funciona como **radar**, não como calendário.

Formato compacto, por exemplo:

- 🔴 10:00 — Fortis
- 🟢 18:30 — Jantar
- 🌧️ Chuva à tarde

Mostrar principalmente:

- qualquer compromisso antes das 16h;
- compromissos pessoais;
- outros compromissos que mudem como o dia começa;
- alertas meteorológicos relevantes.

Não despejar detalhes já disponíveis no calendário.

## 9. Task Backlog

Depois do Radar vem o Task Backlog.

Objetivo:

> bater o olho e saber o que está acontecendo com as obrigações reais do sistema.
> 

Visual:

- compacto;
- Hoje + Semana em uma visão;
- data exata em cada task;
- highlight claro para hoje;
- Mês separado;
- filtro Overdue separado.

Cada task precisa, no mínimo, mostrar título + data + estado visual.

O título “Task Backlog” pode levar para a tabela completa no Notion. Página individual só precisa ser acessível quando houver informação relevante.

Deve existir uma entrada clara para conversar com a Lori/agente dela sobre as tasks.

### Task Backlog é bidirecional

Fluxo:

> Notion → Bom Dia → Odara reage → Lori processa → Notion atualizado → próximo Bom Dia reflete o estado.
> 

A Odara pode dizer:

- “fiz essa”;
- “move pra semana que vem”;
- “isso não faz mais sentido”;
- “preciso de ajuda”.

A Lori deve transformar a conversa em atualização real do sistema.

### Recorrências

Para tasks recorrentes, quando a conclusão real for informada, a próxima ocorrência deve ser calculada segundo a regra de recorrência a partir da data real de conclusão, quando esse for o modelo da task.

Exemplo:

- Cortar unhas;
- recorrência = 14 dias;
- prevista = sexta;
- Odara informa hoje que concluiu;
- registrar hoje como conclusão;
- calcular próxima ocorrência = hoje + 14 dias;
- atualizar a próxima data no Notion.

A data prevista antiga não deve congelar a recorrência.

O Bom Dia mostra o estado; o Notion mantém a lógica, histórico e próximas datas.

### Lori + pet

Está aprovada a exploração de um pet da Lori como agente operacional especializado em Tasks/Obligations. A ideia da raposinha surgiu como candidata. Nome e personalidade ainda não estão fechados. O pet é extensão operacional da Lori, não uma nova persona independente por padrão.

## 10. Atualização via contexto da Scheduled Task

Requisito a validar tecnicamente com Claude:

A Odara quer poder, no contexto do Bom Dia/scheduled task, dizer algo como:

> “Tem um update para a Lori sobre o Bom Dia Cláudio de hoje: fiz X, Y vai para semana que vem…”
> 

e esse contexto deve conseguir encaminhar/processar a atualização com a Lori, sem exigir que ela procure manualmente a persona em outro lugar.

Não assumir que essa capacidade existe sem validação.

## 11. Notícias do Dia

Depois do Task Backlog:

- 🌍 Mundo
- 🇪🇸 Espanha
- 🏙️ Barcelona
- 🇧🇷 Brasil
- ✨ Coisas Boas

Para Mundo/Espanha/Barcelona/Brasil, o critério é:

> **O que a Odara deveria saber hoje?**
> 

Prioridade para impacto real na vida dela.

Espanha:

- imigração/residência;
- tributação;
- moradia;
- trabalho;
- mobilidade/viagens;
- segurança;
- serviços e regras relevantes.

Barcelona/Catalunha:

- segurança;
- transporte;
- clima/interdições;
- moradia;
- serviços;
- turismo quando houver impacto relevante para moradora.

Brasil:

- mudanças que afetem brasileiros no exterior;
- tributação;
- documentação;
- regras e acontecimentos com impacto pessoal.

As headlines devem ser links reais para a fonte.

Quando a relevância pessoal for especialmente importante, pode existir uma microcontextualização, ex. “Pode afetar brasileiros vivendo na Espanha.”

### Fontes

O Source Registry definitivo ainda não está fechado.

- Claudio Catalão deve ajudar a identificar bons canais para Barcelona/Catalunha.
- G1 é a fonte inicial indicada para Brasil.
- Mundo pode usar busca ampla na internet/fontes apropriadas.

### Fallback

Fonte normal → retry → falhou novamente → busca direta na internet → se também falhar, manter a seção visível em estado de erro com caminho manual de busca.

Nunca remover a seção silenciosamente.

## 12. Coisas Boas

A aba existe para mostrar que o mundo também produz coisas significativas e boas.

Não queremos curiosidades pequenas. Queremos histórias realmente impactantes:

- grandes avanços científicos;
- saúde;
- ambiente;
- iniciativas relevantes;
- descobertas importantes;
- grandes histórias humanas.

Formato:

> headline de uma linha + link.
> 

Sem explicação longa.

## 13. Treasures / Poções

No final existe a prateleira **TREASURES / POÇÕES**.

Ela não é mais uma seção editorial. É uma ponte para ação.

Por enquanto:

- 📬 Gmail Sweep.

Clicar abre a Skill/chat correspondente.

Futuros treasures podem incluir outras Skills, como scan de imóveis.

A prateleira é estável; os treasures são plugáveis.

Depois disso, o Bom Dia termina. Não adicionar outro card ou mensagem motivacional. A intenção é que, nesse ponto, a Odara já esteja orientada e pronta para levantar e viver o dia.

## 14. Resiliência — P0

Cada sessão/widget segue:

> **Normal → Retry → Plano B → Erro explícito**
> 

Se falhar:

1. tenta novamente;
2. mesmo erro → Plano B;
3. Plano B falhou → seção continua visível em estado de erro.

Uma sessão nunca desaparece silenciosamente porque uma fonte falhou.

Cada sessão terá seu próprio Plano B, construído progressivamente.

Exemplos já definidos conceitualmente:

- Agenda → link direto para calendário;
- Clima → fonte meteorológica direta;
- Notícias → busca direta na internet;
- falha total → mensagem de erro contextual + caminho manual quando possível.

A mensagem de erro deve ser humana e visualmente integrada ao artefato, não erro técnico cru.

## 15. Publicação e smoke test — P0

O ciclo obrigatório é:

> **gerar → validar → corrigir → validar novamente → publicar → entregar**
> 

Não entregar um link apenas porque o HTML foi gerado.

O smoke test precisa confirmar pelo menos:

- link abre;
- splash/carta principal responde ao clique;
- carta vira;
- Report aparece;
- widgets aparecem;
- interações essenciais funcionam;
- falha de uma integração não quebra o board inteiro;
- fallback/estado de erro aparece quando aplicável.

## 16. Princípios de arquitetura

**O Bom Dia mostra o estado. As personas mantêm o estado.**

A lógica crítica não deve ficar presa no HTML diário.

O HTML é interface; estado, lógica, registries e histórico pertencem ao sistema canônico.

O Notion continua sendo fonte de verdade para os dados e configuração que o runtime precisa consultar.

## 17. Direção futura

A visão de longo prazo é um **Odyssey Live Dashboard**: um ambiente próprio, possivelmente app/site/servidor, em que o sistema rode continuamente e seja comandado por IA.

O MVP atual não precisa resolver isso, mas sua arquitetura não deve impedir essa evolução.

## 18. Ainda não decidido

Não congelar ainda:

- visual final;
- Source Registry definitivo;
- Planos B detalhados de cada sessão;
- identidade final do pet da Lori;
- detalhes completos do Night Shift;
- Gmail Sweep detalhado;
- lista futura de Treasures;
- detalhes técnicos da integração Scheduled Task → Lori;
- schema final do Widget Registry;
- testes completos de cada widget;
- refinamentos visuais derivados do Golden Run 28/09.

## 19. Relação com o run de 28/09/2026

O run de 28/09/2026 é uma **referência comportamental/Golden Run**, não substitui esta especificação.

Devemos preservar dele:

- sensação de diário de bordo;
- abertura/revelação;
- quatro cartas;
- curadoria;
- atmosfera;
- Radar/Agenda;
- contexto meteorológico;
- sensação de “algo foi preparado para mim”.

Não copiar automaticamente seus desvios de implementação.

Esta página é o contrato de comportamento aprovado; o Golden Run serve como referência de experiência.

---

**Próximo passo:** usar esta especificação aprovada como base para um prompt de implementação detalhado para Claude. O prompt deve explicar não só o que construir, mas por que cada decisão existe, e separar experiência, comportamento, arquitetura, integração e critérios de aceitação.

[[ARCHIVE] Bom Dia Cláudio — Implementation Brief / Claude Handoff](%5BARCHIVE%5D%20Bom%20Dia%20Claude%20%E2%80%94%20Experience%20Spec%20v0%201%20(A/%5BARCHIVE%5D%20Bom%20Dia%20Cl%C3%A1udio%20%E2%80%94%20Implementation%20Brief%20C%203e9107b19b49817bb7dccd423287eca8.md)