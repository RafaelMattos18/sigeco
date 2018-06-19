# Análise de Atributos

## Funcionalidade

Com base nos anúncios Connect, é realiza uma busca no mercado livre, através de cron \(que roda uma vez por semana\) trazendo todos os atributos disponíveis para uso e, diariamente, através de cron, busca todos os atributos cadastrados pela Connect.

A principal função da ferramentar, é fazer uma comparação entre os valores disponível e cadastrados, permitindo assim, uma ação de adequação e complementação do cadastro no mercado livre.É possível, caso necessário, ignorar atributos, para que não seja feita analise. Traz somente anúncios ativos.

## Regras

Existem dois serviços para coleta de informação. O primeiro, coleta todos os dados disponíveis para cadastro no mercado livre. O serviço é disparado aos finais de semana. O outro, coleta diariamente, todos os atributos cadastrados por anuncio \(D-1\).Hidden True. EAN e Código Universal são unificados.

## Processo

![](../../.gitbook/assets/image%20%288%29.png)

O campo 'Pesquisar' irá buscar os anúncios com base no 'Código Categoria'. E a caixa de seleção se o anúncio esta ignorado ou não.

![](../../.gitbook/assets/image%20%289%29.png)

No botão 'Comparar' irá abrir uma subtela\(Modal\) com as seguintes informações que vem também da Cron\(Serviço\). Ao clicar no botão 'Ignorar anúncio' ele ira ignorar o anúncio.

![](../../.gitbook/assets/image%20%2813%29.png)

Documento de Apoio: [http://developers.mercadolibre.com/pt-br/identificadores-de-produtos/](http://developers.mercadolibre.com/pt-br/identificadores-de-produtos/)

