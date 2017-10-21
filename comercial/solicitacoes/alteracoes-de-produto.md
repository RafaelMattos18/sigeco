# Alterações de Produtos

---

## Alteração de Nome

![](http://developers.connectparts.com.br/imagens/alteracoesProdutoAlteracaoNome.png)

### Funcionalidade

Nesta tela iremos alterar o nome do produto; a aprovação desta alteração esta no menu **Nomes Pendentes**.

#### Resultado

![](http://developers.connectparts.com.br/imagens/solicitacaoNomePendente02.png)

## Alteração de Preço

![](http://developers.connectparts.com.br/imagens/SolicitarAlteracaoDeProduto02.png)

### Funcionalidade

![](http://developers.connectparts.com.br/imagens/alteracaoPrecos01.png)

![](http://developers.connectparts.com.br/imagens/alteracaoPrecos02.png)


#### Resultado

![](http://developers.connectparts.com.br/imagens/comercialSolicitacaoPrecoPendente02.png)

Temos as informações do produto, quem foi o solicitante de alteração de preço e a data da solicitação e a ação de Aprovar ou Reprovar.

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

- Remover a lista de preço ao realizar a solicitação.
- A lista agora será vinculada ao usuário, semelhante as grupos de produtos.
- Sempre que um usuário realizar uma alteração essa alteração será replicada a todas as listas que o usuário está vinculado.
- Todos poderão solicitar alteração de preço, independente da margem.
- Toda solicitação irá para o líder, caso o líder aprove e a solicitação seja abaxio de 10% essa solicitação irá para o gestor.
	- Se o solicitação for acima de 10% irá diretamente para o abacos.
- Independente da quantidade de KITs que serão listados, poderá ser alterado qualquer produto, sem travas.

> **A pedido do Marçal, não iremos desenvolver a precificação de kit em lote**.
