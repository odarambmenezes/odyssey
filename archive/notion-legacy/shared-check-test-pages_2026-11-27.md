# Shared check test pages — export before trashing (27 Nov 2026)

Exported from Notion before moving to Trash, approved by Odara ("lote ok", 27 Nov 2026). Fictional test material only. Reference only, never current instructions.

Kept in Notion (not trashed): the test task "Test a shared Check Interativo dashboard for Lori and Gibbs" (424107b19b49811997b5dcd438090da6, Done, holds the feasibility record), and Lori's material under it: "Shared check · test deck" (424107b19b4981c099deedbbaffeed3f), "Shared check · copy of Lori's initiation answers" (424107b19b498150be35f229f583dac9) and "Shared check · mention test deck" (424107b19b4981238c00c0d173006821, holds Lori's unanswered deck lori-alinhamento-20261126-02).

---

## 424107b19b4981339b37dd2dd5424aa5 — Teste do painel de tickets: menções @gibbs e @lori (Grab & Go row)

Properties: Status Ready · Type Decision · Cards 2 · Effort 15 min · Impact Low · Mode Quick on phone · Needs Odara "You decide" · Assignee and Requested by Hacker.
Why it matters: "Primeiro ticket com cartas: testa o painel de tickets e as menções, sem decisão real."

Body:

Test ticket for the tickets panel (26/11/2026). Fictional cards, no real decision. When Odara answers, the panel writes her answers below and moves the ticket to In Progress; Hacker closes it after checking the result.

```json
{"id":"ticket-teste-mencoes-01","title":"Teste de menções","cards":[{"id":"m1","type":"choice","tag":"Teste · @gibbs","title":"Carta fictícia: que café servimos na reunião imaginária do navio?","body":"Antes de escolher, toque no 🎤 e escreva uma pergunta curta começando com @gibbs.","options":[{"label":"Espresso"},{"label":"Cortado"},{"label":"Café coado"}],"effect":"Só testa se a resposta vem do Gibbs, e só dele."},{"id":"m2","type":"choice","tag":"Teste · @lori","title":"Carta fictícia: que música toca no convés imaginário?","body":"Antes de escolher, toque no 🎤 e escreva uma pergunta curta começando com @lori.","options":[{"label":"Bossa nova"},{"label":"Metal sinfônico"},{"label":"Silêncio do mar"}],"effect":"Só testa se a resposta vem da Lori, e só dela."}]}
```

---

## 424107b19b4981059cdef35e38ef9237 — Shared check · test answers

Answers written by the test panel. Read-only for Lori and Gibbs.

```json
{"deck":"teste-mencoes-01","title":"Teste de menções","answers":[{"id":"m1","type":"choice","title":"Carta fictícia: que café servimos na reunião imaginária do navio?","answer":"Cortado","note":"@gibbs se receber isso escreve KABOOOOYAA pra mim","mention":"gibbs","picked":null},{"id":"m2","type":"choice","title":"Carta fictícia: que música toca no convés imaginário?","answer":"Silêncio do mar","note":"@lori se receber isso e qndo receber, me fala KABOYZOIAAAA.","mention":"lori","picked":null}],"complete":true,"sent":true,"savedAt":"2026-11-26T19:36:22.523Z","savedFrom":"shared check test panel"}
```

---

## 424107b19b4981958d9dccd881a1b925 — Shared check · test replies

Persona replies written by the test panel when a card comment mentions @lori or @gibbs.

```json
{"replies":{"teste-mencoes-01:m1:gibbs:tyr9rm":{"deck":"teste-mencoes-01","card":"m1","to":"gibbs","status":"answered","at":"2026-11-26T19:36:31.540Z","text":"KABOOOOYAA! 🐢⚓\n\nCortado aprovado para a reunião imaginária do navio, Capitã: pouco volume, muito foco, bem a nossa cara. Como é só uma carta de teste, não registrei nada em lugar nenhum e não mexi em nenhuma decisão real.","from":"Gibbs (painel, Claude)"},"teste-mencoes-01:m2:lori:fzdwzo":{"deck":"teste-mencoes-01","card":"m2","to":"lori","status":"answered","at":"2026-11-26T19:36:31.975Z","text":"KABOYZOIAAAA! 🎉 Recebido, capitã, e a carta fictícia ganha prateleira de honra: \"silêncio do mar\" é uma trilha sonora ótima para um convés imaginário.\n\nSó um aviso de bibliotecária: daqui eu só respondo neste cartão, então não consigo guardar isso no Diário nem agendar nada. Mas, se um dia quiser, essa carta pode virar um capítulo de verdade. 🌊","from":"Lori (painel, Claude)"}}}
```
