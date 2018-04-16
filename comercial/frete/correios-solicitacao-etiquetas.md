# Correios Solicitações Etiquetas

---

![](http://developers.connectparts.com.br/imagens/solicitacaoEtiquetas01.png)

## Funcionalidade

Nesta funcionalidade o sistema solicita a os códigos par geração de etiquetas, determinada pelo **serviço de entrega**, **quantidade** pedida. É requisitada na API dos correios que devolve uma faixa de valores (em cima da quantidade) que poderão ser utilizadas na emissão de etiquetas pela via do **serviço de entrega**.

## Resultado

No resultado apresentado irá aparecer estas informações, Quantidade Solicitada, Etiqueta Inicial e Etiqueta Final.

Será enviado um e-mail para a pessoas que requsitou as estiquetas contendo

|Exemplo||
|---|---|
|Quantidade Solicitada:|10|
|Etiqueta Inicial:	|EC31340465BR|
|Etiqueta Final:	|EC31340474BR|
|Data da Solicitação|	07/04/2017|
|Hora da Solicitação|	09:35:08|


> **Obs.: ** Esta funcionalidade está sendo executada no ambiente de homologação, assim que aprovado pelo representante dos correios, será enviada para o ambiente de produção.

## Regras de cálculo

* Verificar - [Sobre Cálculos das Transportadoras](/comercial/frete.md).
