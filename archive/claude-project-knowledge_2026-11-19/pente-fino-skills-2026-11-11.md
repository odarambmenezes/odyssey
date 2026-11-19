---
name: pente-fino-skills-2026-11-11
description: Pente fino e limpeza do Skills Mapping em 11/11/2026 — o teste do gatilho da Odara, o estado final das 30 linhas (12 Active, 9 On Draft, 2 Paused, 7 Archived) e o que ficou pendente dela
sources: [chat]
---

# Pente fino e limpeza do Skills Mapping — 11/11/2026

Cada página aberta e lida. O critério saiu de uma observação da Odara sobre o Birthday Alert. **A limpeza foi aplicada na mesma noite** — este doc registra o critério e o estado final.

## O teste do gatilho

> "O Birthday Alert é quase como se fosse a database. A skill em si, eu acho que eu tenho que dar um trigger nela."

Formalizado:

- **Skill** — tem gatilho que a Odara *fala*, faz um método, entrega algo.
- **Workflow** — grupo organizado de **duas ou mais** skills.
- **Scheduled Task** — dispara no relógio, sem ela.
- **Não é skill** — é base (Source of Truth), ou é regra permanente, ou é só um passo dentro de outra coisa.

Dois sintomas de erro de classificação:

1. **Se a página é mais dado do que método**, é uma base vestida de skill.
2. **Se o "gatilho" é um lugar** ("roda dentro do Bom Dia") em vez de uma frase, não é gatilho — é posição.

## O que foi aplicado

### Renomeado para a fala dela

| Antes | Agora | Por quê |
|---|---|---|
| Cadence Queue (o que está pendente) | **O que tá pendente** | "Cadence Queue" é vocabulário do Codex, não fala dela. O nome novo bate com a Ação Rápida que já existia, o que mata a duplicata |
| Fechar item do Backlog (Completion Protocol) | **Marca como feito** | Mesma razão |
| Shopping List Workflow | **Lista de compras** | Deixou de ser Workflow |
| Recommendation Skill | **Recomendação de entretenimento** | "Skill" no nome de uma skill é redundante |

### Reclassificado de Workflow para Skill

- **Lista de compras** — Steps tinha 1 item, e esse item era só ideia.
- **Recap Session** — Steps tinha 0. Absorveu o Annual Retrospectives como **modo longo** (junho e dezembro).

### Base separada do método

- **Birthday Alert → "Presente & mensagem de aniversário".** Gatilho novo e real: *"me ajuda com o presente da Flavi"*, *"o que eu mando pro Iago"*. A lista de 30 nomes com vínculos ficou explicitamente marcada como **base que vive na página de Aniversários**, não na skill. O aviso automático continua saindo no "bom dia" e no Pit Stop.
- **Odara's Voice** — o perfil já estava isolado num toggle, o que torna a separação fácil. **Não separei:** criar uma SoT nova é decisão de colocação (G21). Nota de pendência deixada na página.
- **Diário Pessoal** — mesmo caso. Nota deixada; o comportamento já é regra 12 do Charter.

### Arquivado

| Linha | Motivo |
|---|---|
| **Annual Retrospectives** | Fundida no Recap Session como modo longo. Página estava em branco e a Mission tinha sido escrita por mim horas antes |
| **Gerar lista de compras interativa** | É ideia, não skill. A própria página dizia "não ativar nem abrir sprint agora". Destino: 🌊 Future Horizons |
| **Deadline Alert** | Nunca construída, travada em mecanismo de notificação. Coberta na prática pelo "O que tá pendente" + Bom Dia |

### Correções de texto

- "Lore" → **Lori** no corpo da Noticeboard Clean-up e no Use Cases do Hand Off (Crew Mapping é o roster oficial).
- **Noticeboard Clean-up** deixou de recitar o stale check e o protocolo de fechar nota — agora aponta para a página do Crew Noticeboard, onde o protocolo mora.
- **Create a New Persona** ganhou nota explicando que fica fora do template de propósito (é playbook de 11 seções, não runbook) e listando o que está velho: cita C-Staff e Treasure, os dois arquivados, e trata ChatGPT e Claude como donos separados.
- **Recomendação de entretenimento** saiu de página em branco para draft completo no template.

### Correção de um erro meu

Eu havia escrito que o **Weekly Pit Stop** tinha só 1 step. Errado: "O que tá pendente", "Marca como feito" e "Presente & mensagem de aniversário" todos listam o Pit Stop em `Part of`, então ele tem **3 steps** e é workflow de verdade.

## Estado final: 30 linhas

### Active (12)

**Skills (11):** O que tá pendente · Marca como feito · Triage · Carta do Dia · Side Quest Generator · Odara's Voice · Gmail Sweep · Lista de compras · Presente & mensagem de aniversário · Diário Pessoal · Create a New Persona

**Workflow (1):** Bom Dia Claude

Dessas, **9 são disparáveis hoje sem ressalva**. Create a New Persona depende de decisão de formato; Diário Pessoal e Presente & mensagem carregam a pendência de separar a base.

### On Draft (9)

**Skills (6):** Hand Off to Persona · Leave a Note for a Persona · Noticeboard Clean-up · Cap's Journey · Recap Session · Recomendação de entretenimento

**Workflows (3):** Weekly Pit Stop · GM Check-in (Ad Hoc) · Meal Routine

### Paused (2)

Card Pull of the Day · Manutenção Diária do Backlog (auto-revival) — tipo correto, destino amarrado a decisões já registradas.

### Archived (7)

Night Shift · Mesa do Time Weekly Board Clean-up · Good Time Radar · Deadline Alert · Annual Retrospectives · Gerar lista de compras interativa · TEMPLATE - SKILL

## Ficou pendente da Odara

1. **Separar as duas bases.** Perfil de Voz e Lista de Aniversários deveriam virar Source of Truth registradas, com dona. Depende de decisão de colocação (G21).
2. **Ações Rápidas.** Viram vitrine apontando para as skills, ou seguem registro paralelo? Hoje Gmail Sweep e "O que tá pendente" existem nos dois lugares, e o Gmail Sweep se contradiz: a Ação diz "blocos de 2-4", o Mission da skill diz "lotes de 5".
3. **Create a New Persona.** Enxugar para runbook com o playbook linkado, ou assumir como exceção?
4. **GM Check-in × Bom Dia.** Os dois fazem fila + Wildcard. A diferença é peso narrativo. Separar de verdade ou fundir?
5. **Perfil de Entretenimento.** A Recomendação precisa dessa fonte para não recomeçar do zero toda vez. É citado como ilha do Command Center mas não achei a página.
6. **Side Quest On-Demand.** A página antiga e a linha têm o motor escrito nas duas. Aposentar a página ou virar ponteiro.
