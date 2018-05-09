# Alteração de preco

![alteracao de preco](http://developers.connectparts.com.br/imagens/SolicitarAlteracaoDeProduto02.png)

## Funcionalidade

Nesta opção iremos alterar o preço do produto, toda a regra de precificação esta descrita no abaixo.

![Regras dos codigos](http://developers.connectparts.com.br/imagens/alteracaoPrecos01.png)

Ao adicionar o código,clicar na lupa e passar o mouse sobre o ícone **i**, teremos informações sobre o processo que irá acontecer.

![Canais plataformas](http://developers.connectparts.com.br/imagens/alteracaoPrecos02.png)

Temos a opção que listas todas os canais que terão o preços alterados.

## Resultado

![resultado da pesquisa](http://developers.connectparts.com.br/imagens/Previa_precos.png)

No resultado teremos algumas informações sobre o produto \(_se é Pai, kit etc_\) e um local para adicionar um **novo valor**. Haverá casos que teremos várias linhas de resultado, o sistema oferece um **Salvar** que ao adicionar um novo valor ele é salvado temporariamente, e é mostrado a margem do valor inserido. Conforme o valor do Pai for alterado o valor dos Kits também será alterado automaticamente. Para finalizar esta ação clique no botão **Enviar para aprovação** ou **Cancelar operação e remover**.

> **Observação**: Ao adicionar um valor em percentual no campo **Novo Valor** isto irá impactar no **Valor Por** em _Preços Pendentes_

![](http://developers.connectparts.com.br/imagens/comercialSolicitacaoPrecoPendente02.png)

Na tela de **preços pendentes**, o sistema trará as informações do produto, quem foi o solicitante de alteração de preço e a data da solicitação e a ação de **Aprovar **ou **Reprovar**, no menu **Preços Pendentes** temos as regras de aprovação e reprovação destes valores.

Obs: A nova formula para rateio de valores quando se trata de um KIT consiste em encontrar a margem bruta 1-custo bruto individual/preço venda individual. Encontrar a margem de desconto calculando desconto que é a diferença entre o valor do kit e o valor do produto individualmente somado e dividir por Preço de venda individual.
Finalmente para encontrar o novo valor do componente deve-se aplicar a formula Preço de Venda Inidividual Componente - (preço de venda inidividual do componente/pela margem de desconto calculada anteriormente.

> **Regras:** Os produtos que estiverem com preços mais de **7 dias sem aprovação serão automaticamente reprovados**.

