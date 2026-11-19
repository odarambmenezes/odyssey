# [ARCHIVE] Schedule Task Governance v1

> **Status:** 🟢 Estrutura aprovada pela Odara em 28/09/2026 (Hacker = Schedule Task Steward). Parâmetros operacionais (teto, módulos, consolidações) seguem em calibração pelo Hacker com dados reais. Mudanças nesta governança em si escalam para o Mayor. O inventário e as regras valem desde já; as consolidações só acontecem depois do piloto Night Shift (a partir de 04/10).
> 

> 
> 

> Chat do Hacker: [https://claude.ai/chat/0595d281-b565-4340-a2f7-86a1ba44c8d6](https://claude.ai/chat/0595d281-b565-4340-a2f7-86a1ba44c8d6) (link privado).
> 

> **Princípio (Odara, 28/09):** Antes de criar uma nova execução agendada, a Odyssey deve verificar se o trabalho pode ser resolvido por uma Skill, um Workflow ou um módulo de uma execução existente. O objetivo é maximizar trabalho útil por execução, não multiplicar Tasks.
> 

> 
> 

> **A pergunta não é "isso pode ser uma Task?". É "isso precisa consumir uma execução agendada?"**
> 

> 
> 

> **Padrão:** horário fixo + módulos é a primeira opção a explorar, sempre, antes de qualquer execução nova.
> 

> **Maximize useful work per scheduled execution.**
> 

# 1. Orçamento

- **Teto técnico:** ≈ 5 execuções agendadas por dia no plano Pro (anúncio de lançamento; pode mudar). O limite é de **execuções por dia**, não de Tasks existentes.
- **Teto de operação (regra da casa): 3 por dia em regime normal.** As outras 2 ficam de reserva para reexecução, teste e imprevisto. **Política inicial de segurança, não definitiva:** o Hacker recalibra depois de medir consumo real, custo dos módulos e comportamento do piloto.
- **Disparo manual também gasta** ("rodar agora", testes). Teste de Task: preferir simulação no chat; disparo real só quando necessário.
- Hoje: **3/dia**, **4 nos dias 1 e 15** → acima do teto de operação nesses dias.

# 2. Inventário (28/09)

| Task | Owner operacional | Horário real (Madri) | Execuções/mês | Fala com a Odara? | Modelo | Notas do Steward |
| --- | --- | --- | --- | --- | --- | --- |
| 🌙 Night Shift — Piloto | Lore (op.) · Mayor (estrutura) | 05:00 (com fuso ✅) | ~30 | não (via Bom Dia) | Opus 5.5 | piloto até 03/10; modelo herdado, não escolhido |
| 🧹 Manutenção Diária | sem dono (sistema) | 08:00 — **cron sem fuso** | ~30 | não | Sonnet 5 | só auto-revival; idempotente; ideal para virar módulo |
| ☀️ Bom Dia (Card Pull of the Day) | a definir (Lore candidata) | 11:30 — **cron sem fuso** | ~30 | **sim** (entrega) | Sonnet 4.6 | superfície compartilhada; fica separado |
| 🎵 Radar de Shows | Bard | dias 1 e 15, 09:47 (com fuso ✅) | 2 | push só com novidade | Sonnet 5 | scan longo (~38 itens); medir duração no 1º run (01/10) |

**Total:** ~92 execuções/mês · pico 4/dia.

### ⚠️ Achados de saúde técnica

1. **Horário de verão (urgente até 25/10):** Bom Dia e Manutenção estão em UTC. Quando a Espanha sair do horário de verão (25/10), o **Bom Dia passa a chegar às 10:30** e a Manutenção às 07:00, sem ninguém mexer. Correção: fixar `CRON_TZ=Europe/Madrid` com o horário que a Odara quiser.
2. **Conectores demais:** cada Task carrega 10–20 conectores, incluindo BigQuery, Wix, ClickUp e Economic Index, que o Odyssey não usa. Pela fronteira externa protegida, cada Task deveria ter só o que usa. A ferramenta atual não permite limpar isso; precisa ser feito na tela de configurações.
3. **Mistura de modelos:** Opus 5.5 / Sonnet 5 / Sonnet 4.6 sem critério definido. Modelo é escolha da Odara; o Steward só recomenda.
4. **Limpeza da Mesa do Time prometida e inexistente:** vira módulo diário (abaixo), não Task.

# 3. Precisa consumir uma execução agendada? (árvore de decisão)

1. **Precisa acontecer sem a Odara abrir nada?** Não → Skill / Treasure ad hoc. **0 execuções.**
2. **Pode acontecer em algum momento de um período que um slot já cobre** ("toda madrugada", "toda segunda", "dia 1")? Sim → **módulo de um slot existente. 0 execuções novas.**
3. **É pesado, arriscado, ou precisa de conectores/modelo diferentes do slot?** Sim → candidata a Task própria.
4. **Cabe no teto de operação (3/dia)?** Não → consolidar algo antes; se não der, vai ao Captain's Council (e a Odara decide se compra uso extra).
5. **Vai notificar a Odara fora do Bom Dia?** Passa também pelo orçamento de interrupção.

# 4. Fluxo de proposta

1. **Persona identifica** a necessidade e cria uma linha no roster: Type = Schedule Task, Status = Draft, Dono = ela. No corpo: *o que precisa acontecer · quando · por quê · o que acontece se atrasar um dia.*
2. Deixa recado na Mesa do Time (→ Hacker).
3. **Hacker avalia** com a árvore e decide: ad hoc · módulo do slot X · Task nova · não agora (com motivo).
4. **Mayor** só entra se a decisão mexer em superfície compartilhada. **Odara** só entra se estourar o orçamento.
5. A Persona continua dona do **resultado**; o Hacker é dono do **slot**.

# 4b. Autoridade do Steward × autoridade estrutural

| O Hacker (Schedule Steward) pode | Escala para o Mayor (Structural Authority) |
| --- | --- |
| Aprovar, rejeitar ou redirecionar propostas de Task | Mudar esta governança: critérios, política de teto, papéis, o padrão slot + módulos como regra |
| Consolidar, mover módulos entre slots, aposentar Tasks sem uso | Criar ou mudar superfície compartilhada (Bom Dia, Noticeboard, Command Center, Backlog) |
| Ajustar horário, frequência, fuso e conectores dentro das regras | Qualquer coisa que altere como o sistema inteiro funciona |
| Discordar de uma Persona e explicar o porquê | — |

Nenhuma Persona cria ou altera Schedule Task diretamente sem passar pelo Hacker. Modelo de uma Task continua sendo escolha da Odara.

# 5. Bulk schedules — avaliação do Steward

**Veredito: sim, agregar — mas como "slot + módulos", não como um prompt gigante.**

| A favor | Contra | Mitigação |
| --- | --- | --- |
| Economiza execuções | Uma falha pode derrubar tudo | Módulos isolados: cada um roda, registra e segue; falha de um não para os outros |
| Lê o contexto (Notion) uma vez só | Execução longa, risco de estourar tempo/contexto | Módulo pesado fica fora do slot diário |
| Um lugar só para observar | Todos os conectores juntos na mesma execução | Slot só carrega módulos com necessidades parecidas |
| Narrativa natural ("turno") | Prompt vira monstro; ownership embaralha | O prompt do slot é curto e estável; as instruções de cada módulo moram na página da Persona dona |

**Descoberta principal:** não precisamos de Tasks separadas diária/semanal/quinzenal/mensal. **Um slot diário consegue rodar módulos de qualquer cadência** checando a data ("hoje é segunda?", "dia 1 ou 15?", "último domingo?"). Só se abre outro slot quando duração ou risco exigirem.

**Slot** = Task do sistema (Steward: Hacker). **Módulo** = trabalho de uma Persona (dono: a Persona), com cadência, entrada, saída e limites escritos na página dela.

# 6. Direção a validar (depois do piloto) — não é decisão fechada

*Cada módulo abaixo é hipótese. Só entra depois de o Hacker validar com dados do piloto e registrar no Decision Log.*

**Slot 1 — 🌙 Night Shift / Operação Diária, 05:00**

| Módulo | Dono | Cadência |
| --- | --- | --- |
| Manutenção do Backlog (auto-revival) | sistema | diário |
| Limpeza da Mesa do Time (recados > 3 dias → Arquivo) | sistema | diário |
| Roteamento da Lore (Entrada → Noticeboard) | Lore | diário |
| Varredura do Radar de Lares | Keymaster | diário (quando aprovado) |
| Radar de Shows | Bard | dias 1 e 15 — **só se o run de 01/10 provar que é leve**; senão mantém slot próprio |
| Preparação do Monthly Area Report | Lore + Hacker | último domingo do mês |

**Slot 2 — ☀️ Bom Dia, horário a confirmar** — fica separado: fala com a Odara, gera artefato e pode falhar sem afetar a operação.

**Resultado:** de 3–4 execuções/dia para **2** (3 nos dias 1/15 se o Radar de Shows ficar separado). Folga de 2–3 por dia — inclusive para a varredura do Keymaster, **sem Task nova**.

**Risco que sobra:** o slot diário vira peça crítica. Aceitável porque: os módulos são idempotentes (a noite seguinte recupera), o Bom Dia já é fail-safe, e falhas aparecem no relatório do Hacker.

# 7. Sequência de migração

| Quando | Passo | Economia |
| --- | --- | --- |
| Antes de 25/10 | Fixar fuso no Bom Dia e na Manutenção (horário decidido pela Odara) | evita mudança silenciosa de horário |
| 04/10 (pós-piloto) | Manutenção vira módulo do Night Shift + módulo de limpeza da Mesa; desativar a Task de Manutenção | −1/dia |
| Quando o Keymaster estiver pronto | Varredura do Radar de Lares entra como módulo (nunca Task própria) | evita +1/dia |
| 15/10 | Decidir se o Radar de Shows entra no slot (com base na duração do run de 01/10) | −2/mês |
| Fim de outubro | Monthly Area Report como módulo | evita +1/mês |

Nenhum passo acontece durante o piloto. Cada um tem rollback simples (reativar a Task antiga). Todos são **direções a validar**, não decisões.

✅ **Feito em 28/09:** Bom Dia fixado em `CRON_TZ=Europe/Madrid 30 11 * * *` (11:30 local, agora imune ao horário de verão). A Manutenção continua em UTC (08:00 hoje, 07:00 a partir de 25/10) — decisão do Hacker.

# 8. Proposta de campos (não aplicada)

Quando a arquitetura-alvo estiver validada: acrescentar ao roster **Roda em** (Night Shift · Bom Dia · slot próprio · ad hoc) e **Cadência**. Aí o slot lê do registro quais módulos rodar hoje. Até lá, a tabela da §6 é a fonte.