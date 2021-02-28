<p align="center">
   <img src="https://raw.githubusercontent.com/tavareshenrique/rocketpay-nlw/main/assets/logo.png" alt="Rocketpay" width="280"/>
</p>

<p align="center">
   <a href="https://www.linkedin.com/in/tavareshenrique/">
      <img alt="Henrique Tavares" src="https://img.shields.io/badge/-Henrique Tavares-4e5acf?style=flat&logo=Linkedin&logoColor=white" />
   </a>
 <img alt="Repository size" src="https://img.shields.io/github/repo-size/tavareshenrique/rocketpay-nlw?color=4e5acf">

  <a aria-label="Last Commit" href="https://github.com/tavareshenrique/rocketpay-nlw/commits/master">
    <img alt="Last commit on GitHub" src="https://img.shields.io/github/last-commit/tavareshenrique/rocketpay-nlw?color=4e5acf">
  </a>
  <a href="https://github.com/tavareshenrique/rocketpay-nlw/commits/master">
    <img alt="GitHub last commit" src="https://img.shields.io/github/last-commit/tavareshenrique/rocketpay-nlw?color=4e5acf">
  </a>
  <img alt="License" src="https://img.shields.io/badge/license-MIT-4e5acf">
</p>

> <b>Rocketpay</b> é uma API criada utilizando Elixir e Phoenix durante a NLW#4 da [Rocketseat](https://github.com/Rocketseat). Esse projeto permite a transação de valores entre 2 usuários.

<div align="center">
  <sub>O <strong>Rocketpay</strong> foi desenvolvido com ❤︎ pelo
    <a href="https://github.com/tavareshenrique">Henrique Tavares</a>
  </sub>
</div>

# :pushpin: Conteúdo

