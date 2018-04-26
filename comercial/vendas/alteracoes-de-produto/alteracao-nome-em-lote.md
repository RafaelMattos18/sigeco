# Alteração nome em lote

![](http://developers.connectparts.com.br/imagens/alteracaoLote.png)

![](http://developers.connectparts.com.br/imagens/alteracaoLote01.png)

## Funcionalidade

Funcionalidade para alterar nome de produtos em lote.

Na alteração de produto do Sigeco, temos mais uma opção de realizar alteração de nomes em lote, como a alteração de preço e da classe dos produtos, esta funcionalidade irá otimizar o tempo.

## Regras

1. Será alterado o nome dos **DKs** que são iguais ao do **Pai**.
2. Quando o nome da variação for diferente do DK Pai, iremos apresentar uma mensagem de **insucesso**.
3. Para substituir o nome, basta alterar o **Nome** no arquivo xls, o sistema irá verificar se é o mesmo DK e irá substituir pelo mais recente.

## Responsabilidades

1. Ficará sob a responsabilidade do solicitante o envio do arquivo .xls do seguinte modo, inclusive na escrita correta das colunas: 

   ![](http://developers.connectparts.com.br/imagens/alteracaoLoteXls.png)

   1. **Pai**: Código do produto **Pai**
   2. **Email**: email do **solicitante**.
   3. **Nome**: Nome do produto a ser **alterado**.

