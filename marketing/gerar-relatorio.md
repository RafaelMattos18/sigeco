# Gerar relatório

---

![](http://developers.connectparts.com.br/imagens/analytics01.png)

## Funcionalidade

Ao clicar na opção **Gerar Novo Token de Acesso** será direcionado para tela de acesso na conta Google, onde teremos a opção de selecionar por faixa de data ou por datas pré fixadas.

## Resultado

![](http://developers.connectparts.com.br/imagens/analytics02.png)

![](http://developers.connectparts.com.br/imagens/analytics03.png)


Será apresentado uma nova tela com as duas opções de relatório **Google Analytics** e **Google Adwords**. Ao clicar, será apresentada a seguinte mensagem "_Aguarde enquanto exportamos seu relatório._" e caso não algum inconsistência será apresentada a seguinte mensagem:

> _Relatório gerado com sucesso
Seu relatório foi gerado com sucesso! Os dados já podem ser consultados no banco 'Google Analytics'. _

---

### Descrição do projeto Analytics

Uma comunicação com o Google Analytics e Connect Parts, trazendo informações para os departamentos Marketing e B.I. Estas comunicações terão informações de custos por campanhas. As informações deverão segmentadas por Categoria, Subcategoria e Marcas. Estas informações irão agregar benefícios ao departamento comercia, como realizar investimentos estratégicos e mais assertivos.


### Fluxo do projeto

![](http://developers.connectparts.com.br/imagens/fluxoMktAnalytics.png)

Será desenvolvida uma rotina com timer definido, e esta rotina irá requisitar informações na API do Google Analytics que retorna
com as informações requisitadas. A rotina da ConnectParts com estas informações, a armazenará em um banco de dados (A). Do
lado do Business Intelligence haverá também uma rotina que irá consumir as informações no banco de dados da ConnectParts (A) e
armazenará e utilizará em seus cálculos e tomadas de decisões, em um bando de dados separado (B). 

#### Dados a ser consumidos na API Google Analytics

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

#### Particularidades

* Há campanhas que não possuem títulos, então o marketing fará uma pesquisa pelo campo **ga:sourceMedium** (Origem)

#### Regras

**Hora de execução**

No momento que acionar o relatório com Token de autenticação, as informações que virão serão definidas pelas faixas de datas selecionadas, porém, o Google libera estas informações somente no horário 00h.

**Inconsistência na execução**

* Caso tenha alguma inconsistência a rotina como, queda do servidor, instabilidade na internet, não será gravado nada em nossa tabela.