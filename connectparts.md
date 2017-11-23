# INTEGRAÇÃO MANUAL PEDIDO DTS

---

## 

1. **Gerar Token** 
  
  Acesse http://api.dakotaparts.com.br, vá para o controller oauth/token, insira seu usuario e senha e a resposta da api irá te gerar o seu access_token

2. **Inserir pedido manualmente** 

  Acesse http://api.dakotaparts.com.br/dropshipping, vá para o controller pedido/inserir e preencha os seguintes dados:


```
pedidoVm:
{
  "CodigoExterno": "CODIGO_DO_PEDIDO",
  "PedidoConnect": false,
  "DataConfirmacao": [IRÁ SER GERADO AUTOMATICAMENTE],
  "PedidoStatusCodigo": 1,
  "PedidoFornecedores": [
    {
      "PedidoCodigo": "CODIGO_DO_PEDIDO",
      "PedidoFornecedorCodigo": "CODIGO_DO_PEDIDO-DTS",
      "FornecedorCodigo": "a8cd92fb-8d71-40f2-8790-9a02d01c0b19",
      "PedidoStatusCodigo": 1,
      "DataConfirmacao": [IRÁ SER GERADO AUTOMATICAMENTE],
      "PedidoFornecedorProdutos": [
        {
          "PedidoFornecedorCodigo": "CODIGO_DO_PEDIDO-DTS",
          "ProdutoCodigo": "CODIGO_DO_PRODUTO",
          "Quantidade": QTD_PRODUTO,
          "PrecoUnitarioVenda": PRECO_DE_VENDA (EX: 27790 ~ EQUIVALE À R$277,90),
          "PrecoUnitarioCusto": PRECO_DE_CUSTO (VIDE EXEMPLO ACIMA)
        }
      ]
    }
  ]
}

Authorization:
bearer [TOKEN GERADO NO PASSO 1]

Obs.: Sempre conferir pedido com sistema 00K: https://admin.00k.com.br,

Se tudo estiver ok: '**Try it out!**'

```


