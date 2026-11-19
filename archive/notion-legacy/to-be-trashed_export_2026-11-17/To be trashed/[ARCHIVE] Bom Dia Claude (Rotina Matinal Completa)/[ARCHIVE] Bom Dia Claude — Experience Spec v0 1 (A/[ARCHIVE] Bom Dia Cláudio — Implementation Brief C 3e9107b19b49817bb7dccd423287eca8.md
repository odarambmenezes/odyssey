# [ARCHIVE] Bom Dia Cláudio — Implementation Brief / Claude Handoff

> **Documento de handoff para implementação — usar junto com o Experience Spec v0.1 aprovado.**
> 

> 
> 

> Este documento traduz o contrato de experiência em instruções de implementação para o Cláudio. O **Experience Spec é a autoridade funcional**; este documento explica intenção, arquitetura, comportamento e critérios de aceite. Se houver conflito, o Experience Spec prevalece.
> 

## 1. WHY — o problema que estamos resolvendo

**Bom Dia Cláudio não é um dashboard de tarefas.** É a primeira porta de entrada da Odara no Odyssey pela manhã, muitas vezes ainda na cama e antes de abrir outras referências.

A pergunta emocional que a experiência deve provocar é:

> **“Vamos ver o que o dia trouxe para mim.”**
> 

E não:

> “Vamos ver tudo o que eu tenho que fazer hoje.”
> 

A experiência precisa comunicar que o Odyssey **trabalhou durante a noite e organizou o mundo para ela**.

Isso significa que obrigações, backlog, clima, notícias e pendências podem aparecer — mas o ritual deve começar por **curiosidade, descoberta, frescor e possibilidade**.

### Princípio de produto

Bom Dia deve **reduzir carga cognitiva**, não criar mais uma interface que a Odara precise administrar.

Portanto:

- curadoria antes de exibição;
- pouco conteúdo, bem escolhido;
- profundidade somente quando necessária;
- cada elemento deve ter uma função clara;
- nenhum widget deve virar um “mini sistema” independente dentro do Bom Dia.

**Confiabilidade é P0.** Um link quebrado, um card que não abre ou uma integração que simplesmente desaparece reduz a confiança no Odyssey inteiro.

---

## 2. WHAT — experiência da abertura

### Estado inicial

A sessão começa com **uma única carta/card principal fechado**.

A Odara clica.

O card vira e revela o **Bom Dia Captain Report**.

Só então os demais cards/widgets são distribuídos/cascateados sobre a mesa.

A revelação é parte do ritual. Não é apenas uma animação decorativa.

### Regras

- O splash começa fechado.
- O clique deve responder sempre.
- O Report aparece após a revelação.
- Os widgets aparecem depois da revelação.
- Mobile é prioridade; desktop adapta.
- Uma falha em um widget nunca pode impedir o restante do Bom Dia de aparecer.

---

## 3. WHAT — widgets são Skills

Cada card do Bom Dia é uma manifestação visual de uma **Odyssey Skill**.

O card não é apenas UI: ele representa uma capacidade do sistema.

Cada widget deve ter:

- Skill correspondente;
- persona responsável;
- contrato visual;
- ações permitidas;
- estado Ativo/Pausado;
- regras próprias de geração/integração.

### Core Widgets atuais

| Widget | Skill / Owner |
| --- | --- |
| Flo | Healer |
| Soundtrack | Bard |
| Word of the Day | Claudio Catalão |
| Mini Side Quest | Lore |

### Regra de composição

A composição do Bom Dia deve ser **configurada explicitamente no Widget Registry / configuração canônica**.

Não usar aleatoriedade para decidir quais widgets aparecem.

O Cláudio **não pode adicionar, remover, trocar ou inventar widgets por conta própria**.

Um widget futuro pode ser adicionado ou pausado explicitamente.

**Pausado ≠ deletado.**

---

## 4. CONTRATO VISUAL DOS WIDGETS

### Regra central

> **Closed card = glanceable. Open card = depth.**
> 

### Card fechado

Deve permitir que a Odara:

- olhe;
- entenda;
- reconheça;
- siga adiante.

Evitar:

- parágrafos;
- explicações desnecessárias;
- excesso de texto;
- informação secundária acumulada;
- ações que não precisam estar visíveis.

### Card aberto

Pode trazer:

- contexto curto;
- ações;
- links externos;
- avatar da persona;
- personalidade;
- regenerate, quando aplicável.

### Avatar

O avatar da persona é:

1. assinatura visual;
2. porta de entrada para conversar com aquela persona.

Quando fizer sentido, o chat deve abrir **contextualizado ao conteúdo do widget**.

---

## 5. REGENERATE — agência sobre a sorte

Widgets generativos podem oferecer regenerate.

A lógica conceitual é:

- geração inicial = **sorte**;
- Regenerate #1 = “não foi exatamente isso; me realinhe”;
- Regenerate #2 = última chance;
- máximo de **3 resultados por widget/dia**;
- não repetir conteúdo dentro do mesmo ciclo.

No MVP, a transição pode ser apenas um fade.

### Importante

Regenerate não existe para permitir que a Odara fique procurando infinitamente a opção perfeita.

É uma pequena quantidade de **agência sobre a sorte**.

---

# 6. CONTRATOS DOS CORE WIDGETS

## 6.1 Soundtrack — Bard

### Fechado

Mostrar somente:

- música;
- artista.

### Aberto

Mostrar:

- uma frase curta do Bard, com personalidade;
- ícone do Spotify;
- avatar do Bard;
- Regenerate.

Não escrever “Abrir Spotify” se o ícone já comunica essa ação.

---

## 6.2 Word of the Day — Claudio Catalão

### Fechado

Mostrar:

- ícone;
- palavra.

Não acumular:

- tradução;
- subtítulos;
- contexto;
- explicações.

### Aberto

Mostrar:

- tradução;
- contexto/uso;
- Regenerate;
- opção de regenerar especificamente em catalão;
- avatar do Claudio Catalão.

---

## 6.3 Mini Side Quest — Lore

Este é um dos pontos mais importantes do handoff.

### O que ele NÃO é

Não é:

- tarefa;
- obrigação;
- backlog disfarçado;
- lembrete;
- item que a Odara “não pode esquecer”.

Se ao olhar para a Side Quest a reação for:

> “Ah, merda, mais uma coisa que eu tenho que fazer.”
> 

o widget falhou.

### O que ele É

Uma pequena missão que deve provocar:

> “Hmm. Quero rolar esse dado e ver o que acontece.”
> 

Pode nascer de:

- backlog;
- sinais da vida;
- contexto recente;
- interesses;
- curiosidades;
- oportunidades.

Mas precisa ser **transformada em uma quest real**, com sensação de abertura, exploração ou surpresa.

### Aberto

Pode ser um pouco mais textual, mas continua curto e concreto.

Ações:

- Regenerate;
- avatar Lore;
- ✓ Done;
- ✕ Not done.

### Após conclusão

Uma Side Quest concluída pode ser passada para Lore com:

- contexto;
- evidência/prova quando existir;
- resultado.

No futuro isso pode alimentar:

- Memory Log;
- narrativa anual;
- histórico de aventuras.

### Regra crítica

**Nunca transformar automaticamente uma pendência em Mini Side Quest apenas trocando o nome.**

---

## 6.4 Flo — Healer

Flo é diferente porque **não é generativo**.

### Fechado

Mostrar apenas um estado visual simples.

Fora da janela relevante:

- símbolo neutro, por exemplo 🌙;
- sem explicação de fase na frente.

### Aberto

Pode mostrar:

- poucos bullets;
- interpretação prática;
- sugestões de autocuidado/orientação.

Evitar:

- texto clínico;
- artigo;
- afirmações categóricas;
- excesso de interpretação.

### Ações

- ícone do Flo → abre Flo;
- avatar do Healer → conversa contextualizada.

Não existe Regenerate.

O objetivo é **self-orientation**, não diagnóstico.

---

# 7. NIGHT SHIFT REPORT

Depois dos cards entra o:

**NIGHT SHIFT REPORT**

Isso não é um resumo de conversa.

É o **handoff operacional da Lori depois do Night Shift**.

Visualmente, pode se inspirar em:

- MMO chat;
- log de missão;
- sequência de entradas.

Cada entrada pode ter:

- avatar/ícone da persona;
- nota curta.

Não é necessário repetir o nome da persona se o avatar já o comunica.

### Registrar somente

- decisões;
- mudanças;
- handoffs;
- descobertas;
- trabalho efetivamente realizado.

### Não registrar

- cada passo interno;
- atividade mecânica;
- “Lori pesquisou X, abriu Y, clicou Z”.

A pergunta é:

> **“O que mudou no estado do Odyssey durante a noite?”**
> 

Deve existir:

**Ver log completo →**

que leva ao registro operacional completo no Notion.

O registro completo funciona como sistema de tickets:

**request → routing → owner → action → result → state**

---

# 8. RADAR / AGENDA

Depois do Night Shift vem o Radar.

A Agenda não deve parecer um calendário completo.

Ela deve responder:

> **“O que muda a forma como meu dia começa?”**
> 

Exemplos:

- 🔴 10:00 — Fortis
- 🟢 18:30 — Jantar
- 🌧️ Chuva à tarde

Priorizar:

- compromissos antes das 16h;
- compromissos pessoais relevantes;
- qualquer coisa que altere o início do dia;
- alertas meteorológicos relevantes.

Não despejar detalhes que já estão disponíveis no calendário.

---

# 9. TASK BACKLOG

Depois do Radar.

Objetivo:

> **olhar e entender rapidamente o estado das obrigações.**
> 

### Exibição

- Today + Week na mesma visão;
- data exata em cada tarefa;
- Today destacado;
- Month separado;
- Overdue como filtro separado;
- no mínimo: título + data + estado visual.

O título **Task Backlog** pode levar à tabela completa no Notion.

Uma tarefa individual só deve abrir uma página específica quando houver informação relevante ali.

Deve existir uma entrada clara para conversar com a Lori sobre tarefas.

### Bidirecionalidade

O fluxo esperado é:

**Notion → Bom Dia → Odara reage → Lori processa → Notion atualizado → próximo Bom Dia reflete o novo estado**

Exemplos naturais:

- “fiz essa”
- “move pra semana que vem”
- “isso não faz mais sentido”
- “preciso de ajuda”

A Lori deve transformar essa conversa em uma atualização real do sistema.

### Recorrências

Quando uma tarefa recorrente é realmente concluída, a próxima ocorrência deve ser calculada segundo o modelo de recorrência **a partir da data real de conclusão**, quando essa for a regra da tarefa.

Exemplo:

- tarefa a cada 14 dias;
- planejada para sexta;
- concluída hoje;
- próxima ocorrência = hoje + 14 dias.

A data antiga não deve congelar a recorrência.

### Arquitetura

Bom Dia **mostra o estado**.

Notion mantém:

- lógica;
- histórico;
- próximas datas;
- estado canônico.

A HTML do Bom Dia não deve virar o lugar onde a lógica de tarefas mora.

### Lori pet

Explorar a possibilidade de um pet operacional da Lori para Tasks/Obligations.

A ideia do fox é apenas candidata.

Nome, personalidade e identidade ainda não estão fechados.

O pet é uma **extensão da Lori**, não uma nova persona independente por padrão.

---

# 10. SCHEDULED TASK → LORI

Existe um requisito técnico a validar.

A experiência desejada é algo próximo de:

> “Tem um update para a Lori sobre o Bom Dia Cláudio de hoje: fiz X, Y vai para semana que vem…”
> 

Esse contexto deveria conseguir ser roteado/processado pela Lori sem exigir navegação manual.

**Não assumir que essa capacidade já existe.**

O Cláudio precisa validar:

- se a capacidade existe hoje;
- como o contexto chega à Lori;
- qual é o mecanismo de roteamento;
- quais limitações existem.

Se não existir, registrar como gap técnico — não improvisar uma solução falsa.

---

# 11. NEWS

Depois do Task Backlog:

- 🌍 World
- 🇪🇸 Spain
- 🏙️ Barcelona
- 🇧🇷 Brazil
- ✨ Good Things

Pergunta editorial:

> **“O que a Odara deveria saber hoje?”**
> 

### Prioridade

Não é quantidade de notícias.

É impacto real.

### Spain

Priorizar:

- imigração/residência;
- impostos;
- housing;
- trabalho;
- mobilidade/viagens;
- segurança;
- serviços;
- regras que afetem a vida prática.

### Barcelona / Catalonia

Priorizar:

- segurança;
- transporte;
- clima/interdições;
- housing;
- serviços;
- turismo quando relevante para residente.

### Brazil

Priorizar:

- mudanças que afetem brasileiros vivendo fora;
- impostos;
- documentos;
- regras;
- impactos pessoais relevantes.

### Formato

- headline real;
- link real para a fonte;
- micro-contexto somente quando especialmente relevante.

Exemplo:

> “Pode afetar brasileiros vivendo na Espanha.”
> 

### Source Registry

Ainda não está fechado.

Direção atual:

- Claudio Catalão ajuda a identificar bons canais de Barcelona/Catalonia;
- G1 é ponto inicial para Brasil;
- World usa busca ampla / fontes adequadas.

### Fallback

Cada seção deve seguir:

**fonte normal → retry → busca direta → estado de erro explícito**

Nunca:

**fonte falhou → seção desaparece**

---

# 12. GOOD THINGS

Objetivo:

> **lembrar que coisas boas e interessantes continuam acontecendo no mundo.**
> 

Não usar trivia minúscula apenas para preencher espaço.

Buscar histórias com peso real:

- grandes avanços científicos;
- saúde;
- meio ambiente;
- iniciativas relevantes;
- descobertas;
- histórias humanas importantes.

Formato:

**headline de uma linha + link**

Sem transformar em artigo.

---

# 13. TREASURES / POÇÕES

É a prateleira final.

Não é editorial.

É uma ponte para ação.

### Atual

**Gmail Sweep**

Ao clicar, abre a Skill/chat correspondente.

### Futuro

Pode receber outras Skills, por exemplo:

- property scan;
- outras ferramentas operacionais.

A shelf deve ser estável e pluggable.

**Bom Dia termina aqui.**

Não adicionar:

- card motivacional final;
- “have a great day”;
- mensagem de encerramento artificial.

A pessoa já deve estar orientada e pronta para viver o dia.

---

# 14. RESILIENCE — P0

Toda sessão/widget precisa seguir:

**Normal → Retry → Plan B → Error explícito**

### Regra

1. Tenta normalmente.
2. Falha → retry.
3. Mesma falha → Plan B.
4. Plan B falha → seção continua visível em estado de erro.
5. Nunca remover silenciosamente uma seção.

### Exemplos

Agenda:

- fallback para link direto do calendário.

Weather:

- fallback para fonte meteorológica direta.

News:

- fallback para busca web direta.

Falha total:

- erro contextual + caminho manual quando possível.

O erro deve parecer parte do produto:

- humano;
- claro;
- visualmente integrado.

Nunca mostrar erro técnico cru quando houver uma forma melhor de comunicar.

---

# 15. ARQUITETURA

Princípio:

> **“O Bom Dia mostra o estado. As personas mantêm o estado.”**
> 

HTML é interface.

Não é o sistema canônico.

### Não colocar no HTML

- lógica crítica;
- estado permanente;
- registries canônicos;
- histórico;
- regras de negócio que precisam sobreviver ao próximo run.

### Fonte de verdade

**Notion permanece source of truth** para:

- dados;
- configuração;
- registries;
- estado persistente;
- histórico operacional.

O HTML diário é uma representação daquele estado.

### Futuro

O Odyssey deve poder evoluir para um:

**Odyssey Live Dashboard**

— uma aplicação/site/servidor próprio onde o sistema possa rodar continuamente e ser comandado pelas IAs.

O MVP do Bom Dia não precisa resolver isso.

Mas a arquitetura **não deve bloquear essa evolução**.

---

# 16. PUBLICAÇÃO — P0

Nunca considerar a tarefa concluída apenas porque o HTML foi gerado.

Pipeline obrigatório:

**generate → validate → correct → validate again → publish → deliver**

### Smoke test mínimo

Antes de entregar:

- link abre;
- splash responde;
- card vira;
- Report aparece;
- widgets aparecem;
- interações essenciais funcionam;
- uma integração quebrada não derruba o board inteiro;
- fallback/error state aparece quando aplicável.

Se uma etapa falhar:

**corrigir antes de publicar.**

---

# 17. NÃO REGREDIR — LIÇÕES DOS RUNS ANTERIORES

Estas são falhas que já apareceram e não devem voltar.

### Não fazer

- entregar HTML sem smoke test;
- deixar o splash/card sem resposta;
- fazer widget desaparecer quando integração falha;
- hardcodar registries que deveriam vir do sistema canônico;
- adicionar/remover widgets por iniciativa própria;
- transformar Mini Side Quest em obrigação;
- colocar XP no card quando o contrato não pede;
- colocar texto demais no estado fechado;
- usar implementação divergente apenas porque “funciona”;
- tratar o Golden Run como nova especificação;
- depender apenas de memória do chat para decisões importantes;
- corrigir a especificação para justificar uma implementação errada;
- trocar a sensação do produto por uma interface genérica de dashboard;
- inventar funcionalidades técnicas não validadas.

### Caso especialmente importante

No run de 28/09, uma quest de saúde dizia essencialmente para **agendar uma consulta médica atrasada**.

O problema não é o tema “saúde”.

O problema é que a formulação transformou a Side Quest em uma obrigação.

Esse é exatamente o tipo de drift que o contrato deve impedir.

---

# 18. GOLDEN RUN — COMO USAR

O run de **28/09/2026** é uma referência comportamental/experiencial.

Preservar:

- sensação de diário de bordo;
- reveal;
- quatro cards;
- curadoria;
- atmosfera;
- Radar/Agenda;
- contexto de clima;
- sensação de que “algo foi preparado para mim”.

Não copiar automaticamente:

- HTML;
- estrutura técnica;
- CSS;
- nomes de classes;
- conteúdo;
- decisões que contrariem o Experience Spec.

**Golden Run = referência de feeling, não source of truth de implementação.**

---

# 19. O QUE AINDA NÃO ESTÁ DECIDIDO

Não inventar decisões para preencher gaps.

Ainda abertos:

- visual final;
- Source Registry definitivo;
- Plan Bs detalhados;
- identidade final do Lori pet;
- detalhes completos do Night Shift;
- detalhes do Gmail Sweep;
- lista futura de Treasures;
- detalhes técnicos Scheduled Task → Lori;
- schema final do Widget Registry;
- suite completa de testes;
- refinamentos visuais derivados do Golden Run.

Quando houver gap estrutural, **parar e sinalizar**, em vez de decidir silenciosamente.

---

# 20. ACCEPTANCE CRITERIA

A implementação pode ser considerada aderente quando:

- [ ]  A abertura começa com um único card fechado.
- [ ]  O card responde e revela o Report.
- [ ]  Os widgets são exibidos depois do reveal.
- [ ]  Existem os quatro Core Widgets configurados pelo registry.
- [ ]  Nenhum widget é adicionado/removido aleatoriamente.
- [ ]  Closed cards são glanceable.
- [ ]  Open cards oferecem a profundidade prevista.
- [ ]  Soundtrack respeita seu contrato.
- [ ]  Word of the Day respeita seu contrato.
- [ ]  Mini Side Quest é uma quest, não uma obrigação disfarçada.
- [ ]  Flo permanece não-generativo.
- [ ]  Night Shift Report registra mudanças/decisões, não atividade mecânica.
- [ ]  Radar funciona como radar, não como dump de calendário.
- [ ]  Task Backlog mostra estado e mantém a lógica fora do HTML.
- [ ]  Recorrências podem ser recalculadas a partir da conclusão real quando aplicável.
- [ ]  News seguem a curadoria e têm links reais.
- [ ]  Good Things existe como categoria significativa.
- [ ]  Treasures encerram o Bom Dia sem mensagem artificial.
- [ ]  Falhas seguem Normal → Retry → Plan B → Error.
- [ ]  Nenhuma seção desaparece silenciosamente.
- [ ]  O HTML não se torna source of truth.
- [ ]  Smoke test é executado antes da publicação.
- [ ]  Uma falha de integração não derruba a experiência inteira.

---

# 21. ORDEM DE IMPLEMENTAÇÃO RECOMENDADA

Não tentar resolver tudo simultaneamente.

### Fase 1 — Experience shell

- splash;
- reveal;
- Report;
- composição dos quatro widgets;
- closed/open contracts;
- mobile-first.

### Fase 2 — State + architecture

- Widget Registry;
- Skill/Persona ownership;
- Notion state;
- separação entre interface e lógica;
- configuração canônica.

### Fase 3 — Operational layers

- Night Shift;
- Radar;
- Task Backlog;
- Lori flow.

### Fase 4 — Discovery layers

- News;
- Good Things;
- Treasures.

### Fase 5 — Resilience

- retry;
- Plan B;
- error states;
- integration isolation.

### Fase 6 — Validation

- smoke test;
- visual QA;
- interaction QA;
- mobile QA;
- regression check contra este documento.

---

# 22. REGRA FINAL PARA O CLÁUDIO

Quando estiver em dúvida entre:

**“isso deixa o sistema mais completo”**

e

**“isso deixa a experiência mais leve, clara e confiável”**

a prioridade é a segunda.

Bom Dia não precisa mostrar tudo que o Odyssey sabe.

Precisa mostrar **o que vale a pena a Odara ver agora**.

E, quando alguma decisão nova for necessária, não alterar silenciosamente o contrato: **sinalizar o gap, propor a mudança e esperar decisão do PM/Gestão de Projeto.**

[⚓ Leitura do Mayor — Brief × implementação atual](%5BARCHIVE%5D%20Bom%20Dia%20Cl%C3%A1udio%20%E2%80%94%20Implementation%20Brief%20C/%E2%9A%93%20Leitura%20do%20Mayor%20%E2%80%94%20Brief%20%C3%97%20implementa%C3%A7%C3%A3o%20atual%203e9107b19b4981a28dffced93fed2538.md)