# Log Dropshipping

## Listagem de Pedidos - DropShipping

![](http://developers.connectparts.com.br/imagens/sigeco-integracoes-01.png)

## Funcionalidade

Nesta opção temos a listagem de pedidos que contém os componentes DropShipping.

* Campos: **Data Inicial**, **Data Final**, **Status** e **Pedido**. Sendo que o **Status** contém as opções Integrado, Enviado para fornecedor, Pedido de compra recebido, Faturado, Nota fiscal enviada, Nota fiscal de remessa recebida e Concluído.

## Resultado

![](http://developers.connectparts.com.br/imagens/sigeco-integracoes-02.png)

A pesquisa traz as informações **Código** do pedido, **Data de Criação, Status, Data de Atualização e Ação**.

Ao clicar na opção **Ação**, será apresentada a seguinte _**time line**_.

### Time Line

![](http://developers.connectparts.com.br/imagens/statusDropShipping.png)

**Time line** indicando todo o trajeto feito pelo pedido.

1. **Pedido integrado ao Ábacos**
   * Pedido foi inserido/integrado no ERP Ábacos.
2. **Fornecedor confirmou recebimento**
   * Pedido enviado para o fornecedor e confirmado.
3. **Fornecedor enviou NF de Compra**
   * Pedido de compra recebido, fornecedor enviou NF Compra para Connect.
4. **Pedido faturado pela ConnectParts**
5. **Connect enviou NF ao fornecedor**
6. **NF de remessa recebida**
   * Fornecedor encaminha NF para Connect que comunica ao cliente do rastreio, envia dados na nota para transportadora, inclui informações no sistema de CRM, caso não tenha pedido no sistema de CRM fica notificando até localizar pedido.
   * Para seguir para o próximo, será necessário que as 3 notificações estejam concluídas, a saber
7. **Rastreamento enviado ao cliente**
   * Dados enviados ao cliente, este status é alterado quando o sistema conseguir fazer 3 notificações supracitadas.
8. **Despachada pelo fornecedor**
   * Concluído, fornecedor informa a Connect o despacho da mercadoria

