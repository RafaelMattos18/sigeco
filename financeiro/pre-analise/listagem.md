# Consulta de Pedidos - Pré Análise

---

![](http://developers.connectparts.com.br/imagens/img01.png)

## Funcionalidade

Neste processo os departamentos Financeiro e Atendimento fazem uma pré analise dos pedidos oriundos do Ábacos ou DropShipping, levando em consideração algumas regras como: cliente tem pedidos anteriores há 6 meses, cliente fez compras nos últimos 30 dias e CPF/CNPJ está na lista de ocorrências.

## Processos

**Campos**

* **Limpar Filtros**
	* Limpa os filtros e cache armazenado na consulta
* **Pedidos Ábacos - Pedidos DropShipping**
	* Escolha de onde virão os pedidos Ábacos ou pedidos que contenham DropShipping
* **Data Inicial e Final**
	* Selecione as datas para a pesquisa ser especifica.
* **Forma de pagamento**
	* Selecione as formas de pagamento para a pesquisa ser especifica.
* **Pedido**
	* Digite o número do pedido para a pesquisa ser especifica.

> **Observação: ** Caso não selecione e nem preencha algum campo a consulta poderá ser feita clicando no botão de geração "**Lupa**", porém, sem critérios.

### Legenda

|Descrição|  |
|--|--|
|**Imagem**|![](http://developers.connectparts.com.br/imagens/preAnalise02.png)|
|**Cadeado Preto**| Pedido|
|**Cadeado Vermelho**|Pedido barrado (pela pré análise)|
|**Cadeado Verde**|Pedido barrado (pela pré análise) e depois liberado (pelo atendimento)|

#### Ação

Ao clicar na **Ação** será direcionado para a tela de ***Visualização de Pedido - Pré Análise***.

![](http://developers.connectparts.com.br/imagens/preAnalise04.png)

Ao clicar em **Barrar Pedido** é necessário inserir um motivo válido.

É apresentado **Informações Ábacos**, com a opção de bloquear CPF e CNPJ do destinatário e do cliente, formas e condições de pagamento e itens de pedido.

## Resultado

![](http://developers.connectparts.com.br/imagens/financeiroPreAnaliseListagem01.png)

O resultado traz a quantidade de **Pedidos Encontrados**.
E as colunas **Pedido, Tipo de Pessoa, Forma de Pagamento, Valor, Status, Data **e** Ação**.

## Regras

**Para bloqueio**

* Cliente tem pedidos anteriores há 6 meses

* Cliente fez compras nos últimos 30 dias

	* Ou 3 compras com valor total igual ou maior de R$ 1.500,00


* CPF/CNPJ está na lista de ocorrências.

* Pedidos com -TRT , -INT, -TRR não serão demonstrados.

	* Atualmente no Ábacos, existem 03 grupos de comercialização (_DEVOLUCAO PARA FORNECEDORES, SAIDA OUTROS, VENDA_), os pedidos com siglas são encontrados em SAIDA OUTROS.