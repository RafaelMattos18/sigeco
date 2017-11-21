# BLACK FRIDAY

[![N|Solid](https://connectparts.vteximg.com.br/arquivos/logo-connect.png)](https://nodesource.com/products/nsolid)

[![N|Solid](https://cdn.arstechnica.net/wp-content/uploads/2014/02/warning-640x360.png)](https://nodesource.com/products/nsolid)

## Problemas conhecidos!

### Precificação

A precificação ocorre em duas etapas principais. 

1. **A primeira** delas é no gerenciador de tarefas, onde a tarefa "AtualizarPrecos" é responsável por capturar as solicitações de alteração feitas pelo usuário, tratar as mesmas e então joga-las no KPL/ABACOS.

2. **A segunda** é o gerenciador de Integrações na tarefa IntegracaoPreco, essa tarefa é responsável por consumir uma fila de alterações disponibilizada pelo KPL/ABACOS, e então tratar as alterações e então grava-las no VTEX.

### Possíveis problemas.

**Verificar se a fila de solicitações esta sendo consumida corretamente.**

Para fazer isso existem duas maneiras:

**A primeira** é via banco de dados, localize o banco de dados denominado PrecificacaoCadastro e a tabela SOLICITACOES. Na mesma execute a query:

	```
	SELECT * FROM [PrecificacaoCadastro].[dbo].[Solicitacoes] 
	WHERE SolicitacaoStatusCodigo = 2 
	AND SolicitacaoTipoCodigo IN (3,4);
	```
Onde SolicitacaoStatusCodigo 2 indica que a solicitação foi aceita e esta pronta para ser integrada e os tipos 3 e 4 são alteração de preço em lote e normal.

**A segunda** opção é consumir a API de solicitações com os mesmos parametros. Caso essa fila apresente um resultado muito grande pode ser que a **primeira** Tarefa esteja com problemas. Um debug nessa situação pode ajudar a encontrar o problema onde os mais conhecidos são:

1. **A tarefa não esta sendo executada**.
	- Tente reiniciar a cron.
	- Verifique se o servidor esta ligado.
	- Pare a POOL no IIS e delete o banco GerenciadorDeIntegracoes, Crie novamente e Reinicie a POOL no IIS.

2. **O campo ProdutoPreçoListaCodigo estar vazio ou com codigo errado**.
	- Delete as linhas afetadas do banco e pessa para o usuário precificar novamente em lote se atentando para o campo plataforma.
	- Verifique se são todos da mesma plataforma e de um update no banco para ajudar o usuário.

3. **O Abacos esta retornando uma mensagem de erro**.
	- Normalmente quando o abacos retorna uma mensagem de erro ela é bem clara para facilitar na solução do problema, porém para chegar na mesma é necessário de debug ou então solicitar para a TI o log do erro (Não recomendado devido a alta demora, normalmente 35 dias em média).

4. **Verificar se o gerenciador de Integrações esta atualizando a VTEX**. 
	- Para verificar a extensão da fila de integrações utilize o painel na TV ou no endereço http://192.168.0.179:8069/. Se a fila estiver muito grande o problema esta ai. Nesse caso o procedimento pode ser que o serviço esteja parado ou com erros.

5. **A tarefa não esta sendo executada**.
 	- Tente reiniciar a cron.
 	- Verifique se o servidor esta ligado.
 	- Pare a POOL no IIS e delete o banco GerenciadorDeTarefas, Crie novamente e Reinicie a POOL no IIS.

6. **A VTEX retorna mensagem de erro**.
	- Normalmente quando isso acontece é que o produto não esta ainda na VTEX, nesse caso deve-se observar se o mesmo esta apresentando erros no log de integrações VTEX localizado no SIGECO.
    - Instabilidade na VTEX, com debug da para perceber que o tempo medio de resposta subiu muito. Normalmente é de 2 a 5 segundos, porém ja tivemos periodos em que esse tempo de resposta atingiu 5 minutos. Nesse caso dobre os joelhos e recomendo uma oração de todo coração, porque nada é impossível para DEUS.

## Integração de Pedidos

A integrações de Pedidos Possui duas vias principais, a primeira são os pedidos oriundos da Vtex, esses já estão centralizados a loja virtual e ainda os marketplaces diversos que possuímos. A segunda via são os produtos do MercadoLivre que são integrados via 00K, esses os unicos que são nossas resposábilidades são os de DROPSHIPPING.

Possíveis problemas.

1. A tarefa não esta sendo executada.
	- Tente reiniciar a cron.
	- Verifique se o servidor esta ligado.
	- Pare a POOL no IIS e delete o banco GerenciadorDeIntegracoes, Crie novamente e Reinicie a POOL no IIS.

2. Possível falha na integração do pedido é hora de debug

3. Não foi localizada a plataforma. 
	- Todo pedido da VTEX vem com o código iniciado com as siglas das plataformas, por exemplo MZN-9249294, seguindo nosso código existem um momento em que ele tenta localizar esse MZN em uma listagem e localizar a origem do pedido. Caso a sigla não esteja na lista pode ser a origem do problema.

4. Não foi localizado o pagamento. 
	- Assim como no caso acima explicado existe a mesma listagem para forma de pagamento, e pode ser que não esteja conteplada igualmente.

5. O valor da forma de pagamento diverge do valor do Pedido. 
	- Nesse caso é necessário abrir um chamado ao TI para que solicitem a correção na VTEX. Existe uma tratativa hoje para que ele pegue esse valor restante e jogue para um campo de outras despesas, porém não abrange todas as possibilidades.
	
6. Não foi cadastrado a plataforma ou forma de pagamento na interface. 
	- Esse tipo de erro pode ser capturado no debug com a resposta do inserir pedido no abacos ou então em um log do abacos(mais uma vez não recomendado por ser necessário aguardar a TI.). Se for uma resposta positiva de que falta uma determinada plataforma ou forma de pagamento no abacos é necessário solicitar a TI para cadastrar a mesma, e com o retorno do código que o Tecnico irá te passar você deve alterar o código e inserir o mesmo na lista de possíveis formas de pagamento.

7. Produto não localizado na listagem do dropshipping. 
	- Nesse caso existem dois cenarios disponíveis, o pedido não foi integrado ou foi integrado.

	8. **Caso tenha sido integrado** deve ser aberta uma solicitação para a exclusão do mesmo com o pessoal do faturamento, eles podem optar por lançar os dois novamente separados ou solicitar uma nova integração.

	9. **Caso tenha que fazer uma nova integração do pedido não entre em panico**. 
		- O primeiro passo é abrir a solution IntegracoesAbacos. Comente todas as chamadas de tarefa com return;. Menos a que você for utilizar.
Então você deve localizar a sua tarefa alvo, caso seja VTEX vá até IntegracaoPedido.cs, e encontre a linha 111. Ela normalmente esta comentada com o exemplo a seguir, //_vtexServicosExternos.CriarParametro("q","XXXXXXXXXX"). Aqui é um passo simples, comente as 4 linhas acima dela de parametros e descomente apenas a 111 e então substitua os XXXXXXXXX pelo numero do pedido. Antes de realizar essa integração observe o passo 2.5.2 e confira se esta tudo correto. Então basta executar e acompanhar o processo até o final. No caso de se tratar de 00K localize IntegracaoPedidoZeroZeroK.cs e então a linha 270, como no exemplo a seguir //_zzkServicosExternos.CriarParametro("external_id","XXXXXXXX"). Como no processo anterior é necessario comentar as 3 linhas acima de parametro e deixar apenas a que vai utilizar mais uma vez substituindo os XXXXXX pelo pedido. Antes de fazer essa integração verificar o passo 2.5.1 e se necessário o 2.5.1.1. Então basta acompanhar a integração até o final.

10. Caso esteja lidando com 00K é necessário ver se o produto esta ativo na plataforma.
	- Existe uma tabela no banco dropshipping denominada Produtos00K, tente localizar o produto na mesma antes de mais nada.

11. Caso não localize vá até o sigeco e entre na listagem de produtos 00K localize o mesmo e o ative.

12. Caso seja Vtex vá até a lista no banco Dropshipping tabela Produtos, o mesmo deve constar lá e possuir preço de custo preenchido. 
	- Caso não esteja lá o produto deve ser localizado o responsavel por essa lista no comercial.