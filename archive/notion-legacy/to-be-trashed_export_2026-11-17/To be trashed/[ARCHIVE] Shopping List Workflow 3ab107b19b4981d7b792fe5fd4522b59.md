# [ARCHIVE] Shopping List Workflow

> Fluxo de duas mãos: qualquer hora que ela mencionar algo que precisa comprar, vira uma linha na [Odyssey — Shopping List](https://app.notion.com/p/9adfc4b8cd10447d94cc7754a1c0231c?pvs=21). Quando ela pedir a lista, Claude devolve tudo já organizado e priorizado.
> 

## ❗ Regra fixa: uma única lista, sempre

Essa database é a **única** fonte de verdade pra compras, **em qualquer chat do projeto** — não só no chat de Rotina de Alimentação. Se ela disser "me dá minha lista de compras" em qualquer lugar (Building Odyssey, Bom Dia Claude, um chat novo qualquer), a resposta vem sempre daqui, puxando todos os itens Pendentes (Mercado, farmácia, o que for) — nunca criar uma lista nova ou paralela só porque não é "o chat certo". Não existe chat errado pra isso: a database é a mesma em qualquer lugar.

## 📥 Captura (durante o dia, a qualquer momento)

Quando ela mencionar algo que precisa comprar, em qualquer conversa:

1. Extrair o item e qualquer detalhe dado (marca específica, tamanho, etc.)
2. Classificar o **Tipo**:
    - **Mercado** — comida/consumo do dia a dia (leite, capuccino, coisas de comer) — ela compra fisicamente, não precisa de links
    - **Produto Específico** — qualquer coisa que não seja mercado (caixa de ferramentas, TV, monitor, etc.) — aqui sim entram recomendações
3. Se for **Produto Específico**, já buscar e anexar 2-3 links de recomendação na hora (Amazon sempre como primeira opção). Se for **Mercado**, deixar o campo de links vazio
4. Atribuir **Prioridade** (Alta/Média/Baixa) com base em urgência percebida
5. Criar a linha na database com Status = Pendente

## 📤 Recuperação (quando ela pedir a lista)

Quando ela pedir "me dá minha lista de compras":

1. Puxar todos os itens com Status = Pendente
2. Agrupar por Tipo: **Mercado** primeiro (lista simples, sem links, ela resolve no mercado físico), depois **Produto Específico** (ordenado por Prioridade, cada um com os links já anexados)
3. Perguntar se algo já foi comprado, pra marcar como Status = Comprado

## 📝 Exemplo

Ela diz no meio do dia: *"preciso comprar cappuccino [marca X]"* → vira uma linha: Item = Cappuccino, Detalhes = marca X, Tipo = Mercado, Status = Pendente, sem links.

Ela diz: *"preciso de uma caixa de ferramentas"* → Item = Caixa de ferramentas, Tipo = Produto Específico, Links Recomendados = 2-3 opções (Amazon primeiro), Prioridade atribuída.

## 📋 Status

Construído em 2026-07-28, ainda não testado numa captura real.