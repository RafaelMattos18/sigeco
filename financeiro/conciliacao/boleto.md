# Boleto

![](http://developers.connectparts.com.br/imagens/ConciliacaoBoletoBancario_01.png)

## Funcionalidade

Leitura dos documentos bancários, no formato **.RET** ou **.txt**.

## Processos

* Validar pedido existe na Vtex.
* Tolerância de aprovação 5% do valor ou R$ 2,00 \(O que for menor\).
* Não aprovar pedidos cancelados.
  * Somente pedidos com status **pendete de pagamento**
* Não aprovar pedidos que contém Vale + Boleto como forma de pagamento.
* Não aprovar pedidos com data de pagamento após 20 dias da criação do pedido.
* Não aprovar pedido pagos com cheque.
* Não aprovar pedidos com endereço de caixa postal.
  * Para identificar este endereço, verifica-se o 6º digito do CEP e caso 9, é identificado como caixa postal.

## Resultado

![](http://developers.connectparts.com.br/imagens/ConciliacaoBoletoBancario_02.png)

