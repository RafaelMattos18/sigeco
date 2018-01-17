# Preços Pendentes

---

![](http://developers.connectparts.com.br/imagens/comercialSolicitacaoPrecoPendente01.png)

## Funcionalidade

Nesta tela temos um relatório de produtos que sofreram alteração de preço pelo analistas/assistentes ou tivemos sugestão de preço enviada pela [SIEVE](https://www.sieve.com.br/sobre). O líder toma a decisão de reprovar ou aprovar esta solicitação.


### Processos

1. O fluxo para o usuário final continua o mesmo, apenas o backend da aplicação mudou.

## Regras

1. Caso o produto **não tenha nenhum valor em uma das suas listas de preços**, será retornado um e-mail para ao solicitante avisando a falta deste valor.

2. Caso **tenha valor somente em uma das listas** o calculo da margem será feito com base no existente.
3. **Regras na Solicitação de Preço**: Ao receber a solicitação de preço a API de precificação e cadastro aplica as regras
    2. Recalcula a margem do produto
        3. Caso seja abaixo de 10% alteração gera uma solicitação ao grupo proprietário para 9000 (Grupo master)
        4. Adiciona no campo de observação a mensagem “Margem menor que 10% !!!”
5. Sistema de precificação da Sieve também foi adaptado para quando gerar um solicitação com preço abaixo de 10% ir para o grupo master ao invés do líder da categoria.
6. Fluxo interno da aplicação alterado para não interferir na alteração de Classe e Nome.

> **Caso necessite saber mais sobre regras de precificação ir para opção Solicitações / Alterações de Produto em _Alterações de Preços e Preços em lote_**

> Na **SIEVE** temos cadastrado o valor mínimo e máximo

### Cálculo de margem

**Descrição**

Ao aprovar o preço de um produto terá a possibilidade de alterar o valor, calcular margem e aplicar todas as regras que já ocorrem na solicitação de preços.

**Funcionalidades**

1. No modal de aprovação de produtos, agora é possível digitar um novo preço.
2. Adicionado caixa exibindo a margem do produto.
3. Adicionado botão para recalcular margem.

### Aprovação de Preço

5. Caso o preço esteja em branco impede a aprovação do produto.
6. Caso haja alteração de preço aplica as seguintes regras
    7. Se a margem for menor que 10%
        8. Se estiver cadastrado na categoria master permite aprovação
        9. Se não exibe mensagem de erro informando que a margem está abaixo de 10%
    10. Ao registrar a solicitação adiciona no campo de observação a informação: “_Preco alterado manualmente! De: {**PrecoAntigo**} Por: {**PrecoNovo**}_ ”
    11. O preço fictício é atualizado ao registrar a solicitação via API
12. Caso o preço não seja alterado segue o fluxo padrão.

### Precificação

**Descrição**

Quando houver uma solicitação para alteração de preço abaixo de 10% o sistema não enviará para o líder da categoria aprovar e sim para os usuários registrados na categoria master.

![](http://developers.connectparts.com.br/imagens/precosPendentesRegra01.png)

**Analista**

* O **analista** pode solicitar qualquer valor
    * Todas as solicitações irão para o líder do setor para aprovação.
    * Quando o líder aprovar, se a **margem for acima de 10%** segue para o ERP, caso contrário irá para o gestor.

**Líder**

* O **líder** pode solicitar qualquer valor
    * Todas as solicitações que for **maior que a margem de 10%**, serão aprovadas automaticamente.
    * Se solicitação **for menor que a margem de 10%**, o gestor terá que aprovar e seguirá para o ERP.
    
<!--Esta alteração foi feita no dia 25/09-->
<!--
* Precificação maior que 16% os analistas poderão solicitar, abaixo desta porcentagem o sistema não irá permitir a solicitação.

* Os **analistas** poderão solicitar qualquer valor.
    * Valores abaixo de 16% até 10%, terão que ter aprovação dos líderes.
    * Valores abaixo de 10%, terão que ter aprovação dos líderes e também dos gestores.

* Os **líderes** poderão solicitar qualquer valor.
    * Valores abaixo de 10%, terão que ter aprovação dos líderes e também dos gestores.
-->

> Gestores que estão na categoria master: Marçal Junior, Lucas Costa, Marcos Silva.

## Resultado

![](http://developers.connectparts.com.br/imagens/comercialSolicitacaoPrecoPendente02.png)

Temos as informações do produto, quem foi o solicitante de alteração de preço e a data da solicitação e a ação de Aprovar ou Reprovar.