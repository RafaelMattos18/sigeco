# INSERIR PRODUTO 00K

![](http://developers.connectparts.com.br/imagens/listagemProdutos_01.png)

## Funcionalidade

Nesta tela temos os produtos inseridos via arquivo excel na opção **Importar Planilha de Custo**. Aqui temos um controle interno para sabermos se os produtos DropShipping estão ativos no Mercado livre e caso eles sejam adicionados para uma compra, eles seguiram o fluxo DropShipping.

## Regras

1. Há uma tarefa que roda toda madrugada que preenche este estoque, somente após o produto adicionado e ativado hoje, no dia seguinte estará com estoque informado pela **DTS**.
2. Caso o produto não seja ativado nesta funcionalidade, ele irá percorrer o fluxo normal da 00K como um produto **NÃO** Dropshipping.
