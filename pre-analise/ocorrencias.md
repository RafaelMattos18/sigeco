# Ocorrencias

![](http://developers.connectparts.com.br/imagens/preAnalise03.png)

## Funcionalidade

Nesta tela iremos bloquear o CPF ou CNPJ do cliente com as opções:

* Suspeito
* Recorrente
* Fraudador

> O motivo destas opções estão em **Regras / Para Bloqueio**.

Na aba **Buscar** teremos uma relação completa dos bloqueados ou fazer a busca específica pelo **CPF/CNPJ**.

Estes processos irão determinar a avaliação da pré análise. Tanto CPF ou CNPJ bloqueados por estes motivo nesta tela, será refletido uma mensagem na tela de **Visualização de Pedido - Pré Análise** como do exemplo abaixo:

**Exemplo:** 

![](http://developers.connectparts.com.br/imagens/preAnalise06.png)

## Regras

**Para bloqueio**

* Cliente tem pedidos anteriores há 6 meses
* Cliente fez compras nos últimos 30 dias
  * Ou 3 compras com valor total igual ou maior de R$ 1.500,00
* CPF/CNPJ está na lista de ocorrências.

