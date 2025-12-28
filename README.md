# Authgate Starter

This repository lets you run **Authgate** locally in minutes using Docker.

It includes:
- Authgate (authentication service)
- A gateway (Caddy) that routes `/auth/*`
- PostgreSQL for user storage
- A placeholder application

You do **not** need to write any authentication code to get started.

---

## Requirements

- Docker
- Docker Compose

---

## Quickstart

Clone the repository:

    git clone https://github.com/yourorg/authgate-starter

Enter the directory:

    cd authgate-starter

Create your environment file:

    cp .env.example .env

Start everything:

    docker compose up

---

## Open in your browser

Main application:

    http://localhost

Authgate login page:

    http://localhost/auth/login

---

## How it works

- Requests to `/auth/*` are handled by **Authgate**
- Requests to `/` are handled by your application
- Authgate manages users, sessions, and cookies
- Your app only validates incoming requests

---

## Integrating Authgate into your app

Protect routes using the Authgate SDK.

Example (Go):

    app.Use(authgate.RequireAuth)

Unauthenticated users are automatically redirected to:

    /auth/login

---

## Customizing

You can:

- Replace the `app` service with your real backend
- Change database credentials
- Replace the gateway with Nginx or Traefik

Authgate works with **any backend language**.

---

## Production notes

Before deploying to production:

- Use a real domain (not `localhost`)
- Enable HTTPS (Caddy does this automatically)
- Set `COOKIE_SECURE=true`

---

## Authgate v1 scope

Included:
- Email + password authentication
- Hosted authentication UI
- Session-based cookies
- Redirect-based login flow
- Self-hosted deployment

Not included (v1):
- OAuth / OIDC
- Social login
- MFA / passkeys
- Multi-tenancy

---

## License

MIT
