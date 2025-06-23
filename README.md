# 💸 Transactions API – RESTful com Node.js, Fastify & TypeScript

API REST para controle de transações financeiras (crédito e débito), construída com **Fastify**, **TypeScript**, **Knex.js** e banco de dados **SQLite ou PostgreSQL**.

---

## 📦 Tecnologias

- **Node.js** `>=18`
- **TypeScript**
- **Fastify**
- **Knex** (com suporte a SQLite e PostgreSQL)
- **Zod** (validação de dados)
- **dotenv** (variáveis de ambiente)
- **Vitest + Supertest** (testes)
- **Tsup + TSX** (build e dev)
- **ESLint Rocketseat config** (qualidade de código)

---

## 🚀 Scripts

| Script       | Descrição                                |
|--------------|--------------------------------------------|
| `npm run dev` | Inicia o servidor em modo desenvolvimento |
| `npm run build` | Gera build com o `tsup`                |
| `npm run lint` | Aplica correções com ESLint             |
| `npm run test` | Roda os testes com `vitest`             |
| `npm run knex` | Executa comandos do CLI do Knex com suporte a TS |

---

## 📁 Estrutura do Projeto

```
src/
├── @types/
│   └── knex.d.ts
├── env/
│   └── index.ts
├── middlewares/
│   └── check-session-id-exists.ts
├── routes/
│   └── transactions.ts
├── server.ts
├── database.ts
├── app.ts
```

---

## 🌐 Rotas `/transactions`

| Método | Rota                     | Descrição                           |
|--------|--------------------------|--------------------------------------|
| POST   | `/transactions`          | Cria uma nova transação              |
| GET    | `/transactions`          | Lista todas as transações do usuário |
| GET    | `/transactions/:id`      | Detalha uma transação específica     |
| GET    | `/transactions/summary`  | Retorna o saldo total (crédito - débito) |

> 🔐 As rotas `GET` requerem o cookie `sessionId`.

---

## ⚙️ Variáveis de Ambiente

Crie um arquivo `.env`:

```
DATABASE_URL=./db.sqlite
PORT=3333
```

---

## 🧪 Testes

```bash
npm run test
```

- Testes escritos com **Vitest**
- Integração via **Supertest**

---

## 🔧 Inicialização manual (caso crie do zero)

```bash
npm init -y
npm install fastify zod knex sqlite3 dotenv @fastify/cookie
npm install -D typescript tsx tsup eslint @rocketseat/eslint-config vitest supertest @types/node @types/supertest
npx tsc --init
```

---

## 🧰 Build e Produção

```bash
# Gerar build
npm run build

# Saída em: ./build/
node build/server.js
```