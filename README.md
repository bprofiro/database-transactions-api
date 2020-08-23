<div align="center"> 
  <img src="https://camo.githubusercontent.com/8c13dc2618dbd7f76d1d574350b98fdee1335ce5/68747470733a2f2f726f636b6574736561742d63646e2e73332d73612d656173742d312e616d617a6f6e6177732e636f6d2f626f6f7463616d702d6865616465722e706e67" />
 </div>
 
<h3 align="center">
  API de Transações Bancárias com Node.JS com Banco de Dados
</h3>


<p align="center">
   <img src="https://github.com/bprofiro/assets/blob/master/node-with-database.png" />
</p>

<div>
  <h2> :rocket: Rotas da API: </h2>
  
  - **`POST /transactions`**: A rota deve receber `title`, `value`, `type` e `category` no corpo da solicitação, sendo o `type` o tipo de transação, que deve ser a `income` de entrada (depósitos) e o `outcome` de saída (retirada). Ao registrar uma nova transação, ela deve ser armazenada em seu banco de dados, possuindo os campos `id`, `title`, `valor`, `value`, `category_id`, `created_at`, `updated_at`.

```json
{
  "id": "uuid",
  "title": "Salário",
  "value": 3000,
  "type": "income",
  "category": "Alimentação"
}
```

- **`GET /transactions`**: Essa rota retornará uma listagem com todas as transações que você registrou até o momento, juntamente com a soma das entradas, saques e crédito total. Essa rota deve retornar um objeto com o seguinte formato:

```json
{
  "transactions": [
    {
      "id": "uuid",
      "title": "Salário",
      "value": 4000,
      "type": "income",
      "category": {
        "id": "uuid",
        "title": "Salary"
      }
    },
    {
      "id": "uuid",
      "title": "Freela",
      "value": 2000,
      "type": "income",
      "category": {
        "id": "uuid",
        "title": "Others"
      }
    },
    {
      "id": "uuid",
      "title": "Pagamento da fatura",
      "value": 4000,
      "type": "outcome",
      "category": {
        "id": "uuid",
        "title": "Others"
      }
    },
    {
      "id": "uuid",
      "title": "Cadeira Gamer",
      "value": 1200,
      "type": "outcome",
      "category": {
        "id": "uuid",
        "title": "Recreation"
      }
    }
  ],
  "balance": {
    "income": 6000,
    "outcome": 5200,
    "total": 800
  }
}
```

- **`DELETE /transactions/:id`**: A rota excluirá uma transação com o `id` presente nos parâmetros da rota;

* **`POST /transactions/import`**: A rota permitirá a importação de um arquivo no formato `.csv` contendo as mesmas informações necessárias para criar uma transação` id`, `title`,` value`, `type`,` category_id`, `created_at`,` created_at`, `updated_at `, onde cada linha do arquivo CSV deve ser um novo registro para o banco de dados e, finalmente, retornar todas as` transações` que foram importadas para o seu banco de dados. O arquivo csv, deve seguir o seguinte [modelo] (./ assets / file.csv)


</div>

<div>
  <h2> :computer: Tecnologias: </h2>
  <p> Esse projeto foi construído em Node.js e o seu banco de dados é o Postgres, mas pode ser utilizado para outros bancos. Ao clonar o projeto para usar, altere os campos necessários no arquivo `ormconfig.json` com o banco de dados que você deseja e os dados de acesso que o correspondem.</p>
</div>
