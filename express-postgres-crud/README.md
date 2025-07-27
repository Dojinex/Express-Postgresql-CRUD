
# Express.js + PostgreSQL CRUD API

This is a simple RESTful API built with **Express.js** and **PostgreSQL** that performs **CRUD operations** (Create, Read, Update, Delete) on a `users` table.

## 📌 Features

- Create a new user
- Retrieve all users
- Retrieve a specific user by ID
- Update a user's information
- Delete a user
- PostgreSQL database connection
- Basic error handling

---

## 🏗️ Technologies Used

- Node.js
- Express.js
- PostgreSQL
- pg (PostgreSQL client for Node.js)

---

## 📁 Project Structure

```
express-postgres-crud/
├── db.js              # PostgreSQL connection config
├── index.js           # Entry point of the application
├── routes/
│   └── users.js       # User CRUD routes
├── .env               # Environment variables
├── package.json
└── README.md
```

---

## ⚙️ Setup Instructions

### 1. Install Prerequisites

- [Node.js](https://nodejs.org/)
- [PostgreSQL](https://www.postgresql.org/)

---

### 2. Clone the Project

```bash
git clone https://github.com/your-username/express-postgres-crud.git
cd express-postgres-crud
```

---

### 3. Install Dependencies

```bash
npm install
```

---

### 4. Setup PostgreSQL Database

1. Start PostgreSQL service.
2. Open your PostgreSQL client or terminal and run:

```sql
CREATE DATABASE userdb;

\c userdb

CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100),
    age INTEGER
);
```

3. Create a `.env` file in the root directory and add:

```
PGUSER=your_pg_user
PGHOST=localhost
PGDATABASE=userdb
PGPASSWORD=your_pg_password
PGPORT=5432
```

4. Update `db.js` to use the `dotenv` package:

```js
require('dotenv').config();
const { Pool } = require('pg');

const pool = new Pool();

module.exports = pool;
```

---

### 5. Run the Application

```bash
node index.js
```

The server will run at `http://localhost:3000`.

---

## 📮 API Endpoints

| Method | Endpoint        | Description         |
|--------|------------------|---------------------|
| GET    | `/users`         | Get all users       |
| GET    | `/users/:id`     | Get user by ID      |
| POST   | `/users`         | Create a new user   |
| PUT    | `/users/:id`     | Update a user       |
| DELETE | `/users/:id`     | Delete a user       |

### 🧪 Example Request Body (JSON)

```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "age": 25
}
```

---

## ✅ Testing

You can test the API using:

- [Postman](https://www.postman.com/)
- [Thunder Client](https://www.thunderclient.com/) (VS Code extension)
- curl or any HTTP client

---

## 🚀 Deployment (Optional)

To deploy this API:

- Choose a platform like [Render](https://render.com/), [Railway](https://railway.app/), or [Heroku](https://www.heroku.com/).
- Add your environment variables in the deployment dashboard.
- Connect your GitHub repo and deploy.

---

## 📄 License

This project is open-source and available for educational and personal use.

---

## 🙋‍♂️ Author

**Bitrus Dauda Gana**  
Email: bitrusdauda9118@example.com  
GitHub: [your-username](https://github.com/Dojinex)

---
