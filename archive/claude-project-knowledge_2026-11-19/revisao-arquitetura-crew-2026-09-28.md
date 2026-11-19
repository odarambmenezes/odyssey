---
name: revisao-arquitetura-crew-2026-09-28
description: Revisão do Mayor sobre "Odyssey Organizational & Communication Structure — Experimental" (28/09) — compatibilidade, contrato mínimo de comunicação, piloto Night Shift, par Corsair↔Keymaster, modelo de acesso, plano MVP-safe e riscos. Nada implementado.
sources: [chat]
---

# Revisão de arquitetura — Crew como um sistema só

**Data:** 2026-09-28 · **Autor:** Mayor · **Status:** proposta para revisão — nada implementado.
**Lido:** página 🏢 Organizational & Communication Structure, Mesa do Time, Governance (Trust Boundary, Signals, Change Protocol), AI Crew Architecture, Capability Model, os 3 Scheduled Tasks ativos, definição em andamento da Lorekeeper e critérios atuais da busca de casa.

---

## 0. A restrição física que define todo o desenho

Antes de tudo, um fato técnico que muda o desenho:

> **Chats não conversam entre si e não "acordam" sozinhos.** Um chat de Persona só age quando a Odara abre ele. As únicas partes da Odyssey que agem sem ela são os **Scheduled Tasks**, e o único meio que todos leem é o **Notion**.

Consequências:
- "Persona A ↔ Persona B" na prática significa: **A escreve num lugar do Notion que B lê** — ou um Task assume o papel das duas na mesma execução.
- O **Night Shift precisa ser um Scheduled Task**, não um chat. Ele pode "vestir" qualquer Persona lendo a página de definição dela + as Sources of Truth dela. Os chats das Personas não precisam estar abertos pra trabalho ser preparado.
- Isso é uma boa notícia: o roteamento pode acontecer sem a Odara, e sem construir infraestrutura nova — só um Task + uma página.

---

## 1. Compatibilidade com o que já existe

**Já sustenta o modelo (reusar):**
| Peça existente | Papel no novo modelo |
|---|---|
| Trust Boundary (Governance) | Já separa leitura compartilhada × mutação restrita — é a base do modelo de acesso |
| Capability Model | Night Shift = **Task** que dispara um **Workflow**; Bom Dia = entrada/entrega. Não precisa de categoria nova |
| Scheduled Tasks (3 rodando) | Prova que execução noturna autônoma já funciona (Manutenção roda às 8h, sem ninguém) |
| Diário Pessoal (DB, campo "Origem (chat)") | Candidato natural a **caixa de captura do dia** — já existe, já tem origem por chat |
| Mesa do Time | Canal Crew↔Crew pra recados **não íntimos** (Chatty lê) |
| Odyssey Signals inbox | Canal de conhecimento sobre a Odara (vazio até agora) |
| Páginas de Persona no Notion | Lugar onde o contrato de cada Persona pode morar (seção curta, sem DB novo) |
| Bom Dia (pré-voo SQL por Status=Ativo) | Padrão pronto pra "ler o que a Crew preparou se existir, senão seguir normal" |

**O que hoje impede:**
- Nenhum chat escreve "isso interessa a outra Persona" em lugar nenhum — a informação morre no chat onde nasceu.
- Não existe Task noturno nem lugar onde a saída de um turno fique.
- Mesa do Time depende de a Odara dizer "olha a Mesa" — ela continua sendo o gatilho.
- A limpeza automática da Mesa (regra 5) **não está implementada**: o prompt da Manutenção Diária só faz auto-revival e diz explicitamente "não toque em nenhuma outra parte do Notion".
- O Bom Dia roda às **11h30** (cron sem fuso) com prompt de 05/09 — "curar de manhã" hoje é "curar no fim da manhã".

**O que seria perigoso introduzir cedo:**
- Um banco de "mensagens entre Personas" (vira Slack, vira manutenção).
- Todas as Personas plugadas de uma vez.
- Night Shift com ações externas (e-mails, mensagens) antes de validar a qualidade da triagem.
- Diário cru circulando pra outras Personas.
- Mudar o Bom Dia de produção antes do Night Shift provar que gera algo útil.

---

## 2. O que falta (mínimo)

1. **Uma saída do turno:** uma página "🌙 Night Shift — Diário de Turno" (página, não banco).
2. **Um Task noturno** (Night Shift) com conectores mínimos.
3. **Um formato de pacote** padrão (seção 3).
4. **Um contrato curto por Persona** — só pra Lorekeeper, Keymaster e Corsair no piloto.
5. **Uma lista de autorizações permanentes** (o que pode ser executado sem perguntar de novo) — hoje isso está espalhado em memória e conversa.
6. **Esclarecimento de papel:** "Hacker, The Good" não está no roster canônico. Pela descrição é Builder, não Crew — registrar como Builder quando a Odara decidir, não criar agora.

---

## 3. Contrato mínimo de comunicação

