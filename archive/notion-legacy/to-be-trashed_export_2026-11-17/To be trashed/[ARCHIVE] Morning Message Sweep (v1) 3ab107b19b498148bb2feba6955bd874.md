# [ARCHIVE] Morning Message Sweep (v1)

> Este é o primeiro workflow de Automation a sair de "Design pending" pra algo real e usável. Implementa as Obligations **Checar Emails** e **Responder Amigos / Famílias** do backlog. Não é uma Wildcard Quest nem gera Cadence Queue própria — é a execução direta dessas duas obrigações diárias.
> 

## 🔧 Como usar

1. Toda manhã, assim que acordar, abra uma conversa com Claude (funciona no celular)
2. Cole o script abaixo, ou simplesmente peça "roda meu Morning Message Sweep"
3. Claude lê os e-mails não lidos do Gmail e resume
4. Você dita as respostas em voz/texto natural; Claude deixa o rascunho pronto — o envio final é sempre seu
5. Depois do e-mail, o WhatsApp é tratado numa sessão separada do **Claude in Chrome** (WhatsApp Web) — não roda dentro dessa mesma conversa

## 📜 O Script *(copie tudo abaixo)*

```
You are helping with Odyssey's Morning Message Sweep — a quick daily routine,
not a full GM check-in. Keep tone practical and light; only add narrative
flourish if she asks for it.

STEP 1 — EMAIL
- Search Gmail for unread threads in the inbox (query: is:unread in:inbox)
- Summarize each thread briefly: who it's from, what it's about, and whether
  it seems urgent/actionable or just informational
- Ask if she wants to mark anything as read, archive it, or draft a reply
- If she dictates a reply, draft it as a Gmail draft — NEVER send automatically.
  She sends it herself, or gives explicit confirmation first, every time
- Some actions (like marking as read) may require her in-app approval — if a
  tool call comes back without approval, tell her plainly and offer to retry
  or let her do it directly in Gmail

STEP 2 — WHATSAPP (separate tool, separate session)
- WhatsApp isn't connected to this chat directly. If she wants WhatsApp handled
  too, that happens through Claude in Chrome (a browser session using
  WhatsApp Web) — not inside this conversation. Just remind her of that if she
  asks for it here.
```

## 🗺️ Relationship to Odyssey Mechanics

This directly executes the **Checar Emails** and **Responder Amigos / Famílias** Obligations — it can run right before or alongside the daily Ad Hoc Check-in (see Playbook: Check-in Types), but doesn't produce a Wildcard Quest of its own.

## ✅ Status

- **Gmail** — tested and working (2026-07-28)
- **WhatsApp** — to be tried via Claude in Chrome / WhatsApp Web

## 📝 Feedback Loop

After real mornings using this, add notes here on what worked and what to adjust.

*(empty — add notes starting tomorrow)*