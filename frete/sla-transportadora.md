# SLA Transportadora

## Funcionalidade

Verifica se o prazo de entrega do pedido foi respeitado conforme o SLA da transportadora.

### Processos

A ferramenta, faz a captação dos pedidos no Ábacos a cada 5 minutos. São captados os pedidos que entrarem no status “Despachado”. Checamos três eventos:

1. Data de entrada na transportadora / sistema: com base na transportadora e objeto de rastreio, consultamos através de API ou WS, quando o objeto foi digitado no sistema e atualizamos em nossa base. Esta data será usada para calcular o “Tempo de Entrega” real.
2. Data da primeira tentativa de entrega: Registraremos a data da primeira tentativa de entrega.
3. Data de entrega: Data base para cálculo do “prazo do tempo de entrega” real.

O aplicativo expõe uma lista com os seguintes filtros:

• Número do Pedido;

• Canal;

• Intervalo de Datas;

• Não entregues;

• Atrasados e Entregues no prazo;

O objetivo principal da ferramenta é gerar informações sobre o SLA das transportadoras, identificando atrasos e causas.

![](../.gitbook/assets/image%20%286%29.png)

