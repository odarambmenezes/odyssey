---
name: auditoria-task-backlog-2026-11-11
description: Auditoria da estrutura do Task Backlog em 11/11/2026 — o que o auto-revival faria se religasse, os 32 itens com prazo no passado, o cluster 🔺 parado e os 6 problemas estruturais. Nada foi alterado.
sources: [chat]
---

# Auditoria do Task Backlog — 11/11/2026

Database: https://app.notion.com/p/c72071d037784ba5b6308c82a5a36d07 · data source `collection://a4f2dc93-71ae-44c6-8049-b2cd8f752220`

**Nada foi alterado nesta auditoria.** GM Charter regra 14: sempre perguntar antes de mudar o Backlog.

## Tamanho

74 linhas: 50 Obligations (36 A Fazer · 6 Feito (Ciclo) · 6 Done · 2 Em Pausa) e 24 Quests (22 A Fazer · 1 Em Andamento · 1 Done). Nenhuma em Aguardando Terceiros.

## 1. A database está dentro de "To be trashed"

Caminho real: `Project Odyssey / Odyssey - Architecture Overview / 05 A Jornada / 🗂️ Archive / To be trashed / Codex / Odyssey — Backlog de Tarefas`.

É a única que existe (busca no workspace confirma) e é a que as instruções do projeto citam como fonte de verdade. Se alguém esvaziar "To be trashed", o backlog vivo vai com ele. Mover é mudança estrutural (G21), então fica para a Odara decidir.

## 2. O auto-revival é seguro de religar

A regra do Codex vira **Feito (Ciclo)** → **A Fazer** quando o Próximo Deadline já passou. Hoje isso atingiria exatamente 4 linhas, todas domésticas e com cerca de um mês de atraso:

| Item | Recorrência | Última vez | Deadline |
|---|---|---|---|
| Limpar o Banheiro | Mensal | 06/09 | 06/10 |
| Lavar Roupa de Banho | Mensal | 07/09 | 07/10 |
| Lavar Roupa de Cama | Mensal | 07/09 | 07/10 |
| Hidratar o Cabelo | Mensal | 10/09 | 10/10 |

Ficam de fora (deadline no futuro): Conferir assinaturas recorrentes (23/11) e Cortar o cabelo (10/12).

**Conclusão:** o medo de "jogar um monte de coisa pra A Fazer de uma vez" não se confirma. O auto-revival nunca foi o problema.

## 3. O problema real: 32 linhas com prazo no passado, que nenhum mecanismo toca

Essas já estão em **A Fazer**. O auto-revival não as alcança, porque ele só mexe em Feito (Ciclo).

**Recorrentes travadas (17):** Pedicure combo (04/09) · Limpar o Quarto (05/09) · Blondor (09/09) · Tirar a Sobrancelha (11/09) · Cortar as unhas (11/09) · Registrar no Diário Pessoal (11/09) · Arrumar o Quarto (17/09) · Check-up do Mês (17/09) · os 7 "Agendar [especialista]" (18/09) · Pagar contas mensais (01/10) · Treino na Academia (10/09).

**Pontuais e sem recorrência (15):** Resolver Stremio · as 4 de responder mensagem (10/09) · Decidir SIBMOL · 🔺 coral em inglês · organizar agendamentos médicos · piscina · aula presencial · Long Term Contract · Empadronamiento · 🔺 clínico geral DKV · invisalign · Procurar um Esporte.

## 4. Os 4 Rígidos vencidos

Rigidez **Rígido** quer dizer parede, não janela. Todos vencidos:

| Item | Deadline | Atraso | Status |
|---|---|---|---|
| Pagar contas mensais | 01/10 | 41 dias | A Fazer |
| Encontrar um Long Term Contract | 22/10 | 20 dias | A Fazer |
| Empadronamiento | 22/10 | 20 dias | **Em Pausa** |
| 🔺 Marcar clínico geral pelo plano DKV | 30/10 | 12 dias | A Fazer |

Mais dois de Life in Spain sem prazo nenhum: **TSI / Saúde Pública (CatSalut)** (Em Pausa, Rígido) e **Verificar TIE e passos administrativos após o passaporte novo** (sem data). Pela regra 8 do GM Charter, status legal na Espanha tem prioridade elevada; esses quatro itens de Life in Spain estão todos parados ou sem data.

## 5. Problemas estruturais

1. **9 Obligations sem Recorrência.** O Codex exige Recorrência para Obligation. Sem ela a Cadence Queue não calcula nada: a linha nunca "vence" sozinha. São: Málaga, Retomar projeto parado, as 4 de responder mensagem, SIBMOL, coral em inglês, agendamentos médicos. Mais 2 em "A definir" (Nutricionista, CNH).
2. **Duplicatas.** "Renovar Passaporte Brasileiro" (Admin) × "Renovar passaporte brasileiro (Consulado de Barcelona)" (Life in Spain) — mesmo prazo 14/03/2027. E "Procurar aula de canto / coral em Barcelona" × "🔺 Procurar mais aulas de coral (preferência em inglês)".
3. **Categoria mistura dois eixos.** O select Categoria tem áreas da vida (Home, Health…) e também Main Quest e Side Quest, que são tipo de item e já vivem em Tipo. Resultado: "Encontrar um Long Term Contract" é Tipo=Obligation com Categoria=Main Quest. As views Tasks e Quests dependem dessa mistura para filtrar.
4. **10 linhas "[Cap]" são tarefa de construção fantasiadas de Quest.** Tipo=Quest, Categoria=Travel, Pontual, sem prazo. Ficam no pool de onde o Wildcard sorteia, então em teoria o GM pode entregar "[Cap] Confirmar o bloqueio de trilha" como Side Quest do dia. Uma delas, "[Cap] Registrar Cap's Journey no Skills Mapping", foi concluída em 11/11.
5. **O holofote das Main Quests nunca rodou.** As 8 linhas de Categoria=Main Quest têm "Última Side Quest Recebida" vazia. É o campo que alimenta o holofote orgânico do motor de Side Quest (Playbook, Side Quest Path). Sem ele o modo "Ancorada em Main Quest" não tem como escolher qual Quest merece holofote.
6. **Pontual + Flexível + sem data = invisível.** Umas 14 linhas (coral, TIE, Scanner Mode e as [Cap]) não têm prazo e não têm recorrência, então nenhum check-in as faz aparecer. Só aparecem se a Odara abrir o backlog na mão.

## 6. Pequenas inconsistências

- A Playbook lista 6 Main Quests ativas; o backlog tem 8 linhas de Categoria=Main Quest (as 6 mais "Procurar um Esporte" e "Encontrar um Long Term Contract").
- "Planejar viagem para Málaga (provavelmente outubro)" — a viagem pela Andaluzia aconteceu de 19 a 28/10. A linha é histórico.
- "Responder ao pessoal sobre ida à casa deles hoje" — o "hoje" era 10/09.
