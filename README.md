<div align="center"> 
  <img src="https://camo.githubusercontent.com/8c13dc2618dbd7f76d1d574350b98fdee1335ce5/68747470733a2f2f726f636b6574736561742d63646e2e73332d73612d656173742d312e616d617a6f6e6177732e636f6d2f626f6f7463616d702d6865616465722e706e67" />
 </div>
 
<h3 align="center">
  Challenge 02: First Node.js project with database
</h3>


<p align="center">
   <img src="https://github.com/bprofiro/assets/blob/master/node-with-database.png" />
</p>

<div>
  <h2> :rocket: About the challenge: </h2>
  
  - **`POST /transactions`**: The route must receive title, value, type, and category within the body of the request, the type being the type of the transaction, which should be income for incoming (deposits) and outcome for outgoing (withdrawn). When registering a new transaction, it must be stored within your database, having the fields id, title, value, type, category_id, created_at, updated_at.

```json
{
  "id": "uuid",
  "title": "Salário",
  "value": 3000,
  "type": "income",
  "category": "Alimentação"
}
```

- **`GET /transactions`**: This route will return a listing with all the transactions you have registered so far, along with the sum of the entries, withdrawals and total credit. This route must return an object with the following format:

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

- **`DELETE /transactions/:id`**: The route will delete a transaction with the `id` present in the route parameters;

* **`POST /transactions/import`**: The route will allow the import of a file in `.csv` format containing the same information needed to create a transaction` id`, `title`,` value`, `type`,` category_id`, `created_at`,` updated_at `, where each line of the CSV file must be a new record for the database, and finally return all the` transactions` that have been imported into your database. The csv file, must follow the following [model] (./ assets / file.csv)


</div>

<div>
  <h2> :computer: Techs: </h2>
   <p> This project was built in just one language: JavaScript, using the following technologies:

   -   [Node.js](https://nodejs.org/en/)
  </p>
</div>
