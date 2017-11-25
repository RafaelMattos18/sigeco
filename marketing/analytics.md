# Marketing Google Analytics

---

## Descrição do projeto

Uma comunicação com o Google Analytics e Connect Parts, trazendo informações para os departamentos Marketing e B.I. Estas comunicações terão informações de custos por campanhas. As informações deverão segmentadas por Categoria, Subcategoria e Marcas. Estas informações irão agregar benefícios ao departamento comercia, como realizar investimentos estratégicos e mais assertivos.

## Fluxo do projeto

![](http://developers.connectparts.com.br/imagens/fluxoMktAnalytics.png)

Será desenvolvida uma rotina com timer definido, e esta rotina irá requisitar informações na API do Google Analytics que retorna
com as informações requisitadas. A rotina da ConnectParts com estas informações, a armazenará em um banco de dados (A). Do
lado do Business Intelligence haverá também uma rotina que irá consumir as informações no banco de dados da ConnectParts (A) e
armazenará e utilizará em seus cálculos e tomadas de decisões, em um bando de dados separado (B). 

### Dados a ser consumidos na API Google Analytics

**Relatório de Ids de transação, origem / mídia, campanha, data, transações e valor de transação**:

* Dimensões: ga:transactionId, ga:sourceMedium, ga:date, ga:campaign
* Métricas: ga:transactions, ga:transactionRevenue
    * Caso queira dividir valor da receita pelo número de transações para duplicar transações
*Filtro para pegar apenas Google Adwords: ga:sourceMedium==google / cpc


**Relatório de Custo de Google Adwords**:

* Dimensões: ga:sourceMedium,ga:campaign,ga:date
* Métricas: ga:adCost, ga:adClicks, ga:impressions
    * Caso queiram ver cliques e impressões também
* Filtro: ga:sourceMedium==google / cpc

### Particularidades

* Há campanhas que não possuem títulos, então o marketing fará uma pesquisa pelo campo ga:sourceMedium (Origem)

### Regras

1. **Hora de execução**
    A rotina será executada todo dia as 00:00horas.

2. **Inconsistência na execução** 
    Caso tenha alguma inconsistência a rotina como, queda do servidor, instabilidade na internet, não será gravado nada em
nossa tabela.

3. **Tempo de armazenagem** 
    As informações na tabela da parte do Desenvolvimento / Inovação serão mantidas até a próxima requisição. Então o serviço de consultar e gravar estas informações por parte do B.I deverá agir neste período.