# Variacoes

![](http://developers.connectparts.com.br/imagens/inseriVariacaoMercadoLivre01.png)

## Funcionalidade

Criar variações nos anúncios do **Mercado Livre**.

## Resultado

![](http://developers.connectparts.com.br/imagens/inseriVariacaoMercadoLivre02.png)

## Processo

### Tipo de Variação Combinada

* São variações que o ML permite, podendo ser uma ou múltiplas variações tendo no máximo 3 tipos de tags diferentes e podemos enviar através do nosso sistema \(arquivo excel\) até 3 descritores por linha, podendo inserir mais descritores nas linhas seguintes.
* Ao clicar em ** **_**Realize o download do arquivo modelo clicando aqui. **_** **, será gerado um arquivo.xls com as colunas **Mlb**, **CodigoExterno**, **Tag1**, **Descritor1**, **Tag2**, **Descritor2**, **Tag3** e **Descritor3**.
* Para fazer o download do modelo de layout do **Combinada** clique no botão **Exportar Atributos**.
  * Ao clicar em exportar atributos, abrirá uma tela onde você deverá digitar o MLB e então será exportado os atributos do anúncio.
  * Somente os atributos exportados, são permitidos nas variações combinadas.
  * O MLB pesquisado terá que ter a letras MLB + números, sem hífen \(-\)
    * Exemplo: MLB780641225 \(_maneira correta_\)
  * Será feito automaticamente um **download** de um arquivo **.xls** contendo a seguinte estrutura:

    ![](http://developers.connectparts.com.br/imagens//modelo01.jpg)

  * A **TagValor** corresponde as **Tag1, 2 e 3** e o **DescritorValor** corresponde ao **Descritor1, 2 e 3**, como o exemplo abaixo:

    ![](http://developers.connectparts.com.br/imagens//modelo02.jpg)

### Tipo de Variação Customizada

* Poderá ser enviada uma única variação: Deverão escolher somente uma TAG, podendo ter vários descritores.
* Ao clicar em ** **_**Realize o download do arquivo modelo clicando aqui. **_** **, será gerado um arquivo.xls com as colunas **Mlb**, **CodigoExterno**, **Tag1** e **Descritor1**
* Para fazer o download do modelo de layout do **Customizada** para clicar no link: **Realize o download do arquivo modelo clicando **_**aqui**_**. **

#### Tags e Descritores

* O que são descritores?  
  * São os descritores da tag: amarelo, 56, verde
* O que é tag?
  * Cor, tamanho, cor secundária
* Exemplo:

  ![](http://developers.connectparts.com.br/imagens//VariacaoML01.png)

### Observações

* Código externo = DK.
* Ao exportar atributos MLB
  * Na coluna **Mlb** no arquivo **.xls**, esta informação terá que ter a letras MLB + números, sem hífen \(-\)
    * Exemplo: MLB780641225 \(_maneira correta_\)
* Esta rotina é executada a cada 1 hora.
* As **TAG** e **DESCRITOR** suportam somente 60 caracteres.

## Regras

### Impedimentos

* Não é permitido preços diferentes nas variações
* Sempre será utilizado o saldo real do Ábacos para subir as variações
* Verifica se o produto está ativo no Mercado Livre
  * No máximo três variações poderão ir para Mercado Livre.
  * Somente pode subir variações combinadas se o ML permitir.

### Coluna \(Tag1\)

Quando tivermos que adicionar o valor da coluna **Tag1** com o valor **MANUFACTURER\_HELMET\_SIZE** deverá ser adicionado **somente números** na coluna **Descritor1**, como é demonstrado na figura abaixo.

![](http://developers.connectparts.com.br/imagens/NovoModeloVariacao01.jpg)

Quando utilizamos a opção **Exportar Atributos** virá informações nas colunas que deverão ser iguais ao arquivo que iremos fazer o upload, como está na coluna **TagValor** - figura abaixo.

![](http://developers.connectparts.com.br/imagens/NovoModeloVariacao02.jpg)

### Motivos de geração de Erro

* Anuncio pausado
* Estoque
  * Utilizando os estoques **Real** e **Virtual**. 
  * Instabilidade no ML
    * Quando houver a remoção de um anúncio, deverá ser aberto um chamado para o departamento de **Inovação e Desenvolvimento**.    
* Toda variação da categoria deve ter entre 1 e 10 imagens.
  * Resposta desta mensagem, que virá no arquivo xls: 

    ```text
    [  {    "code": "item.pictures.variation.quantity",    "message": "Every variation of category MLB63553 must have between 1 and 10 pictures."  }]
    ```

