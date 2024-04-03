# Projeto Moeda Estrangeira

Nossa empresa necessita de um microserviço que gere uma ordem de compra das moedas estrangeiras em REAL.

Antes de qualquer compra, precisamos ter registrado os dados do cliente: nome, cpf, data de nascimento, estado civil e sexo no sistema, e também ser possível consultar esses dados através do cpf.

Com cliente cadastrado no sistema, é possível registrar uma ordem de compra que consiste em: tipo da moeda, o valor da moeda estrangeira e o número da agência (4 dígitos) que ocorrerá a retirada.

Terá que ter integração com a API externa https://docs.awesomeapi.com.br/api-de-moedas para calcular a cotação da moeda.

### Regra de Negócio:
 
A API irá calcular o valor total com base na cotação da moeda multiplicada pelo valor desejado de compra. Ao final de uma requisição bem sucedida, deverá ser retornado o request body abaixo:

```
{
    "id_compra": 1,
    "id_cliente": 1,
    "cpf_cliente": "43488428095",
    "dataSolicitacao": "2021-08-27T16:11:23.866",
    "tipo_moeda": "EUR",
    "valor_moeda_estrangeira": 100.0,
    "valor_cotacao": 6.5857,
    "valor_total_operacao": 658.57,
    "numero_agencia_retirada": "7057"
}
```
