# [ARCHIVE] Crew Noticeboard & Night Shift — Pilot

> **Status:** ⚫ Retired 2026-11-06. The overnight Night Shift is no longer used and its scheduled task is off. This page stays as history. The note protocol now lives in Mesa do Time (02 O Navio); the quick-capture Skill replaces the overnight batch.
> 

> 
> 

> This page is the execution specification for the first Crew Communication pilot. It does not create new structural authority.
> 

# ⚓ Crew Noticeboard & 🌙 Night Shift — Pilot

## Objective

Validate that Odyssey can coordinate internal Crew communication through shared Notion artifacts without making Odara the manual communication layer.

**Pilot:** The Catalan Corsair ↔ The Keymaster  

**Duration:** 5 nights  

**Mode:** Shadow mode  

**Night Shift close:** 05:00 local time  

**External actions:** paused

## Flow

**Night**

→ Odara talks to Lorekeeper  

→ Lorekeeper holds context  

→ optional explicit “good night” closes the human interaction

**05:00**

→ Night Shift Task closes/consolidates the period  

→ Lorekeeper identifies relevant recipients  

→ creates internal handoffs  

→ writes them to Crew Noticeboard  

→ records full chain in Night Shift Log

**11:30 Bom Dia**

→ reads Night Shift output  

→ presents dedicated Night Shift section  

→ surfaces what is handled / prepared / waiting / needs Odara  

→ links to full log

## Handoff contract

Every internal handoff should contain:

- **From**
- **To**
- **Context**
- **Why it matters**
- **Suggested action**
- **Urgency / Status**
- **Expected return**

The handoff should preserve the original context while adapting the message to the recipient's domain.

## Pilot case

### 🔑 Keymaster

Focus:

- housing contract;
- price;
- bureaucracy;
- documentation;
- practical feasibility.

### 🏴‍☠️ Catalan Corsair

Focus:

- neighborhood vitality;
- Barcelona/Catalonia context;
- local character;
- lived experience;
- fit with Odara.

Neither Persona silently resolves the other's disagreement.

If their outputs materially conflict, the conflict becomes:

**🔴 Odara Decision Required**

## Shadow-mode boundary

Allowed:

- internal routing;
- research;
- preparation;
- analysis;
- drafting;
- writing to shared Notion artifacts.

Paused:

- agency contact;
- external messages;
- external commitments;
- irreversible actions.

## Observability

The full log must preserve:

**Input → routing → handoff → response/preparation → consolidation → Bom Dia**

Odara must be able to inspect the full record in Notion.

## Success criteria

The pilot succeeds if:

1. Odara no longer has to manually decide which Persona receives relevant context.
2. Keymaster and Corsair can work from shared prepared context.
3. Their domain perspectives remain distinct.
4. Meaningful disagreement reaches Odara rather than being silently resolved.
5. Bom Dia can explain what happened overnight without dumping raw activity.
6. Odara can inspect the complete log when she wants.
7. The system reduces coordination work rather than creating another inbox to manage.

> **Invisible execution, visible accountability.**
> 

## Stop conditions

Stop and return to the working baseline if:

- routing creates noise;
- Odara has to maintain the communication system manually;
- Personas begin changing structure autonomously;
- the pilot requires broad new infrastructure;
- the system becomes a second task manager;
- observability becomes harder instead of easier.

[[ARCHIVE] Entrada da Noite](%5BARCHIVE%5D%20Crew%20Noticeboard%20&%20Night%20Shift%20%E2%80%94%20Pilot/%5BARCHIVE%5D%20Entrada%20da%20Noite%203e9107b19b4981d9bb88cddd29e07c42.md)

[[ARCHIVE] Night Shift Log](%5BARCHIVE%5D%20Crew%20Noticeboard%20&%20Night%20Shift%20%E2%80%94%20Pilot/%5BARCHIVE%5D%20Night%20Shift%20Log%203e9107b19b498193bb34fbbceccb85d9.md)

---

## 📮 Protocolo do Noticeboard

Moved to [Crew Noticeboard](https://app.notion.com/p/Crew-Noticeboard-410107b19b4981009b2ada911ec304fb?pvs=21) (02 O Navio) on 2026-11-06. The original 10/10/2026 wording is kept in the toggle on that page.

---

## ⚓ Implementação — Fase 1 (Mayor, 28/09/2026)

> Decisão do Mayor sobre **como** construir. O que queremos (narrativa/experiência) vem das páginas acima; o como está aqui.
> 

### Restrição física que define o desenho

Chats não conversam entre si e não acordam sozinhos — só agem quando a Odara abre. As únicas partes que agem sozinhas são os **Scheduled Tasks**, e o único meio comum é o **Notion**. Por isso: o Night Shift é um Task que "veste" Lorekeeper, Keymaster e Corsair lendo as páginas deles; a comunicação passa por artefatos no Notion; nada é chat-to-chat.

### Os 3 artefatos do piloto (e só eles)

- **📥 Entrada da Noite** (página) — a Lorekeeper anexa contexto durante a noite; o Night Shift esvazia às 05:00.
- **⚓ Crew Noticeboard** (banco pequeno, 12 campos) — handoffs com status. É banco (e não página) porque o Bom Dia e as Personas precisam **filtrar por data e status via SQL**, igual ao pré-voo que o Bom Dia já faz.
- **🌙 Night Shift Log** (página) — observabilidade completa, turno mais novo em cima.

### Automação

- **Task "🌙 Night Shift — Piloto"**: `CRON_TZ=Europe/Madrid 0 5 * * *` (05:00 Madri), silencioso (sem push), aprovação automática. Não conflita com nenhum Task existente (Manutenção roda às 08:00, Bom Dia às 11:30).
- **Bom Dia ("Card Pull of the Day")**: ganhou um bloco opcional e fail-safe que lê o Noticeboard do dia e mostra a seção 🌙 Night Shift. Sem linhas = Bom Dia normal.

### Modo sombra

- Autoridade de contato do Keymaster **pausada** (callout ⏸️ no Radar de Lares).
- O Night Shift só escreve nos 3 artefatos. Não mexe em Sources of Truth, Backlog, Persona pages, Governance.
- ⚠️ Limitação honesta: não dá pra restringir tecnicamente os conectores de um Task (o Gmail vem anexado). O limite de "não enviar" é por instrução, não por bloqueio técnico.

### O único passo manual (uma vez só)

A Lorekeeper é um chat — ela só escreve na Entrada da Noite se souber que deve. A Odara cola **uma vez** o prompt de setup no chat da Lorekeeper. Depois disso, nada é manual.

### Rollback (ordem)

1. Desativar o Task "🌙 Night Shift — Piloto" (trig_01KBn9jigKXf8sCt9UdT9PES).
2. No Task "Card Pull of the Day", remover o bloco "🌙 NIGHT SHIFT (piloto…)" do prompt — cópia integral do prompt anterior está no Project Knowledge do Claude (`claude/piloto-night-shift-implementacao-2026-09-28.md`).
3. No Radar de Lares, remover o callout ⏸️ (a autorização de contato volta).
4. Os 3 artefatos podem ficar (histórico) ou ser arquivados. Nada mais foi alterado.

### Fora desta fase (de propósito)

Command Center preview (adiado — ver relatório), outras Personas, contrato para o resto do Crew, automação Chatty↔Claude, qualquer ação externa.