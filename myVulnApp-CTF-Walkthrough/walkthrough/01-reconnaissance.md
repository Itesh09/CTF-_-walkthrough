# 1. Reconnaissance

## Initial Access

We started by navigating to the target URL: `http://152.42.242.139:5000`

The application presents a login page with the following options:
- Login form with username/password fields
- "Remember Me" checkbox
- Register new account link
- Forgot password link

## Basic Reconnaissance Steps

### 1. Identify Technology Stack

- **Server:** Flask (Python)
- **Port:** 5000
- **Framework:** Werkzeug
- **Database:** SQLite (discovered later)

### 2. Check HTTP Headers

```
Server: Werkzeug/3.1.3 Python/3.12.8
Content-Type: text/html; charset=utf-8
```

### 3. Directory Enumeration

Initial gobuster scan revealed:

```
/login          (302) -> Login page
/register       (200) -> Registration page
/logout         (302) -> Logout
/dashboard      (302) -> User dashboard (requires auth)
/profile        (302) -> User profile (requires auth)
/upload         (302) -> File upload (requires auth)
/search         (200) -> Search functionality
/admin          (302) -> Admin panel (redirects to login)
/debug          (200) -> Debug information
/debug_api      (200) -> Debug API endpoint
/password_viewer (200) -> Password viewer
/robots.txt     (200) -> Robots.txt file
/app.db         (200) -> Database file exposed!
```

### 4. Information Gathering

**robots.txt contents:**
```
User-agent: *
Disallow: /admin
Disallow: /debug
Disallow: /app.db
```

The robots.txt actually points us to interesting endpoints!

### 5. Initial Credentials

From the CTF description:
- **Username:** `bob`
- **Password:** `bob123`

Using these credentials, we can access the dashboard and begin exploring vulnerabilities.

## Findings Summary

| Endpoint | Status | Notes |
|----------|--------|-------|
| /login | 200 | Login form |
| /register | 200 | Registration |
| /dashboard | 302 | Auth required |
| /admin | 302 | Auth required |
| /debug | 200 | Exposed! |
| /debug_api | 200 | Exposed! |
| /password_viewer | 200 | Exposed! |
| /app.db | 200 | Database exposed! |

## Next Steps

Proceed to [02-sql-injection.md](./02-sql-injection.md) to exploit the SQL injection vulnerability.
