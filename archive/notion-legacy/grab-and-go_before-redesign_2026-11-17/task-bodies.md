# Grab & Go — task bodies saved before the redesign (17 Nov 2026)

Properties of all 65 tasks are in `grab-and-go_rows.json`. Below are the page bodies that held content and were rewritten or merged.

## Moradia (Clau): retomar a busca depois da auditoria das Personas, com o contato externo ainda PAUSADO
(merged into "Wake up Clau, The Keymaster")

Fica parada até a auditoria das Personas terminar. Depois disso, Chatty + Clau revisam o checklist abaixo com a Odara, que decide qualquer reativação e mudanças significativas. Estado atual do contato externo: PAUSADO. A autorização de 27/09 não foi reativada. Este item não autoriza buscas, mensagens, reservas nem qualquer ação externa.

Checklist:
- Resolver autoridade de contato e pausa: conciliar a autorização única de contato informativo (27/09) com a suspensão posterior do Night Shift. Pedir confirmação explícita nova da Odara antes de qualquer contato. Se reautorizar, definir canais exatos, template, regra de um contato por anúncio e as ações que continuam exigindo aprovação separada (confirmar visita, documentos, negociação, reserva, pagamento). NIE e documentos pessoais nunca vão em anúncios públicos nem em chats de portais; qualquer divulgação privada exige aprovação explícita.
- Recalibrar a prontidão da busca: confirmar orçamento atual, critérios obrigatórios, fase/prazo da busca, forma de comprovar renda, status e validade da pré-qualificação Aserta e implicações para aluguel de longo prazo. Tratar contexto de trabalho sensível de forma privada e mínima; não assumir que critérios antigos continuam valendo.
- Conciliar a Main Page do Clau com o Radar: incluir vivienda habitual + empadronamiento como prioridade rígida de verificação quando aplicável; refletir a autoridade limitada de contato aprovada sem contornar a pausa; voz em português, template de agência em espanhol, Milo Thatch + Amy Santiago. Confirmar avatar, fluxo de aluguel de ponta a ponta, handoff com a Lore, ponteiros de checklist/template e status do Radar. Validação final do piloto pelo Clau.
- Auditar operação e restrições de ferramenta do Radar de Lares: confirmar termos atuais da plataforma e acesso técnico antes de qualquer integração/busca no Idealista. Evitar coleta em massa, varredura área por área ou estatísticas automatizadas proibidas; revisar cadência e escopo do deep scan. Verificar agências, registros de anúncios, checklist de visita e template v2.
- Auditar fornecedor de moradia e marcos da mudança: avaliação pendente de fornecedor/contrato do Espanha Fácil, aviso prévio do contrato atual, documentos, depósitos/taxas, lembretes de agenda, checklist de assinatura, endereço/TIE e empadronamiento. Verificar exigências legais atuais em fontes oficiais antes de agir.
- Só então conciliar o Tenant Profile (SoT): estrutura mínima separando fatos e preferências estáveis da inquilina de regras datadas do Radar, anúncios e registros de agências. Preservar o antigo Perfil de Inquilina e o Radar até checar dependências.

Origem: Future Horizons & Backlog ("Post-Audit Backlog — Clau / Housing Search").

## Corrigir o Bom Dia Claude (rotina diária)
(rewritten as "Rebuild Bom Dia (morning routine)")

Por que importa: o Bom Dia Claude roda todo dia, mas com regras desatualizadas. Corrigir isso é o objetivo prático desta reconciliação.
Passo a passo: 1) Ler a página do Bom Dia e o diagnóstico de conectores (doc do Project: diagnostico-conectores-bdc-2026-10-07.md). 2) Listar o que está errado (regras antigas, SoTs, conectores, widgets). 3) Cruzar com arquitetura/governança validadas. 4) Propor correções em lista curta. 5) Aplicar o que for Livre; resto em Review Needed. 6) Rodar 1 execução de teste.
Pronto quando: Bom Dia roda com as regras atuais, checa Status=Ativo nos widgets (Registro de Cartas, Ações Rápidas, Temas) e Odara aprova 1 execução de teste.
Prompt: "Vamos corrigir o Bom Dia Claude. Leia a página do Bom Dia, o diagnóstico de conectores de 07/10 e a arquitetura/governança já validadas no Project Odyssey. Liste o que está desatualizado, proponha as correções em ordem de impacto e aplique só o que for seguro. Deixe qualquer mudança estrutural como proposta para eu aprovar. No final, registre o handoff nesta tarefa."
Cuidados: não mudar taxonomia nem apagar/arquivar em lote; dúvida de autoridade ou dado sensível → parar e perguntar à Odara.