### 3a. Cartão de contrato (uma seção curta na página de cada Persona)
```
🔌 Contrato de Comunicação
Domínio:            o que é meu
Coordenação:        Lorekeeper (vida) | Mayor+ChatGPT (sistema)
Pares:              quem + pra quê (1 linha cada)
Escala pra:         quando cruza fronteira → quem
Recebe:             que tipo de informação me faz agir diferente
Entrega:            o que eu produzo e onde deixo
Lê:                 nível de acesso (Aberto / Crew / Íntimo)
Executa sem perguntar: autorizações permanentes (lista explícita)
Nunca:              limites
```
Uma Persona nova "entra na rede" preenchendo esse cartão. Ninguém liga Persona com Persona manualmente.

### 3b. Formato do pacote (qualquer roteamento usa isso)
```
[De → Para] · DD/MM · Sensibilidade: Aberto | Crew | Íntimo
Por que você:     1 linha
O que precisa saber: até 3 linhas (já filtrado pro domínio)
Pedido:           só saber | preparar X | levar à Odara
Prazo:            se houver
Origem:           link
```

### 3c. Regra de roteamento
> **Rotear só se o destinatário agiria diferente sabendo disso.** Sem pacote = Persona não é incomodada.

Máximo de 1 pacote por Persona por noite (consolida). Dúvida sobre relevância → não roteia, anota no turno.

---

## 4. Fluxo do Night Shift (piloto)

```
DIA
Odara conversa com Lorekeeper (ou outro chat)
  → o chat registra 1 linha no Diário Pessoal quando algo cruza domínio
    (Origem = chat, Tipo existente, Resumo filtrado)

NOITE (Task, ~03:00 Madrid)
1. Lê: Diário Pessoal (últimas 24h) · Mesa ativa · Backlog 🔺/itens do domínio piloto
2. Decide relevância por Persona (regra 3c)
3. Pro piloto: "veste" Keymaster → prepara trabalho (seção 5)
                "veste" Corsair  → revisa como par
4. Escreve no Diário de Turno:
   • Pacotes por Persona (formato 3b)
   • "Pro Bom Dia": até 3 itens curados + "já resolvido" + "precisa de você"
   • Fios em aberto (o que não foi roteado e por quê)
5. Silencioso: sem push, sem e-mail, sem mudança estrutural

MANHÃ
Bom Dia lê a entrada de hoje SE existir → 1 bloco "A casa em ordem"
  ("Me conta o que importa" = 3 itens · "Quero ver tudo" = link pro turno)
Se não existir → roda exatamente como hoje (fail-safe)
```

**Onde a Odara ainda é gargalo (honesto):**
| Ponto | Continua dependendo dela? | Por quê |
|---|---|---|
| Handoff interno entre Personas | **Não** | Night Shift roteia sem aprovação |
| Preparar trabalho (pesquisa, shortlist) | **Não** | Task executa workflow já acordado |
| Captura durante o dia | **Parcial** | Só entra o que algum chat registrou; conversa que não gera registro some |
| Ação externa (e-mail a agência) | **Sim, até ativar autorização permanente** | Fronteira externa protegida |
| Decisão de vida (visitar, aplicar) | **Sim, por design** | Agência dela |
| Mudança estrutural | **Sim → Builders** | Trust Boundary |
| Chatty ↔ Claude | **Sim** ("olha a Mesa") | Fora do escopo deste piloto |

---

## 5. Par Catalan Corsair ↔ Keymaster

**Por que esse par é o piloto certo:** tem necessidade real e urgente (contrato longo, Rígido 22/10, empadronamiento 🔺), critérios já definidos, conector do idealista disponível, e um caso concreto onde um sozinho erra: a Odara recusou um apê ótimo no leste de Poblenou porque a rua era vazia — **o Keymaster não sabe disso, o Corsair sabe.**

**Contrato do par:**
| | Keymaster (Clau) | Catalan Corsair (Jaume) |
|---|---|---|
| Traz | anúncio, preço, m², contrato, pet, documentação, riscos de contrato | rua viva ou morta, o que abre perto, deslocamento real, como é morar ali |
| Pede ao par | "esse endereço passa no teste de vida?" | "esse bairro tem oferta dentro do orçamento?" |
| Decide sozinho | se o anúncio atende aos critérios objetivos | se o bairro combina com o jeito que ela vive |
| Veto | contrato de temporada (mata empadronamiento) | rua sem vida / volta de madrugada ruim |
| Discordância | vai pra Odara como **opção com os dois olhares**, nunca resolvida em silêncio |

**Saída no Bom Dia:** "🏠 Casa — 3 opções" com uma linha do Clau (contrato/preço) e uma do Jaume (bairro). Nada é contatado no piloto.

**Não é hierarquia:** nenhum dos dois reporta ao outro; os dois são coordenados pela Lorekeeper só no sentido de "ela sabe que isso está acontecendo".

---

## 6. Modelo de acesso e autoridade (proposta, não implementar)

**Três níveis de sensibilidade:**
| Nível | O que é | Quem lê |
|---|---|---|
| 🟢 Aberto | Operacional, sem intimidade (Backlog, Shopping, Radar, Mesa) | Crew + Builders + Chatty |
| 🟡 Crew | Contexto pessoal não íntimo (preferências, critérios de casa, rotina) | Crew + Builders do lado Claude |
| 🔴 Íntimo | Diário cru, saúde, ciclo, emoção, "criança fragilizada" | Lorekeeper e Healer; os outros só recebem **insight derivado** |

