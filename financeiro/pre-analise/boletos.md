# Boletos

---

![ReversaoBoleto](http://developers.connectparts.com.br/imagens/reversaoBoletoMKP02.png)

## Funcionalidade

O sistema mostrará os boletos captados e listar quais não foram pagos do dia anterior e não compraram com outra forma de pagamento, para que haja uma ação junto com cliente.

### Processos

1. Após a Conciliação de Boleto Bancário, as 10h será feita uma busca na **VTEX** que relaciona todos os pedidos de boletos não pagos do dia anterior, consultando se o CPF já tem alguma compra feita naquela data e salvos no banco de dados. A consulta dos usuários será feita diretamente neste banco (o que torna o processo rápido ao usuário).
> O sistema fará a verificação automáticamente após as 10h.

2. Será exibida uma lista com: **NOME, CPF, DATA DA COMPRA, STATUS** (verificado ou não verificado), a ordenação deste resultado será pelos boletos mais antigos.

3. Toda vez que for feita uma ação para com o cliente, teremos um botão de **Análise** que irá retirar esta informação da lista.

4. Os resultados serão apresentados sem filtros

5. Iremos manter as informações não analisadas durante 2 dias no sistema. O sistema irá limpar estas informações automaticamente.

6. Iremos gerar um relatório (.xls) somando a quantidade de boletos que foram pagos, para conseguir um média de desempenho. Neste relatório teremos a data de pagamento e quantidade de boletos pagos por dia.

## Resultado

![ReversaoBoleto](http://developers.connectparts.com.br/imagens/reversaoBoletoMKP.png)

Ao confirmar a ação de verificação do resultado.

![ReversaoBoleto](http://developers.connectparts.com.br/imagens/reversaoBoletoMKP03.png)

### Regras

Pesquisas na VTEX:

* Capturar pedidos de boletos do dia anterior.

* Todos que não foram pagos.

* Verificar se o boleto tem outra compra com os mesmos itens e outra forma de pagamento.

* Não teremos controle sobre outros MarketPlaces que não passam pela VTex, por exemplo, Mercado Livre.

* Teremos que ter no resultado apresentado uma confirmação de análise, assim que o analista entrar em contato com o cliente clicar nesta opção.

* Iremos demonstrar durante 2 dias, as datas de pagamento dos boletos que foram analisados e tiveram pagamento efetuado.



