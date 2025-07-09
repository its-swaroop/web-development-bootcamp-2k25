# MODULE 8.0: DEPLOYMENT — Static, Server, and Database Hosting


#### 1. Hosting Static Websites with GitHub Pages

GitHub Pages is ideal for **static frontend projects** (HTML, CSS, JS only).

**Steps:**

1. Push your static project to a GitHub repo
2. Go to **Settings > Pages**
3. Choose source: `main` branch + `/root` or `/docs` folder
4. Save and access your live site at:

   ```
   https://yourusername.github.io/reponame/
   ```

**Best Practice:**

* Your landing page should be named `index.html`

---

#### 2. Deploying Server-Based Applications with Heroku

Heroku is a **PaaS** (Platform-as-a-Service) for Node.js and backend apps.

**Steps:**

1. **Login to Heroku:**

```bash
heroku login
```

2. **Create Heroku App:**

```bash
heroku create your-app-name
```

3. **Push Code:**

```bash
git push heroku main
```

4. **Define Start Script in `package.json`:**

```json
"scripts": {
  "start": "node app.js"
}
```

5. **Set Environment Variables:**

```bash
heroku config:set KEY=VALUE
```

6. **View App:**

```bash
heroku open
```

---

#### 3. Deploying Databases with MongoDB Atlas

**MongoDB Atlas** hosts your NoSQL MongoDB database in the cloud.

**Steps:**

1. Go to [https://cloud.mongodb.com](https://cloud.mongodb.com)
2. Create a **free cluster**
3. Add a **database user** and **IP whitelist** (`0.0.0.0/0` for all)
4. Copy the **Connection URI** (with username, password, cluster info)
5. Use with Mongoose in Node:

```js
mongoose.connect("mongodb+srv://<user>:<pass>@cluster.mongodb.net/mydb");
```

---

### Summary

| Deployment Type        | Platform      | Key Command/Setup                           |
| ---------------------- | ------------- | ------------------------------------------- |
| Static Site (Frontend) | GitHub Pages  | Repo → Settings → Pages                     |
| Server App (Backend)   | Heroku        | `heroku create`, `git push heroku main`     |
| Database (NoSQL)       | MongoDB Atlas | Create cluster, get URI, connect via driver |

<footer>TO BE CONT....</footer>
