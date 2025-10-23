# 🛍️ API de Gerenciamento de Produtos

Esta API permite realizar o gerenciamento de produtos através de operações CRUD (Criar, Listar, Atualizar e Excluir). É ideal para aplicações que precisam de controle básico de inventário ou catálogo.

---

## 🎯 Objetivo

Prover uma interface RESTful simples para gerenciamento de produtos, com validação de dados de entrada e pronta para testes com ferramentas como Insomnia ou Postman.

---

## 🚀 Funcionalidades

- ✅ Criar produtos (`POST /produtos`)
- 📃 Listar todos os produtos (`GET /produtos`)
- 📝 Atualizar um produto (`PUT /produtos/:id`)
- ❌ Excluir um produto (`DELETE /produtos/:id`)
- ⚠️ Validação de dados nos endpoints de criação e edição

---

## 🛠️ Tecnologias Utilizadas

- [Node.js](https://nodejs.org/)
- [Express](https://expressjs.com/)
- [express-validator](https://express-validator.github.io/docs/)

---

## 💾 Instalação e Execução

### 1. Clone o projeto

```bash
git clone https://github.com/KauSR1/api-produtos.git
cd api-produtos
```

### 2. Instale as dependências

```bash
npm install
```

### 3. Inicie o servidor

```bash
node index.js
```

> A API será executada por padrão em: `http://localhost:3000`

---

## 📬 Endpoints e Exemplos

### 🔸 Criar Produto

**POST /produtos**

#### Corpo da requisição (JSON)

```json
{
  "nome": "Mouse Gamer",
  "preco": 150.00
}
```

#### Resposta de sucesso (201)

```json
{
  "id": 1,
  "nome": "Mouse Gamer",
  "preco": 150.00
}
```

#### Erros de validação (400)

```json
{
  "erros": [
    {
      "msg": "O nome é obrigatório",
      "param": "nome",
      "location": "body"
    }
  ]
}
```

---

### 🔹 Listar Produtos

**GET /produtos**

#### Resposta (200)

```json
[
  {
    "id": 1,
    "nome": "Mouse Gamer",
    "preco": 150.00
  },
  {
    "id": 2,
    "nome": "Teclado Mecânico",
    "preco": 250.00
  }
]
```

---

### 🔸 Atualizar Produto

**PUT /produtos/:id**

#### Exemplo: `PUT /produtos/1`

```json
{
  "nome": "Mouse Sem Fio",
  "preco": 120.00
}
```

#### Resposta (200)

```json
{
  "id": 1,
  "nome": "Mouse Sem Fio",
  "preco": 120.00
}
```

#### Produto não encontrado (404)

```json
{
  "erro": "Produto não encontrado"
}
```

---

### 🔹 Excluir Produto

**DELETE /produtos/:id**

#### Exemplo: `DELETE /produtos/1`

#### Resposta (204 No Content)

Sem conteúdo na resposta.

#### Produto não encontrado (404)

```json
{
  "erro": "Produto não encontrado"
}
```

---

## 🧪 Testando com Insomnia

Você pode importar os seguintes endpoints no Insomnia:

1. Crie uma nova coleção chamada `API Produtos`
2. Crie requisições com os métodos e URLs mencionados acima
3. Envie os dados JSON no corpo da requisição (no caso de POST e PUT)

---

## 📌 Observações

- Os dados são armazenados em memória (array), ou seja, são perdidos ao reiniciar o servidor.
- Ideal para fins de estudo, teste de ferramentas como Insomnia/Postman, e prototipagem.
- Pode ser facilmente adaptado para uso com bancos de dados como MongoDB, PostgreSQL ou SQLite.

---
