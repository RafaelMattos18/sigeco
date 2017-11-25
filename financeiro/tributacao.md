# Tributação

---

![](http://developers.connectparts.com.br/imagens/tributacao01.png

## Funcionalidade

Esta funcionaliade fará sistema de cálculos de margem de venda para o departamento financeiro. 

## Processo

Com esta ferramenta o financeiro terá uma tomada de decisão que será mais assertiva e lucrativa para a ConnectParts, no qual informações do DK e de fornecedores de linha PRIME ou não, tributações, tipo de empresa, estado de origem serão fatores que poderão alterar a margem final.

## Locais de acesso

http://sgc.dakotaparts.com.br/financeiro/tributacao/upload

http://sgc.dakotaparts.com.br/financeiro/tributacao/consulta

## Regras

### Valores fixos

Teremos os valores fixos de:

* **PIS e COFINS**
    * Esta informação será retirada do cadastro do fornecedor.
    * Tabela 02 – Tributação PIS - COFINS.
    * Pelo NCM, iremos executar o calculo
    * Quando for monofásico não faz calculo
    * Tributação normal faz calculo
        * Soma dos tributados 9,25%
* **IPI**
    * Nota Fiscal de Entrada.
* **ICMS Origem**
    * Nota Fiscal de Entrada ou Cadastro Fornecedor.


### Cálculo Custo ST

> _Dentro do estado_

**Partir do DK**
* NCM do Cadastro, Fornecedor (NF-Entrada), CST (NF-Entrada), estado de origem (NF-Entrada), IPI (NF-Entrada).

**Valor Total**

* Quantidade multiplicado pelo Valor Unitário.
    * Formula: =Quantidade * Valor Unitário

**Base Cálculo ICMS ST**

* Se DK não estiver vazio, soma-se (Valor Total com Frete e IPI), multiplicando o resultado de (1 mais MVA).
    * Formula: =SE (DK="";"";(Valor total + Frete + IPI) *(1 + MVA))
    
**ICMS ST**

* Se DK não estiver vazio, multiplica-se a Base de Cálculo com Alíquota Interna, subtraindo a soma do Valor total com Frete multiplicada pela Alíquota Interna ICMS.
    * Formula: =SE (DK="";"";(Base de Cálculo ICMS ST * Alíquota Interna ICMS) - ((Valor total + Frete) * Alíquota Interna ICMS))

**COFINS**

* Se DK não estiver vazio, multiplica-se Valor Total com COFINS.
    * Formula: =SE (DK="";"“; Valor Total * COFINS)

**PIS**

* Se DK não estiver vazio, multiplica-se Valor Total com PIS.
    * Formula: =SE (DK="";"“; Valor Total * PIS)

**IPI**

* Se DK não estiver vazio, multiplica-se Valor Total com IPI.
    * Formula: =SE (A4="";"“; Valor Total * IPI)

**Custo Líquido Total**

* Se DK não estiver vazio, soma-se Valor total com Frete e ICMS ST, subtraindo COFINS e IPI, somando IPI.
    * Formula: =SE (DK="";"“; Valor Total + Frete + ICMS ST – COFINS – PIS + IPI)

**Custo Líquido Unitário**

* Se DK não estiver vazio, divide-se Custo Líquido Total pela Quantidade.
    * Formula: =SE (DK="";"“; Custo Liquido Total / Quantidade)

**Custo Bruto Total**

* Se DK não estiver vazio, soma-se o Valor Total com Frete, ICMS ST e IPI.
    * Formula: =SE (DK="";"“; Valor Total + Frete + ICMS ST + IPI)

**Custo Bruto Unitário**

* Custo Bruto Total dividido pela Quantidade.
    * Formula: =Custo Bruto Total / Quantidade
    
#### ST recolhida anteriormente

**Valor Total**

* Quantidade multiplicada pelo Valor Unitário
    * Formula: =Quantidade * Valor Unitário

**COFINS, PIS e IPI**

* Se DK não estiver vazio, multiplica o Valor Total vezes o COFINS ou PIS ou IPI.
    * Formula: =SE (DK="";"“; Valor Total * COFINS)
    * Formula: =SE (DK="";"“; Valor Total * PIS)
    * Formula: =SE (DK="";"“; Valor Total * IPI)

**Custo Líquido Total**

* Se DK não estiver vazio, soma-se Valor total com Frete e ICMS ST, subtraindo COFINS e IPI, somando IPI.
    * Formula: =SE (DK="";"“; Valor Total + Frete – COFINS – PIS + IPI)

**Custo Líquido Unitário**

* Se DK não estiver vazio, divide-se Custo Líquido Total pela Quantidade.
    * Formula: =SE (DK="";"“; Custo Liquido Total / Quantidade)

**Custo Bruto Total**

* Se DK não estiver vazio, soma-se o Valor Total mais IPI.
    *  Formula: =SE (DK="";"“; Valor Total + IPI)

**Custo Bruto Unitário**

* Custo Bruto Total dividido pela Quantidade.
    * Formula: =Custo Bruto Total / Quantidade


#### Cálculo Custo ICMS

> Custo

**Valor Total**

* Para chegarmos ao Valor Total, multiplica a Quantidade vezes Valor Unitário.
    * Formula: =Quantidade * Valor Unitário

**Base Cálculo ICMS**

* No caso de Custo para a Base Cálculo ICMS é o Valor Unitário do produto.

**ICMS**

* Com o Valor Total do produto multiplica-se o valor do ICMS.
    * Formula: =Valor Total * ICMS

**COFINS, PIS e IPI**

* Se DK não estiver vazio, multiplica o Valor Total vezes o COFINS ou PIS ou IPI.
    * Formula: =SE (DK="";"“; Valor Total * COFINS)
    * Formula: =SE (DK="";"“; Valor Total * PIS)
    * Formula: =SE (DK="";"“; Valor Total * IPI)

**Custo Bruto Total**

* Se Valor Unitário não estiver vazio, soma-se Valor Total com IPI.
    * Formula: =SE (Valor Unitário="";""; Valor Total + IPI)

**Custo Bruto Unitário**

* Se Valor Unitário não estiver vazio, divide-se Custo Bruto Total pela Quantidade.
    * Formula: = SE (Valor Unitário ="";"“; Custo Bruto Total / Quantidade)

**Custo Líquido Total**

* Se DK não estiver vazio, soma-se Valor total com Frete e ICMS ST, subtraindo COFINS e IPI, somando IPI.
    * Formula: =SE (DK="";"“; Valor Total – ICMS – COFINS – PIS + IPI)

**Custo Líquido Unitário**

* Se DK não estiver vazio, divide-se Custo Liquido Total pela Quantidade.
    * Formula: =SE (DK="";"“; Custo Liquido Total / Quantidade)
    
#### Simulação de venda

**ICMS, PIS e COFINS**

* O valor do ICMS é conseguido com o Preço de Venda vezes Alíquota Interna do ICMS ou IPI ou PIS.
    * Formula: =Preço de Venda * Alíquota Interna do ICMS no estado SP
    * Formula: =Preço de Venda * IPI
    * Formula: =Preço de Venda * COFINS

**Preço de Venda Líquido**

* Preço de venda liquido é o resultado da subtração de Valor de Vendas, ICMS, PIS, COFINS.
    * Formula: =Valor de Vendas – ICMS – PIS - COFINS

**Margem**

* Para conseguir a margem, subtraímos Preço de Venda Líquido menos Custo Líquido, dividido por Preço de Venda.
    * Formula: = (Preço de Venda Liquido – Custo Líquido) / Preço de Venda.








