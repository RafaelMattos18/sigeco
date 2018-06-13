# Análise de Atributos

## Funcionalidade

Comparar atributos de anúncios do Mercado Livre cadastrados com atributos disponíveis.

## Regras

Uma Cron\(Serviços\) que coleta as informações dos atributos dos anúncios na madrugada, ou seja ele irá pegar anúncios do dia anterior\(D - 1\). São considerados atributos com relevância 1 ou nullo, sempre trazendo SKU. Não são considerados atributos com 'tag hiden'\(tag escondida\). 

![](../../.gitbook/assets/image%20%2810%29.png)

## Processo

A campo 'Pesquisar' irá buscar os anúncios com base no 'Código Categoria'. E a caixa de seleção se o anúncio esta ignorado ou não.

Obs: Liberar o download dos arquivos no navegador.

![](../../.gitbook/assets/image%20%286%29.png)

No botão 'Comparar' irá abrir uma subtela\(Modal\) com as seguintes informações que vem também da Cron\(Serviço\). Ao clicar no botão 'Ignorar anúncio' ele ira ignorar o anúncio.

![](../../.gitbook/assets/analise_de_atributos_2.png)

Documento de Apoio: [http://developers.mercadolibre.com/pt-br/identificadores-de-produtos/](http://developers.mercadolibre.com/pt-br/identificadores-de-produtos/)

