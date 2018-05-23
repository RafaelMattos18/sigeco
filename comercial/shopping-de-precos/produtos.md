# Produtos

![](http://developers.connectparts.com.br/imagens/SDPprod01.png)

## Funcionalidade

Nesta tela teremos uma listagem de produtos da Connect Parts; em cada linha de produtos informações sobre ele dentro do mercado livre.

## Processo

O departamento comercial e processo, utiliza esta ferramenta para mensurar uma métrica e agir de forma que sejamos mais competitivos no mercado livre. Os filtros que estão na tela, irão auxiliar os departamentos no afilamento de informações.

### Filtros

* DK ou Pai
  * Pesquisas específicas pelo DK do produto ou seu código Pai
* Título Anúncio ou Ábacos 
  * Descrição do título no Mercado Livre ou no ERP 
* Status dos Anúncios
  * Tudo
    * Todos os status dos anúncios e anúncios que não estão publicado
  * Tem anúncios ativos, pausados, encerrados ou com qualquer status
  * Não tem anúncios publicados
* Categoria
  * Categorias cadastradas no Mercado Livre
* Grupo
  * Grupo que o produto perntece
* Marca
* MLB
  * Código do produto no Mercado Livre
* Vendedor Concorrente
  * Descrição do título do concorrente que deseja pesquisar
* Relações
  * Tem concorrente relacionado, há concorrentes rejeitados, qualquer tipo de relação, os que não tem relacionamentos feitos, 
* Situação
  * Situação é a campo de seleção onde irá filtrar produtos que estamos perdendo, ganhando, empatados em relação aos preços.
* Modalidade
  * Modalidade que o produto esta cadastrado no Mercado Livre
* Frete Grátis
* Desconto
  * Descontos aplicados nos produtos.

## Resultado

![](http://developers.connectparts.com.br/imagens/SDPprod02.png)

Para a listagem, temos a opção de ordenar os resultados, exibição de títulos no Mercado Livre ou Ábacos e paginação.

### Detalhes

Mostra todos os nossos produtos que selecionado na tela anterior, trazendo nesta funcionalidade informações sobre estes produtos como, título, MLB, se há Frete Grátis, dimensões e garantia, valores e percentual de margem ganhando ou perdendo, status deste produto, quantidade de vendidos e quantidade de disponíveis para venda.

#### Históricos

* **Vendas**

![](http://developers.connectparts.com.br/imagens/spdBosta01.png)

Histórico de quantidades vendidas

* **Preço**

![](http://developers.connectparts.com.br/imagens/spdBosta02.png)

Histórico de alterações de preços

* **Relatório**

![](http://developers.connectparts.com.br/imagens/spdBosta03.png)

Histórico de Preço, Diferença Preço, Variação Preço, Vendas, Diferença Vendas, Frete Grátis e Data/Hora.

### Relações

![](http://developers.connectparts.com.br/imagens/spdBosta04.png)

Traz informações de produtos similares dos concorrentes, onde temos a base de comparação de valores. Podemos verificar o **histórico** do concorrente, **remover esta relação** e **rejeitar**.

### Buscar Concorrentes

Ao clicar na opção **Buscar Concorrentes** o sistema nos traz informações sobre o produto da ConnectParts e produtos similares de concorrentes.

![](http://developers.connectparts.com.br/imagens/buscarCorrentes01.png)

![](http://developers.connectparts.com.br/imagens/buscarCorrentes02.png)

Ao clicar em **Pesquisar** é demonstrada informações do Mercado Livre com produtos similares de concorrentes, podemos esconder anúncios da **Connnectparts**.

![](http://developers.connectparts.com.br/imagens/buscarCorrentes03.png)

Podemos relacionar este produto; e após esta relacção o sistem dentro de uma margem de valores máximo e mínimo irá demonstrar se estamos perdendo ou ganhando com a venda deste produto.

## Regras

* Um anúncio pode ter no máximo 300 anúncios relacionados.
* Há um espaço de tempo da construção do anúncio até sua exposição na listagem desta funcionalidade e amostragem no Mercado Livre, este tempo é em torno de 24horas.
* Em relacionados, a captação de valores será sempre um dia atrás.
* Recuperamos estas informações sempre via API.

