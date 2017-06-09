# Preços Pendentes

---

![](/assets/comercialSolicitacaoPrecoPendente01.png)

## Funcionalidade

Nesta tela temos um relatório de produtos que sofreram alteração de preço pelo analistas/assistentes ou tivemos sugestão de preço enviada pela [SIEVE](https://www.sieve.com.br/sobre). O líder toma a decisão de reprovar ou aprovar esta solicitação.

## Resultado

![](/assets/comercialSolicitacaoPrecoPendente02.png)

Temos as informações do produto, quem foi o solicitante de alteração de preço e a data da solicitação e a ação de Aprovar ou Reprovar.

### Regras

Na SIEVE temos cadastrado o valor mínimo e máximo


#### Precificação abaixo de 10%

Temos a seguinte regra no sistema:

* O analista/assistente solicita alteração de  preço abaixo de 16%(margem), é apresentada um alerta proibindo tal ação. **Porém o líder consegue precificar abaixo de 16%**.

#### Descrição

Quando houver uma solicitação para alteração de preço abaixo de 10% o sistema não enviará para o líder da categoria aprovar e sim para os usuários registrados na categoria master.

![](/assets/precosPendentesRegra01.png)

##### Funcionalidades 

1. O fluxo para o usuário final continua o mesmo, apenas o backend da aplicação mudou.

**Regras na Solicitação de Preço**

1. Ao receber a solicitação de preço a API de precificação e cadastro aplica as regras
    2. Recalcula a margem do produto
        3. Caso seja abaixo de 10% alteração o grupo proprietário para 9000 (Grupo master)
        4. Adiciona no campo de observação a mensagem “Margem menor que 10% !!!”
5. Sistema de precificação da Sieve também foi adaptado para quando gerar um solicitação com preço abaixo de 10% ir para o grupo master ao invés do líder da categoria.
6. Fluxo interno da aplicação alterado para não interferir na alteração de Classe e Nome.









