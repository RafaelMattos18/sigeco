# Alterações de Produtos

---

## Alteração de Nome

![](http://developers.connectparts.com.br/imagens/alteracoesProdutoAlteracaoNome.png)

### Funcionalidade

Nesta tela iremos alterar o nome do produto; a aprovação desta alteração esta no menu **Nomes Pendentes**.

#### Resultado

![](http://developers.connectparts.com.br/imagens/solicitacaoNomePendente02.png)

## Alteração de Preço

![alteracao de preco](http://developers.connectparts.com.br/imagens/SolicitarAlteracaoDeProduto02.png)

### Funcionalidade

Nesta opção iremos alterar o preço do produto, toda a regra de precificação esta descrita no abaixo.

![Regras dos codigos](http://developers.connectparts.com.br/imagens/alteracaoPrecos01.png)

Ao adicionar o código,clicar na lupa e passar o mouse sobre o ícone **i**, teremos informações sobre o processo que irá acontecer.

![Canais plataformas](http://developers.connectparts.com.br/imagens/alteracaoPrecos02.png)

Temos a opção que listas todas os canais que terão o preços alterados.

#### Resultado

![resultado da pesquisa](http://developers.connectparts.com.br/imagens/alteracaoPrecos03.png)

No resultado teremos algumas informações sobre o produto (_se é Pai, kit etc_) e um local para adicionar um **novo valor**. Haverá casos que teremos várias linhas de resultado, o sistema oferece um botão **Salvar** que ao adicionar um novo valor deve ser pressionado, salvando assim o valor. Para finalizar esta ação clique no botão **Enviar para aprovação** ou **Cancelar operação e remover**.


![](http://developers.connectparts.com.br/imagens/comercialSolicitacaoPrecoPendente02.png)

Na tela de **preços pendentes**, o sistema trará as informações do produto, quem foi o solicitante de alteração de preço e a data da solicitação e a ação de **Aprovar **ou **Reprovar**, no menu **Preços Pendentes** temos as regras de aprovação e reprovação destes valores.

> **Regras:** Os produtos que estiverem com preços mais de **7 dias sem aprovação serão automaticamente reprovados**. 

## Alteração de Nome

![](http://developers.connectparts.com.br/imagens/alteracaoLote.png)



alteracaoLoteXls.png

### Funcionalidade

Funcionalidade para alterar nome de produtos em lote.

Na alteração de produto do Sigeco, temos mais uma opção de realizar alteração de nomes em lote, como a alteração de preço e da classe dos produtos, esta funcionalidade irá otimizar o tempo.

### Regras

1. Será alterado o nome dos **DKs** que são iguais ao do **Pai**.
2. Quando o nome da variação for diferente do DK Pai, iremos apresentar uma mensagem de **insucesso**.

### Responsabilidades

1. Ficará sob a responsabilidade do solicitante o envio do arquivo .xls do seguinte modo: ![](http://developers.connectparts.com.br/imagens/alteracaoLoteXls.png)
	2. **Pai**: Código do produto **Pai**
	3. **Email**: email do **solicitante**.
	4. **Nome**: Nome do produto a ser **alterado**.

## Alteração de Classe

![](http://developers.connectparts.com.br/imagens/SolicitarAlteracaoDeProduto03.png)

### Funcionalidade

**Classe** é o status de um produto, podemos alterar este status que irá para aprovação no menu **Classes Pendente**.

![](http://developers.connectparts.com.br/imagens/resultadoAlteracaoClasse.png)

#### Resultado

![](http://developers.connectparts.com.br/imagens/comercialSolicatacoesClassesPendentes02.png)
    
## Alteração de Preço em Lote

![](http://developers.connectparts.com.br/imagens/SolicitarAlteracaoDeProduto04.png)

### Funcionalidade

Selecione a opção **Alteração de Preço em lote** e faça o upload do arquivo .xls. O arquivo deverá ter o layout abaixo:

![](http://developers.connectparts.com.br/imagens/modeloAlteracaoEmLote.png)
    

## Regras

## Alterações de Preços e Preços em lote 

### Se for Código PAI

**Caso contenha somente filhos KITS**

- Listar o **PAI** para precificar.
- Cada filho recebe o preço do **PAI**.
- Irá realizar o calculo de margem dos componentes baseado nesse preço do **PAI**.

**Caso contenha somente filhos NÃO KITS**

- Listar o PAI para precificar.
- Todos os filhos recebem o preço do PAI.
- Para cada filho, listar todos os kits que contém ele como componente (Não duplicar).
- Precificar cada kit individualmente, baseado nesse preço será realizado cálculo de margem dos componentes.

**Caso contenha somente filhos KITS e NÃO KITS**

- Listar o PAI para precificar.
- Todos os filhos não kit recebem o preço do PAI.
- Os filhos KIT recebem o preço do PAI * Qtde de componentes dentro dele.

### Se for Código FILHO

- Listar o Pai para precificar.
- Todos os filhos recebem o preço do PAI.
- Para o código do filho, listar todos os kits que contém ele como componente.

### Observações

- O produto Pai não possui preço de custo, então o sistema pega o preço do filho, para que seja gerado um valor aproximado.
- Remover a lista de preço ao realizar a solicitação.
- A lista agora será vinculada ao usuário, semelhante as grupos de produtos.
- Sempre que um usuário realizar uma alteração essa alteração será replicada a todas as listas que o usuário está vinculado.
- Todos poderão solicitar alteração de preço, independente da margem.
- Toda solicitação irá para o líder, caso o líder aprove e a solicitação seja abaxio de 10% essa solicitação irá para o gestor.
	- Se o solicitação for acima de 10% irá diretamente para o abacos.
- Independente da quantidade de KITs que serão listados, poderá ser alterado qualquer produto, sem travas.

> **A pedido do Marçal, não iremos desenvolver a precificação de kit em lote**.
