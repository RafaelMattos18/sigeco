# Tributação

---

## Descrição
Desenvolvimento de um sistema de cálculos de margem de venda, no qual informações do DK e de fornecedores de linha PRIME ou não, tributações, tipo de empresa, estado de origem serão fatores que poderão alterar a margem final. Com esta ferramenta o financeiro terá uma tomada de decisão que será mais assertiva e lucrativa para a ConnectParts.

## Regras

**Valores fixos**

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


