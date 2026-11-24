# MM — Simple Login / Register

Zero-build Node.js auth starter: Express server, SQLite database, bcrypt password hashing,
and a neumorphic login/register UI in a single `index.html`.

## Stack

- **Backend:** Express 5 + `sqlite3` + `bcryptjs` + `body-parser`
- **Database:** SQLite (`users.db`, created on first run)
- **Frontend:** Single static `index.html` with inline CSS/JS — no build step, no framework

## Run

```bash
npm install
node index.js
# open http://localhost:3000
```

## Routes

| Route | Method | Description |
|---|---|---|
| `GET /` | — | Serves the login/register page |
| `POST /register` | form | Hashes password with bcrypt (10 rounds), inserts user into SQLite |
| `POST /login` | form | Looks up user, compares password with bcrypt, returns success/failure |

## Security notes

- Passwords are **never stored plaintext** — bcrypt with 10 salt rounds.
- `users.db` is gitignored and never committed.
- This is a learning/starter project — add rate limiting, session tokens, and HTTPS
 before exposing it to the internet.

## Files

- `index.js` — Express app, SQLite schema, register/login routes
- `index.html` — Login/register tabbed UI with neumorphic design
- `package.json` — Dependencies (express, sqlite3, bcryptjs, body-parser)
- `.gitignore` — Excludes `node_modules/`, `*.db`, `*.sqlite`, `.env`, logs