**Seis direitos, separados:**
| Direito | Quem |
|---|---|
| Ler | Todos no seu nível (leitura ampla é recurso — Trust Boundary) |
| Escrever dados do próprio domínio | A Persona dona + Completion Protocol no Backlog |
| Propor | Qualquer um → Ideas Intake (sistema) ou Signals (sobre a Odara) |
| Executar workflow acordado | Persona/Task, dentro das autorizações permanentes |
| Ação externa | Só com autorização permanente por tipo de ação, ou pedido explícito |
| Mutar estrutura | Só Builders |

**Autorizações permanentes (registro explícito, uma linha cada):** por exemplo, "Keymaster pode mandar 1º contato informativo a agências, sem follow-up, nunca decidindo por ela" — a Odara já autorizou isso em 27/09; hoje só vive em memória de conversa. **Proposta:** registrar, mas manter **desligada durante o piloto**.

**Lorekeeper Steward:** coordena, não manda. Não edita página de outra Persona; se houver atrito, leva ao Builder.

---

## 7. Plano de implementação MVP-safe

**Fase 0 — Decisão (sem build)**
Odara aprova o contrato + o piloto. Mayor registra no Decision Log como **experimental**, com critério de sucesso e prazo.

**Fase 1 — Modo sombra (5 noites)**
- Criar 1 página: "🌙 Night Shift — Diário de Turno" (Crew-only, não compartilhar com Chatty).
- Criar 1 Scheduled Task "Night Shift (piloto)" às 03:00 Madrid (com `CRON_TZ`), conectores **só Notion + idealista**.
- Adicionar o cartão de contrato em 3 páginas: Lorekeeper, Keymaster, Corsair.
- Instruir o chat da Lorekeeper a registrar 1 linha no Diário Pessoal quando algo cruza domínio.
- **Bom Dia não é tocado.** Sem push, sem e-mail. A Odara pode ler o turno ou ignorar.

**Critério de sucesso da Fase 1:** em 5 noites, pelo menos 3 entradas em que a Odara diria "isso me poupou trabalho", e nenhuma com vazamento de conteúdo íntimo ou ruído.

**Fase 2 — Entrega**
Na revisão do Bom Dia (já em curso): 1 leitura opcional do turno do dia → bloco "A casa em ordem". Fail-safe se não houver turno. Aproveitar para corrigir o horário (11h30 → decidir).

**Fase 3 — Autorização externa**
Só depois de a shortlist ser boa: ligar a autorização permanente do Keymaster (1º contato informativo).

**Fase 4 — Replicar**
Só então outras Personas preenchem o cartão. Nenhuma ligação manual.

**Parar se:** o piloto exigir banco novo, mudança de Governance, mudança no Command Center, ou se a Odara começar a revisar o turno por obrigação.

---

## 8. Riscos e modos de falha

| Risco | Como aparece | Mitigação |
|---|---|---|
| Vazamento íntimo | Diário cru vira pacote pro Keymaster | Pacotes só com insight derivado; nível 🔴 nunca sai da Lorekeeper |
| Ruído / Slack | Pacote pra todo mundo toda noite | Regra "agiria diferente?" + 1 pacote/Persona/noite + fios em aberto |
| Captura vazia | Nada registrado no dia → turno vazio | Aceitável; turno vazio = "nada a fazer", não erro |
| Night Shift monolítico | Task vira "faz tudo" | Piloto = 1 Persona + 1 par; replicar por contrato, não por inchaço do prompt |
| Autoridade difusa | Lorekeeper começa a "decidir" | Coordena ≠ manda; estrutura só Builders |
| Confusão de identidade | Duas Lorekeepers (canônica × Steward) | Steward = modo/extensão documentada da mesma Persona, não um chat novo |
| Mais uma coisa pra ler | Diário de Turno vira dever | Odara não precisa abrir; Bom Dia entrega o resumo |
| Ação externa precoce | E-mail enviado com critério errado | Autorização desligada até Fase 3 |
| Fuso horário | Task noturno roda às 5h ou 1h | Sempre `CRON_TZ=Europe/Madrid` |
| Governance contraditória | 3 versões de quem decide estrutura | Resolver antes da Fase 4 (já apontado na auditoria de 27/09) |

---

## 9. O que NÃO construir ainda

- Banco de mensagens entre Personas.
- Contratos para as 9 Personas.
- Qualquer mudança no Command Center.
- Push/notificação do Night Shift.
- E-mails automáticos (autorização permanente fica desligada).
- Roteamento Chatty ↔ Claude automático.
- Modelo de permissões técnico (é convenção de prompt por enquanto).
- Persona nova (incluindo formalizar "Hacker" como Persona).
- Um segundo chat de Lorekeeper.

---

> **A Odyssey pode pensar junto. Não muda a si mesma junto.**
> Piloto mínimo = 1 página + 1 Task + 3 cartões de contrato + 0 mudança em produção.
