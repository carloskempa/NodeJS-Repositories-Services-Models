<h3 align="center">
  Projeto NodeJS GoFinances
</h3>

## :rocket: Desafio

Criar uma aplicação para armazenar transações financeiras de entrada e saída, que deve permitir o cadastro e a listagem dessas transações.

### Rotas da aplicação

- **`POST /transactions`**: A rota deve receber `title`, `value` e `type` dentro do corpo da requisição, sendo `type` o tipo da transação, que deve ser `income` para entradas (depósitos) e `outcome` para saídas (retiradas). Ao cadastrar uma nova transação, ela deve ser armazenada dentro de um objeto com o seguinte formato :

```json
{
  "id": "uuid",
  "title": "Salário X",
  "value": 4000,
  "type": "income"
}
```

- **`GET /transactions`**: Essa rota deve retornar uma listagem com todas as transações, junto com o valor de soma de entradas, retiradas e total de crédito. Essa rota deve retornar um objeto com o formato a seguir:

```json
{
  "transactions": [
    {
      "id": "uuid",
      "title": "Salário X",
      "value": 4000,
      "type": "income"
    },
    
    {
      "id": "uuid",
      "title": "Fatura do Carta de Credito",
      "value": 300,
      "type": "outcome"
    },
    {
      "id": "uuid",
      "title": "Monitor 25 Polegadas",
      "value": 1200,
      "type": "outcome"
    }
  ],
  "balance": {
    "income": 4000,
    "outcome": 1500,
    "total": 2500
  }
}
```
