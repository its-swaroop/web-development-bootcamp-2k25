# MODULE 7.1: SQL DATABASES — SCHEMAS, CRUD, JOINS & QUERIES


#### 1. Working with Database Schemas

**Schema** = Structure of the database
Includes:

* Tables
* Columns & Data types
* Constraints (primary key, foreign key, not null, etc.)
* Indexes

**Example (PostgreSQL):**

```sql
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  name TEXT NOT NULL,
  email TEXT UNIQUE
);

CREATE TABLE posts (
  id SERIAL PRIMARY KEY,
  title TEXT,
  user_id INTEGER REFERENCES users(id)
);
```

---

#### 2. CRUD Operations

| Action     | SQL Command Example                                                    |
| ---------- | ---------------------------------------------------------------------- |
| C — Create | `INSERT INTO users (name, email) VALUES ('Ruth', 'ruth@example.com');` |
| R — Read   | `SELECT * FROM users;`                                                 |
| U — Update | `UPDATE users SET name = 'Roy' WHERE id = 1;`                          |
| D — Delete | `DELETE FROM users WHERE id = 1;`                                      |

**Select specific fields:**

```sql
SELECT name, email FROM users;
```

**Where clause:**

```sql
SELECT * FROM users WHERE name = 'Ruth';
```

---

#### 3. Database Joins

Used to **combine data from multiple tables** based on related keys.

| Join Type  | Usage                                                 |
| ---------- | ----------------------------------------------------- |
| INNER JOIN | Returns rows with matching keys in both tables        |
| LEFT JOIN  | All rows from left table + matched ones from right    |
| RIGHT JOIN | All from right + matched from left (rare in practice) |
| FULL JOIN  | All rows from both, matched where possible            |

**Example:**

```sql
SELECT users.name, posts.title
FROM users
JOIN posts ON users.id = posts.user_id;
```

---

#### 4. Querying SQL Databases

**Filter results:**

```sql
SELECT * FROM posts WHERE title LIKE '%Node%';
```

**Sort results:**

```sql
SELECT * FROM users ORDER BY name ASC;
```

**Limit and Offset:**

```sql
SELECT * FROM posts LIMIT 10 OFFSET 20;
```

**Aggregate Functions:**

```sql
SELECT COUNT(*) FROM users;
SELECT AVG(age) FROM users;
```

**Grouping:**

```sql
SELECT user_id, COUNT(*) 
FROM posts
GROUP BY user_id;
```

---

### Summary

| Feature   | SQL Example                                 |
| --------- | ------------------------------------------- |
| Schema    | `CREATE TABLE` with types & constraints     |
| Insert    | `INSERT INTO table (cols) VALUES (...)`     |
| Read      | `SELECT` with `WHERE`, `ORDER BY`, `LIMIT`  |
| Update    | `UPDATE table SET col = val WHERE ...`      |
| Delete    | `DELETE FROM table WHERE ...`               |
| Join      | `SELECT ... FROM A JOIN B ON A.id = B.a_id` |
| Aggregate | `COUNT`, `AVG`, `GROUP BY`                  |

<footer>TO BE CONT...</footer>
