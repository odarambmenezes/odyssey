# Diagnóstico BDC — Conectores & Fixes Confirmados
**Data:** 07/10/2026 · **Run:** Bom Dia Claude + Investigação Completa

---

## TL;DR

3 bugs confirmados com fix testado e funcionando. 1 limitação estrutural (Spotify, sem fix simples). O prompt do trigger foi atualizado com as correções.

---

## Bug 1 — Google Calendar: HTTP 400

**Afetava:** Bloco de Agenda (silêncio ou erro toda vez)

**Causa:** Parâmetros `time_min`, `time_max`, `single_events` em snake_case não são aceitos pelo MCP do Google Calendar.

**Fix confirmado:**
```python
# ERRADO — causava 400:
list_events(calendar_id="...", time_min="...", time_max="...", single_events=True)

# CERTO — funciona perfeitamente:
list_events(calendar_id="odarambmenezes@gmail.com")
# Sem parâmetros de tempo — retorna próximos eventos por padrão
```

**Calendários disponíveis:**
- `odarambmenezes@gmail.com` — agenda pessoal
- `tacomigoencomendas@gmail.com` — Odara Pessoal
- `odara.menezes@fortisgames.com` — Fortis (freeBusyReader, título dos eventos oculto)
- `family09011627861380320805@group.calendar.google.com`
- `en.brazilian#holiday@group.v.calendar.google.com`

**Eventos hoje confirmados (07/10):** Dns 18:00–19:00 na agenda pessoal; 7 eventos no Fortis (14h, 15h, 16h, 16:30, 17h, 20h–20:30, 21h–21:30).

---

## Bug 2 — Gmail: HTTP 400

**Afetava:** Bloco de Correspondência (silêncio ou erro toda vez)

**Causa:** O parâmetro `max_results` não existe na ferramenta `search_threads`.

**Fix confirmado:**
```python
# ERRADO — causava 400:
search_threads(query="is:unread newer_than:1d", max_results=10)

# CERTO — funciona:
search_threads(query="is:unread newer_than:1d")
```

**Resultado hoje:** 13 threads não lidas encontradas.

---

## Bug 3 — Notion: "Invalid arguments: data: Invalid input"

**Afetava:** Pré-vôo inteiro — Mini Cards, Poções, Tema, Backlog, Night Shift. Era o maior causador de falhas em cascata.

**Causa:** O prompt instruía o modelo a usar `notion-query-data-sources` em modo SQL. A estrutura esperada pelo MCP para SQL exige `data_source_urls` (plural, array) dentro de um objeto `data`. O modelo provavelmente estava passando `data_source_url` singular ou com estrutura incorreta.

**Fix confirmado:** Usar `mode: "rows"` com `data_source_url` singular e filtros estruturados. Esse modo não exige SQL e aceita filtros tipados de forma robusta.

```json
// Exemplo — buscar cartas ativas do Registro de Cartas:
{
  "mode": "rows",
  "data_source_url": "collection://049c4322-6c07-4726-9af3-72844974938e",
  "filter": {
    "type": "group",
    "operator": "and",
    "filters": [{
      "type": "property",
      "property": "Status",
      "propertyType": "select",
      "operator": "enum_is",
      "value": {"type": "exact", "value": "Ativo"}
    }]
  }
}
```

**Dados confirmados disponíveis (todos retornaram corretamente hoje):**

### Registro de Cartas — 4 cartas ativas
| Nome | Cor | Tema |
|------|-----|------|
| Mini Side Quest | Vinho | Criativo |
| Soundtrack | Mar Profundo | Música |
| Flo | Vinho | Saúde |
| Word of the Day | Veludo | Aprendizado |

### Registro de Ações Rápidas — 3 botões ativos
| Ícone | Nome | Categoria |
|-------|------|-----------|
| 📅 | Calendar Check | Agenda |
| 📧 | Gmail Sweep | Comunicação |
| 📋 | O que tá pendente? | Backlog |

### Task Backlog — retornou 20+ itens
**⚠️ Observação:** Todos os itens recuperados têm deadline em setembro 2026. Muitas obrigações estão com deadline atrasado (Pedicure, Limpar Quarto, Blondor, Stremio, mensagens sociais...). A rotina de auto-revival (`Odyssey — Manutenção Diária do Backlog`) está **desabilitada** desde 02/10/2026 — pode ser que itens com status "Feito (Ciclo)" não estejam voltando para "A Fazer". Recomendo revisar.

**Collection URLs para referência:**
- Registro de Cartas: `collection://049c4322-6c07-4726-9af3-72844974938e`
- Registro de Ações Rápidas: `collection://bd11c886-f95f-4d7e-bae8-d9914d57d9e5`
- Task Backlog: `collection://a4f2dc93-71ae-44c6-8049-b2cd8f752220`
- Crew Noticeboard: `collection://7cba836a-a6e5-48bf-b8fa-0468fee673d2`

---

## Limitação Estrutural — Spotify

**Afetava:** Card de Soundtrack (nunca funcionou em sessões agendadas)

**Causa:** OAuth do Spotify exige autenticação interativa no browser. Impossível em sessões cloud sem ninguém presente.

**Opções:**
1. ✅ **Aceitar (atual):** Soundtrack hardcoded por tema no HTML — funciona, honesto
2. 🔶 **Token de longa duração:** setup manual uma vez, token no Notion — técnico mas viável
3. 🔶 **Last.fm (sem OAuth):** busca músicas por humor/tema via API pública
4. ❌ **Fix no MCP:** fora do nosso controle

---

## O que foi atualizado no trigger do BDC

O prompt do `trig_01EC7E7Uf5AapZV4gmHpM3dZ` (Card Pull of the Day) foi atualizado com:
- Instrução de usar `mode: "rows"` para todas as queries Notion do pré-vôo
- Instrução de não usar `time_min`/`time_max` no Calendar
- Instrução de não usar `max_results` no Gmail
- Night Shift: instrução para usar `mode: "rows"` no Noticeboard

---

## Status das Pendências Originais

| Item | Status |
|------|--------|
| Calendar HTTP 400 | ✅ Fix confirmado + trigger atualizado |
| Gmail HTTP 400 | ✅ Fix confirmado + trigger atualizado |
| Notion query failures | ✅ Fix confirmado + trigger atualizado |
| Registro de Cartas live | ✅ Dados acessíveis com modo rows |
| Ações Rápidas live | ✅ Dados acessíveis com modo rows |
| Task Backlog live | ✅ Dados acessíveis com modo rows |
| Spotify | 🔶 Limitação estrutural — decisão pendente da Odara |
| Backlog auto-revival desabilitado | ⚠️ Trigger está disabled desde 02/10 — pode reativar |
