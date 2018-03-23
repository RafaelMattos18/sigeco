# Simulação de Custo - Pedido

---

![](http://developers.connectparts.com.br/imagens/simulacaoCustoFretePedido01.png)

## Funcionalidade

Faz uma consulta no Ábacos para pegar as informações do pedido e uma consulta e uma requisição na API dos Correios para pegar o endereço de entrega.

## Resultado

Adicionar texto

### Faixa de CEP

![](http://developers.connectparts.com.br/imagens/simulacaoCustoFretePedido02.png)

### Número do pedido

![](http://developers.connectparts.com.br/imagens/simulacaoCustoFretePedido03.png)

### Endereço de Entrega

**Validar Correios**

![](http://developers.connectparts.com.br/imagens/simulacaoCustoFretePedido04.png)

### Informações do Pedido

* As informações vêm do Ábacos

* Existem cálculos diferentes para Peso cubado calculado (KG), Peso escolhido (KG) e Valor simulado (pago transp.) (R$) dependendo da **Transportadora**.

* Os valores dos campos de Peso cubado calculado (KG), Peso escolhido (KG) e Valor simulado (pago transp.)(R$) são somados em API diferente.


### Endereço de Entrega

* Esta consulta é requisita na mesma API que **Validação de CEP (Correios) **

### Regra

- Se o peso cubado for maior que 5, faz o calculo pelo peso real.