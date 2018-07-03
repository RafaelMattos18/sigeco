# Regulador de Estoque

## Funcionalidade

O sistema irá fazer uma pesquisa em produtos que poderão ter suas margens alteradas, ou inserir as margem para alterar o novo valor.

## Processos

Quando fizermos contato com o fornecedor e o mesmo comunicar que o produto requisitado, terá um tempo para fabricar ou esta indisponível. O analista irá verificar o produto no SIGECO e poderá alterar a margem deste produto, para que sua venda diminua e que tenhamos estoque até a reposição.

O sistema apresenta todos os produtos que estão com as classes **Indisponível** e **Fora de Linha Connect**, dando a opção para o solicitante aumentar a margem do produto. Há também a opção de **importar lista**, nesta funcionalidade poderemos importar uma lista de produtos, com a possibilidade de fazer um upload de produtos que não estão nas classes descrita acima, porém, necessita que a margem seja alterada.

## Mockups

**img01**

![](http://developers.connectparts.com.br/imagens/reguladorEstoque01.png)

**img02**

![](../../.gitbook/assets/image%20%2814%29.png)

## Regras

1. Há um serviço que é executado toda as madrugadas as 02h.
2. As listas de produtos devem seguir estes títulos nas colunas:

   | Dk | email |
   | --- | --- |
   | 010203 | teste@connectparts.com.br |

   1. Como se escreve - **Dk** e **email**

3. Quando o valor do produto alterado for menor que o valor atual o sistema apresentará uma mensagem "_valor informado é menor que o valor atual_" e não deixará proesseguir a aprovação.
4. Se a **margem** da precificação for abaixo de **10%** o gestor irá receber um e-mail comentando sobre a aprovação de preço.
5. Somente os líderes poderão acessar esta tela.
6. Não será apresentada as informações que forem giro **0** e dias de estoque **0** e não será apresentado estoque maior que 45 dias.

## Responsabilidades

* **Comercial**
  * Fazer o upload da lista de **Dk** da maneira descrita nas regras **nº2** e **2.1**.
  * Fazer a aprovação ou reprovação dos produtos.
* **Desenvolvimento**
  * Manutenção da cron de serviços, como registrado na regra **nº01**.

