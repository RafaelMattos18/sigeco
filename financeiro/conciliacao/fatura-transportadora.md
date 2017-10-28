# Fatura Transportadora

---

![](http://developers.connectparts.com.br/imagens/freteTransportadora01.png)

## Funcionalidade

Fazer conciliações de valores do arquivo .xls que as transportadoras nos envia em arquivos .xls de tabelas de CEP e valores que a ConnectParts possui.

## Resultado

![](http://developers.connectparts.com.br/imagens/freteTransportadora02.png)

Traz os resultados da conciliação, como transportadora, data de processamento e vencimento, quantidade de registros processados, quantidade de reversos e caso tenha erros apresenta a quantidade. Em opções podemos **Exportar** para verificar o erros apresentados ou **Excluir** a conciliação.


### Processos

![](http://developers.connectparts.com.br/imagens/freteTransportadora04.png)

### Regras

![](http://developers.connectparts.com.br/imagens/freteTransportadora03.png)

Os Relatórios AWB da transportadora Gollog devem ser agrupados em um único arquivo Excel. 
> Obs.: Este arquivo pode conter mais de uma planilha. 

#### Rodonaves

* A ConnectParts está insenta de cobrança de peso **cubado**, caso o valor do peso base seja o mesmo do valor cubado e diferente do valor real, retorna um erro.
* A tabela de peso da Rodonaves aceita até **100kg**, caso o valor do peso base que estiver na planilha for maior, retorna um erro.



