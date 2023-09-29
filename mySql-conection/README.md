# Utilizar de conexão de banco de dados

## Sobre

Ola desenvolvedor,aqui estara o guia para usar conexão ao banco mysql/mariaDB.
Use esta classe em conjunto com a [estrutura base api next js](./../README.md)

### dependencias necessarias

- npm install dotenv
- npm install mysql2

### Inicio da integração

No arquivo [/mySql-conection/arquivos/conections.js](/mySql-conection//arquivos/conections.js) esta a class de conexão para banco de dados

#### As variaveis de ambientes

As variaveis de ambientes se referem as dados que são sigilosos para seu servidor no caso os

```bash
    host: process.env.DB_HOST,
    user: process.env.DB_USER,
    password: process.env.DB_PASSWORD,
    port: process.env.DB_PORT,
    database: process.env.DB_DATABASE,
```

#### Como executar as querys sql

Pronto agora com o arquivo **.env** iniciado com os dados.
Declare a instancia da classe no local para se ter a operação de execução de query sql.

```javascript
const DatabaseConnection = require("./DatabaseConnection"); // Ajuste o caminho conforme necessário
```

No caso declaramos e atribuimos a DatabaseConnection a **db** .

````javascript
async function main() {
  const db = new DatabaseConnection();
}

main();```
````

Conectando ao banco de dados

```javascript
try {
  await db.connect();
  console.log("Connected to the database");
} catch (error) {
  console.error("Error connecting to the database:", error);
}
```

Executando a query sql

```javascript
try {
  await db.connect();
  console.log("Connected to the database");

  const sql = "SELECT * FROM sua_tabela"; // query SQL atribuida a variavel
  const results = await db.query(sql); // query SQL sendo executada

  console.log("Query results:", results); // em caso de sucesso ira print a mensagem results
} catch (error) {
  console.error("Error:", error); // caso falhe irar printar o erro
} finally {
  // Certifique-se de fechar a conexão quando terminar
  await db.close(); // por fim ele encerra a conexão
}
```
