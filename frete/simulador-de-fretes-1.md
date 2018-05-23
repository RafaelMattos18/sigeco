# Simulador de Fretes

## Descrição do Projeto

Desenvolvido um simulador de fretes onde passa o código do produto ou pedido e se calcula o frete do produto específico ou dos produtos do pedido, de acordo como calculo fornecido pelo responsável do setor.

**Conciliação do frete baseado em dados gerados pelo responsável do setor de frete**.

**Sobre Cálculos das Transportadoras**

## Correios

* Possui os serviços **PAC, SEDEX, E-SEDEX** _****_ e **PAC-GF**.
* Atende o Brasil todo e é o único que entrega em **CEP caixa postal**.

  > É um serviço que possibilita ao cliente alugar uma Caixa Postal em uma unidade dos Correios, para receber seus objetos de correspondência.

### Regras

* **PAC, SEDEX e PAC-GF**, aceita pedidos de até **30kg**, sendo esse cúbico ou real.
* **E-SEDEX** aceita até **15kg real ou cúbico**.
* Até **10Kg** cúbicos temos isenção de cubagem:
  * Exemplo: Pedido **ABC** com peso real de **5 KG** e peso cúbico de **9Kg**; então teremos a isenção do peso cúbico, pois é menor que **10Kg**.
* Para itens individuais
  * Os serviços **PAC, SEDEX** e **E-SEDEX** tem limite de **105 cm \(individual\)**  para maior medida, e **150 cm \(individual\)**  para o **PAC-GF**.
* Para itens em conjunto
  * **PAC**, **SEDEX** e **E-SEDEX** soma-se o Comprimento + Largura + Altura e caso for menor ou igual a **200 cm** segue o fluxo normalmente, caso contrário o fluxo é cancelado.
  * **PAC-GF** soma-se o Comprimento + Largura + Altura e caso for menor ou igual a **300 cm** segue o fluxo normalmente, caso contrário o fluxo é cancelado.

## Gollog

* Atende alguns **CEPs** espalhados no Brasil.
* Possui serviço de entrega expresso.
* Aceita pedidos de até **30Kg**, sendo este cúbico ou real.

### Regras

* Utiliza sempre o maior peso para a cobrança.
  * Exemplo **01:**  Pedido **ABC**
    * Peso real **15Kg**
    * Peso cúbico **25Kg**
  * O peso que será cobrado será o maior no caso peso cúbico **25Kg**
  * Exemplo **02:**  Pedido **CBA**
    * Peso real **5Kg**
    * Peso cúbico **2Kg**
  * O peso que será cobrado será o maior no caso peso real **5Kg**
* Não possui limite de maior medida
  * Porém a cubagem não poderá exceder o limite de **30Kg**.
* Valor da fatura e feita uma comparação com o valor que simulamos internamente.

## TNT e Mercúrio

* Atende todo Brasil exceto **CEP caixa postal** e **Fernando de Noronha**.
* Aceita pedidos com **peso real** de até **100kg**
* **Isento de cubagem**.
* Não possui limites de maior medida.
* Não possui limites de peso Cúbico.

### Regras

* **Mercúrio** não envia informações sobre o pesos e medidas dos produtos, então, todo cálculo feito é com base nas informações contidas no Ábacos.

## Regras Gerais

### Cálculos de simulação

#### Soma dos volumes

* É a soma dos volumes dos itens do pedido, dividido por **6000** que é o fator de cubagem.

#### Rateio de valores do frete

 **Correios e outros**

* A transportadora rateia os valores do frete, frente as informações dos produtos que compõe o pedido.
* Ábacos não possui estas informações separadas por itens.
  * Temos o valor total e a quantidade total de volume, então, o sistema **SIGECO** rateia em partes iguais para termos os valores individuais aproximados.

### Ad-valorem

* É o cálculo feito em cima dos valores dos itens

