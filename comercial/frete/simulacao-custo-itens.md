# Simulação Custo Itens

---

![](http://developers.connectparts.com.br/imagens/SimulacaoCustoFreteItensPedido01.png)

## Funcionalidade

Traz informações sobre os itens do pedido, valores unitários, ações de retira e devolver o item ao pedido. Traz os cálculos de fretes por transportadora.

## Processo

### Valores Considerados

* As informações vêm do Ábacos, Valor dos Itens (total com itens), Peso Real (KG) e Peso Cubado (KG).

* Sobre o **Peso Cubado (KG) ** este cálculo não vem do pedido (Ábacos) ele é feito em cima dos volumes dos itens que estão no pedido, ao retirar ou adicionar os itens estes valores são alterados.
 > **Obs.: ** pode acontecer que as dimensões dos produtos que compõe o pedido mudem e o valor pode dar negativo.

#### Mark-up

* Um mark-up é adicionado ao custo total, para geração de lucro.

![](http://developers.connectparts.com.br/imagens/SimulacaoCustoFreteItensPedido02.png)

#### Itens do Pedido

* Trazido do Ábacos as informações dos produtos que compõe o pedido e para ser mais específico podemos clicar no resultado da coluna **Código**, onde se fará uma consulta mais detalhada no Ábacos sobre Dados do produto, Fornecedores e Estoque.

![](http://developers.connectparts.com.br/imagens/SimulacaoCustoFreteItensPedido03.png)

#### Resultado da Simulação

* Demonstrado na coluna **Serviço de Entrega** os valores de cada forma
 * Quando a linha estiver em **vermelho**, que dizer que os produtos foram enviados por aquele serviço.
 * Quando estiver **verde**, demonstra a forma de envio mais barata.
 
## Regras

- Se o peso cubado for maior que 5, faz o calculo pelo peso real.