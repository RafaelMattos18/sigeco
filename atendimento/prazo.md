# Prazo

---

![CalculoPrazoFrete](http://developers.connectparts.com.br/imagens/calucloPrazoFrete01.png)

## Funcionalidade

Nesta funcionalidade o sistema traz informações sobre o pedido pesquisado.Com o objetivo de termos prazos corretos para informar aos clientes, diminuindo as reclamações de PIs desnecessárias

## Processo

Atendimento insere o número do pedido e através deste número o sistema identifica o **canal de venda do pedido**, onde busca o prazo correto nas tabelas **já inseridas no SIGECO**, somando com o prazo que cada canal tem individualmente, no qual será o prazo que o cliente já recebeu na hora da compra; **este prazo será lido em dias úteis**, iremos somar o prazo estabelecido internamente através das tabelas (_inseridas pelo departamento de frete_) avisando o cliente sobre um possível atraso.

## Resultado

![CalculoPrazoFrete](http://developers.connectparts.com.br/imagens/calucloPrazoFrete02.png)

rt

<!-- ![](http://developers.connectparts.com.br/imagens/calucloPrazoFrete03.png)-->

![InformacoesDoPedido](http://developers.connectparts.com.br/imagens/calucloPrazoFrete04.png)

* Informações sobre o pedido e a opção de rastreio.

![InformacaoCliente](http://developers.connectparts.com.br/imagens/calucloPrazoFrete05.png)

* Informações sobre o cliente que executou o pedido.

![ItensPedidp](http://developers.connectparts.com.br/imagens/calucloPrazoFrete06.png)

* Informações sobre o Kit (_caso o cliente tenha adquirido_), estoque, valores; informações sobre os produtos individuais ou os que compõe o kit.

![HistoricoPedido](http://developers.connectparts.com.br/imagens/calucloPrazoFrete07.png)

* Informações sobre o status do pedido, observações e nome de colaboradores que tiveram alguma ação com o produto.

### Regras

1. Ao se tratar de **Correios**, será verificado o prazo na API dos correios somando o dia do despacho com o prazo informado, se o prazo estiver vencido, será informado **“Abrir um PI”** caso contrário **”No prazo dos Correios”**.

2. Teremos um prazo geral que é prometido segundo as tabelas inseridas, **quando for Correios teremos dois prazos. Prazo dado ao cliente** e o que os **Correios nos oferece**.
Iremos verificar nas tabelas dos Correios caso este dentro do prazo.

3. Pode gerar as seguintes situações:

	1. Os prazos em ambos podem estar iguais.
	
	2. O prazo que prometemos ao cliente está correto, porém os correios passaram o prazo divergente, então poderá ser aberto uma divergência com os Correios.
	
	3. Caso o prazo que passamos ao cliente venceu, porém, o passado pelos correios está dentro do prazo, isto ocorre quando atrasamos a entrega (_visto que os prazos do correios começa a contar de quando nós despachamos o produto_)

