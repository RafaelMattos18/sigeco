# URA KING VOICE

---

# Funcionalidade

A King Voice executa uma rotina de ligação para o cliente que esta em zona de risco (*domiciliar em algumas cidades, em área rural, logradouros de difícil acesso ou de risco*), assim o cliente retira o objeto na agência do correio.

## Processo

O sistema pega o numero do pedido de 15 retroativos (ontem + 14 dias), verifica a transportadora se é correios.

Se status for  "*objeto aguardando retirada no endereço indicado", "aguardando retirada", "disponível em caixa postal", "destinatário ausente*" coloca pedido no banco de dados e fica disponivel na API da KingVoice

## Regras

* Somente correio entrega em caixa postal - retirada do produto
* Cliente coloca o CPF dele no nosso site e há uma rotina que a KingVoice bate em uma API nossa.

### Retornos

```
case 10:
	retorno = "PRONTO PARA FATURAR";
	break;
case 11:
	retorno = "FATURADO";
	break;
case 12:
	retorno = "CANCELADO";
	break;
case 8://AGUARDANDO ESTOQUE
case 9://ESTOQUE RESERVADO PARCIALMENTE
case 13:
	retorno = "AGUARDANDO SEPARACAO DE MERCADORIAS";
	break;
case 22:
case 17:
	retorno = "AGUARDANDO CONFIRMACAO DO PAGAMENTO";
	break;
//case 22:
//    retorno = "PEDIDO EM PROCESSAMENTO";
//break;
case 27:
	retorno = "DESPACHADO";
	break;
case 28:
	retorno = "ENTREGUE";
	break;
default:
	retorno = "STATUS NAO ENCONTRADO";
	break;
```

## Reenvio de rastreio

### EndPoints

* http://api.dakotaparts.com.br/KingVoice
* PedidoReenvioRastreio/Inserir
* PedidoReenvioRastreio/Listar
* PedidoLigacaoPendente

## API

* http://api.connectparts.com.br:8014/token

## Fluxo URA

**Link:** [Fluxo URA King Voice](http://developers.connectparts.com.br/imagens/Fluxograma URA.pdf)