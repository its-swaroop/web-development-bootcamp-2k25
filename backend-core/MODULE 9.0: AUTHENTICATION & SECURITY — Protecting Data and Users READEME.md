# MODULE 9.0: AUTHENTICATION & SECURITY — Protecting Data and Users


#### 1. Why Authentication & Security Matter

* To **verify user identity**
* To **protect user data** (e.g. passwords, sessions)
* To **prevent attacks** (e.g. brute force, token theft, cookie hijacking)
* To **enable login + authorization** workflows

**Security Golden Rule:**

> Never store sensitive data (like passwords) in plaintext.

---

#### 2. Hashing and Salting Passwords with `bcrypt`

* **Hashing**: Converts data to fixed-length string (irreversible)
* **Salting**: Adds randomness before hashing to prevent lookup attacks

**Install & Use:**

```bash
npm install bcrypt
```

**Hash Password:**

```js
const bcrypt = require('bcrypt');
const hash = await bcrypt.hash(password, 12);
```

**Verify Password:**

```js
const match = await bcrypt.compare(userInput, storedHash);
```

---

#### 3. Sessions and Cookies

* **Session**: Stores user info on the server
* **Cookie**: Stores session ID on client browser

**Install session middleware:**

```bash
npm install express-session
```

**Setup in Express:**

```js
const session = require('express-session');

app.use(session({
  secret: 'yourSecretKey',
  resave: false,
  saveUninitialized: false,
  cookie: { secure: false } // secure: true for HTTPS
}));
```

**Set session on login:**

```js
req.session.userId = user._id;
```

**Check session:**

```js
if (req.session.userId) {
  // user is logged in
}
```

---

#### 4. Local Authentication (Manual)

* User signs up → password hashed → saved to DB
* User logs in → password compared → session created
* Logout → session destroyed

**Steps:**

1. Create login and register routes
2. Use bcrypt to hash/compare
3. Store user session on login
4. Destroy session on logout

---

#### 5. Authentication with Passport.js

Passport is a **modular auth middleware** for Express.

**Install:**

```bash
npm install passport passport-local
```

**Basic Setup:**

```js
const passport = require('passport');
const LocalStrategy = require('passport-local').Strategy;

passport.use(new LocalStrategy(User.authenticate()));
passport.serializeUser(User.serializeUser());
passport.deserializeUser(User.deserializeUser());
```

**In Express:**

```js
app.use(passport.initialize());
app.use(passport.session());
```

**Login:**

```js
app.post('/login', passport.authenticate('local', {
  successRedirect: '/dashboard',
  failureRedirect: '/login'
}));
```

Use `passport-local-mongoose` for easy integration with Mongoose.

---

#### 6. Using Environment Variables (`.env`)

* Store API keys, DB passwords, JWT secrets in `.env` file
* Prevents secrets from being pushed to GitHub

**Install dotenv:**

```bash
npm install dotenv
```

**In code:**

```js
require('dotenv').config();
const apiKey = process.env.API_KEY;
```

---

#### 7. OAuth 2.0 — Login with Google / Facebook

**Install Strategy:**

```bash
npm install passport-google-oauth20
```

**Google OAuth Setup:**

1. Get Client ID and Secret from Google Cloud Console
2. Create route:

```js
passport.use(new GoogleStrategy({
  clientID: process.env.GOOGLE_ID,
  clientSecret: process.env.GOOGLE_SECRET,
  callbackURL: '/auth/google/callback'
}, function(accessToken, refreshToken, profile, done) {
  // Handle login/signup logic
}));
```

**Trigger OAuth Flow:**

```js
app.get('/auth/google', passport.authenticate('google', {
  scope: ['profile', 'email']
}));
```

---

### Summary

| Concept            | Tool / Technique                            |
| ------------------ | ------------------------------------------- |
| Hashing + Salting  | `bcrypt.hash()`, `bcrypt.compare()`         |
| Sessions & Cookies | `express-session`                           |
| Local Auth         | Manual login/session setup                  |
| Passport.js        | Pluggable auth framework                    |
| `.env`             | `dotenv` to hide API keys/secrets           |
| OAuth              | Google/Facebook login using Passport OAuth2 |

<footer>TO BE CONT...</footer>
