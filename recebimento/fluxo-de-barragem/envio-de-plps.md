# Envio de PLPs

![](http://developers.connectparts.com.br/imagens/fluxoBarragem01.png)

## Funcionalidade

Comunicação com a central dos correios, barrando o rastreio que é suspeito de fraude.

## Processo

Esta ferramenta em que o cliente \(**Connect**\) irá comunicar a central dos correios que o rastreamento que é suspeito de fraude, automaticamente e garantindo que o departamento de **recebimento** irá dar continuidade a este pedido até sua finalização. O sistema armazenara esse rastreio e trará o último status para o acompanhamento. Tem como base um arquivo de EDI que é gerado no Ábacos, o sistema lê este arquivo e cria um arquivo no formato padrão exigido pelo **correios**. Após esta ação , o arquivo é enviado e processado, retornando o ID-PLP e o ID-PLPCliente, que são dados necessários para o bloqueio. Existe uma aba chamada "Críticas" onde quando se sobe um arquivo através do botão enviar no lado esquerdo em que o arquivo é processado e é demonstrada as críticas do mesmo.

Para processar os arquivos para as críticas o mesmo se encontram no caminho: \\nas\EDI\_Expedicao\correios1

Ao lado do botão **Enviar** temos a opção de fazer um upload do arquivo **PLP**

## Resultado

![](../../.gitbook/assets/image.png)

![](../../.gitbook/assets/image%20%2810%29.png)

Informações sobre os pedidos com a possibilidade de **Barrar ocorrência**.

## Regras

**Para barragem**

1. Várias compras para o mesmo CEP ou mesmo CPF.
2. Somente para o Correios.
3. Endereço suspeito.
4. Compras duplicadas.

### Observação

* Há uma possibilidade minima por parte dos Correios que este pedido **NÃO** seja barrado.

## Responsabilidades

* Ficará sob a responsabilidade do departamento de Processos a cobrança do acompanhamento do pedido barrado até sua finalização.
* Ficará sob a responsabilidade do departamento de Desenvolvimento e Inovação o desenvolvimento da ferramenta e a nossa comunicação até o Correios e o tratamento de retorno e a disponibilização no SIGECO desta informação de barragem para o departamento responsável.

