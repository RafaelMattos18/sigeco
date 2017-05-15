# Tributação

---

## Descrição
Desenvolvimento de um sistema de cálculos de margem de venda, no qual informações do DK e de fornecedores de linha PRIME ou não, tributações, tipo de empresa, estado de origem serão fatores que poderão alterar a margem final. Com esta ferramenta o financeiro terá uma tomada de decisão que será mais assertiva e lucrativa para a ConnectParts.

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



