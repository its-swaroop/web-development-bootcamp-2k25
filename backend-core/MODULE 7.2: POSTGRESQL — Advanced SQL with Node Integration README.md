# MODULE 7.2: POSTGRESQL — Advanced SQL with Node Integration


#### 1. Installing PostgreSQL

**On Ubuntu (Linux):**

```bash
sudo apt update
sudo apt install postgresql postgresql-contrib
```

**Start PostgreSQL CLI:**

```bash
sudo -u postgres psql
```

**Create DB and User:**

```sql
CREATE DATABASE appdb;
CREATE USER devuser WITH PASSWORD 'password';
GRANT ALL PRIVILEGES ON DATABASE appdb TO devuser;
```

---

#### 2. PostgreSQL Queries (CRUD)

| Action | Example                                                                |
| ------ | ---------------------------------------------------------------------- |
| Create | `INSERT INTO users (name, email) VALUES ('Ruth', 'ruth@example.com');` |
| Read   | `SELECT * FROM users;`                                                 |
| Update | `UPDATE users SET name = 'Roy' WHERE id = 1;`                          |
| Delete | `DELETE FROM users WHERE id = 1;`                                      |

**Advanced:**

* Use `RETURNING` to get data back after insert/update:

```sql
INSERT INTO users (name) VALUES ('Ruth') RETURNING *;
```

---

#### 3. Postgres Best Practices

* Use **`SERIAL`** or **`BIGSERIAL`** for auto-incrementing IDs
* Use **`NOT NULL`** and **`UNIQUE`** constraints for validation
* Always **index foreign keys** for performance
* Use **`CHECK`** constraints for domain rules (e.g. age > 0)
* Use **`uuid`** for IDs in distributed systems if needed

---

#### 4. Relational Database Relationships in Postgres

##### One-to-One

```sql
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  name TEXT
);

CREATE TABLE profiles (
  id SERIAL PRIMARY KEY,
  user_id INTEGER UNIQUE REFERENCES users(id),
  bio TEXT
);
```

##### One-to-Many

```sql
CREATE TABLE posts (
  id SERIAL PRIMARY KEY,
  user_id INTEGER REFERENCES users(id),
  title TEXT
);
```

##### Many-to-Many (Join Table)

```sql
CREATE TABLE students (
  id SERIAL PRIMARY KEY,
  name TEXT
);

CREATE TABLE courses (
  id SERIAL PRIMARY KEY,
  title TEXT
);

CREATE TABLE enrollments (
  student_id INTEGER REFERENCES students(id),
  course_id INTEGER REFERENCES courses(id),
  PRIMARY KEY (student_id, course_id)
);
```

---

#### 5. Working with Postgres in Node using `pg` package

**Install:**

```bash
npm install pg
```

**Basic Connection:**

```js
const { Pool } = require('pg');

const pool = new Pool({
  user: 'devuser',
  host: 'localhost',
  database: 'appdb',
  password: 'password',
  port: 5432,
});
```

**Query Example:**

```js
pool.query('SELECT * FROM users', (err, res) => {
  if (err) throw err;
  console.log(res.rows);
});
```

**Async/Await Version:**

```js
async function getUsers() {
  const res = await pool.query('SELECT * FROM users');
  console.log(res.rows);
}
```

---

### Summary

| Topic                   | Key Focus                              |
| ----------------------- | -------------------------------------- |
| Install & CLI           | `psql`, `createdb`, `createuser`       |
| CRUD in Postgres        | `INSERT`, `SELECT`, `UPDATE`, `DELETE` |
| Relationships           | Foreign Keys, Join Tables              |
| Best Practices          | Constraints, indexing, `RETURNING`     |
| Node Integration (`pg`) | Pool config, async queries             |

<footer>TO BE CONT....</footer>
