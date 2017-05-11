# Pré Análise

---

## Funcionalidade

Neste processo os departamentos Financeiro e Atendimento fazem uma pré analise dos pedidos oriundos do Ábacos ou DropShipping, levando em consideração algumas regras como: cliente tem pedidos anteriores há 6 meses, cliente fez compras nos últimos 30 dias e CPF/CNPJ está na lista de ocorrências.

### Local

Financeiro / Pré Análise.

## Consulta de Pedidos - Pré Análise

![](/assets/img01.png)

### Campos

* **Limpar Filtros**

	* Limpa os filtros e cache armazenado na consulta

* **Pedidos Ábacos - Pedidos DropShipping**

	* Escolha de onde virão os pedidos Ábacos ou pedidos que contenham DropShipping

* **Data Inicial e Final**

	* Selecione as datas para a pesquisa ser especifica.
	* Todas as datas são referente a data de registro

* **Forma de pagamento**

	* Selecione as formas de pagamento para a pesquisa ser especifica.

* **Pedido**

	* Digite o número do pedido para a pesquisa ser especifica.

> **Observação: ** Caso não selecione e nem preencha algum campo a consulta poderá ser feita clicando no botão de geração "**Lupa**", porém, sem critérios.

### Legenda

|Descrição|  |
|--|--|
|**Imagem**|![](/assets/preAnalise02.png)|
|**Cadeado Preto**| Pedido|
|**Cadeado Vermelho**|Pedido barrado (pela pré análise)|
|**Cadeado Verde**|Pedido barrado (pela pré análise) e depois liberado (pelo atendimento)|

### Resultado

O resultado traz a quantidade de **Pedidos Encontrados**.

E as colunas **Pedido, Tipo de Pessoa, Forma de Pagamento, Valor, Status, Data **e** Ação**.


####Ação

Ao clicar na **Ação** será direcionado para a tela de ***Visualização de Pedido - Pré Análise***.

![](/assets/preAnalise03.png)

Ao clicar em **Barrar Pedido** é necessário inserir um motivo válido.

É apresentado **Informações Ábacos**, com a opção de bloquear CPF e CNPJ do destinatário e do cliente, formas e condições de pagamento e itens de pedido.

##Lista de Ocorrências - CPF/CNPJ

![Barrar Pedido](C:\Users\heltonrodrigues\Google Drive\01 - Projetos Internos\Sigeco\Financeiro\Pre Analise\img04.png)

![](/assets/preAnalise04.png)

###Funcionalidade

Nesta tela iremos bloquear o CPF ou CNPJ do cliente com as opções:

* Suspeito

* Recorrente

* Fraudador


> O motivo destas opções estão em **Regras / Para Bloqueio**.

Na aba **Buscar** teremos uma relação completa dos bloqueados ou fazer a busca específica pelo **CPF/CNPJ**.

Estes processos irão determinar a avaliação da pré análise. Tanto CPF ou CNPJ bloqueados por estes motivo nesta tela, será refletido uma mensagem na tela de **Visualização de Pedido - Pré Análise** como do exemplo abaixo:

**Exemplo:**

![](/assets/preAnalise06.png)

## Consulta de Pedidos Barrados - Atendimento

![](/assets/preAnalise05.png)

### Funcionalidade

Faz a busca de pedidos barrados no atendimento, podendo fazer pesquisa específica pelo **Status do Pedido**, **Código do Pedido** ou sem filtro algum. A pesquisa traz os resultados de **Data, Pedido, Data / Pedido, Motivo** e **Ação**.

Ao clicar na **Ação**, poderá ser liberado o pedido, após a digitação do **motivo**.

## Regras

### Para bloqueio

* Cliente tem pedidos anteriores há 6 meses

* Cliente fez compras nos últimos 30 dias

	* Ou 3 compras com valor total igual ou maior de R$ 1.500,00

* CPF/CNPJ está na lista de ocorrências.