- [API](#floppy_disk-api)
  - [Accounts](#accounts)
    - [Deposit](#deposit)
    - [Withdraw](#withdraw)
    - [Transaction](#transaction)
  - [User](#user)
    - [Create User](#create-user)
- [Tecnologias](#computer-tecnologias)
- [Executando](#construction_worker-executando)
- [Autores](#computer-autores)
- [Licença](#closed_book-licença)

# :floppy_disk: API

# Accounts

## Deposit

Esse End-Point permite o deposito de um determinado valor na conta do usuário.

- **URL**

  `/accounts/:userId/deposit`

- **Method:**

  `POST`

- **URL Params**

  - **Required:**

    `:userId` **-> ID do usuário que será feito o deposito.**
    `Basic Auth` **-> Informe o nome de usuário "henrique" e senha "123456" como autenticação básica**

- **JSON Example:**

  ```json
  {
    "value": "100.50"
  }
  ```

- **Success Response:**

  - **Code:** 200 <br />
    **Content:**

    ```json
    {
      "account": {
        "balance": "100.50",
        "id": "a44e81ee-7852-49d0-85b1-e3fa5775e3a7"
      },
      "message": "Ballance changed successfully"
    }
    ```

---

## Withdraw

Esse End-Point permite o saque de um determinado valor na conta do usuário.

- **URL**

  `/accounts/:userId/withdraw`

- **Method:**

  `POST`

- **URL Params**

  - **Required:**

    `:userId` **-> ID do usuário que será feito o deposito.**
    `Basic Auth` **-> Informe o nome de usuário "henrique" e senha "123456" como autenticação básica**

- **JSON Example:**

  ```json
  {
    "value": "50.50"
  }
  ```

- **Success Response:**

  - **Code:** 200 <br />
    **Content:**

    ```json
    {
      "account": {
        "balance": "50",
        "id": "a44e81ee-7852-49d0-85b1-e3fa5775e3a7"
      },
      "message": "Ballance changed successfully"
    }
    ```

---

## Transaction

Esse End-Point permite a transferência entre dois usuários.

- **URL**

  `/accounts/transaction`

- **Method:**

  `POST`

- **URL Params**

  - **Required:**

    `Basic Auth` **-> Informe o nome de usuário "henrique" e senha "123456" como autenticação básica**

- **JSON Example:**

  ```json
  {
    "value": "39.60",
    "from": "a44e81ee-7852-49d0-85b1-e3fa5775e3a7",
    "to": "98981aca-7c3c-4f1d-8520-1cbf0445dd11"
  }
  ```

- **Success Response:**

  - **Code:** 200 <br />
    **Content:**

    ```json
    {
      "message": "Transaction done successfully",
      "transaction": {
        "from_account": {
          "balance": "120.80",
          "id": "a44e81ee-7852-49d0-85b1-e3fa5775e3a7"
        },
        "to_account": {
          "balance": "368.80",
          "id": "98981aca-7c3c-4f1d-8520-1cbf0445dd11"
        }
      }
    }
    ```

---

# User

## Create User

Esse End-Point permit a criação de um usuário

- **URL**

  `/accounts/transaction`

- **Method:**

  `POST`

- **JSON Example:**

  ```json
  {
    "name": "Henrique",
    "nickname": "henrique",
    "email": "henrique@gmail.com",
    "age": 24,
    "password": "123456"
  }
  ```

- **Success Response:**

  - **Code:** 200 <br />
    **Content:**

    ```json
    {
      "message": "User created",
      "user": {
        "account": {
          "balance": "0.00",
          "id": "a44e81ee-7852-49d0-85b1-e3fa5775e3a7"
        },
        "id": "d88ffdf0-0cf7-4a32-ac18-7ac00b8eaaaf",
        "name": "Henrique",
        "nickname": "henrique"
      }
    }
    ```

---

# :computer: Tecnologias

Este projeto foi feito utilizando as seguintes tecnologias:

- [Elixir](https://github.com/elixir-lang/elixir)
- [Phoenix](https://github.com/phoenixframework/phoenix)
- [Ecto](https://github.com/elixir-ecto/ecto)
- [Postgres](https://www.postgresql.org/)
- [Credo](https://github.com/rrrene/credo)
- [pbkdf2_elixir](https://github.com/riverrun/pbkdf2_elixir)
- [decimal](https://github.com/ericmj/decimal)
- [excoveralls](https://github.com/parroty/excoveralls)

# :construction_worker: Executando

**Passo 1:**

```bash
# Clone o Repositório
$ git@github.com:tavareshenrique/rocketpay-nlw.git
```

**Passo 2:**

```bash
# É necessário que você tenha o banco Postgres rodando em sua máquina, seja Docker ou não.
```

**Passo 3:**

```bash
# Crie dois bancos com os seguintes nomes:

rocketpay_dev
# e
rocketpay_test
```

**Passo 4:**

```bash
# Configure seu usuário, senha etc. do banco nos arquivos:

config > dev.exs
# e
config > test.exs
```

**Passo 5:**

```bash
# Rode esse comando para ele criar/registrar o banco de dados
$ mix ecto.create
```

**Passo 5:**

```bash
# Rodando as Migrations
$ mix ecto.migrate
```

**Passo 5:**

```bash
# Pronto! Agora é só executar o Server;
$ mix phx.server
```

Acesse <http://localhost:3000> para ver o resultado.

# :computer: Autores

<table>
  <tr>
    <td align="center">
      <a href="http://github.com/tavareshenrique/">
        <img src="https://avatars1.githubusercontent.com/u/27022914?v=4" width="100px;" alt="Henrique Tavares"/>
        <br />
        <sub>
          <b>Henrique Tavares</b>
        </sub>
       </a>
       <br />
       <a href="https://www.linkedin.com/in/tavareshenrique/" title="Linkedin">@tavareshenrique</a>
       <br />
       <a href="https://github.com/tavareshenrique/fastfeet-api/commits?author=tavareshenrique" title="Code">💻</a>
    </td>
    <td align="center">
      <a href="http://github.com/tavareshenrique/">
        <img src="https://avatars0.githubusercontent.com/u/28929274?s=200&v=4" width="100px;" alt="Henrique Tavares"/>
        <br />
        <sub>
          <b>Rocketseat</b>
        </sub>
       </a>
       <br />
       <a href="https://github.com/Rocketseat" title="Linkedin">@Rocketseat</a>
       <br />
       <a href="https://github.com/tavareshenrique/fastfeet-api/commits?author=tavareshenrique" title="Creators">🚀</a>
    </td>
  </tr>
</table>

# :closed_book: Licença

Este projeto está sob a licença [MIT](./LICENSE).
