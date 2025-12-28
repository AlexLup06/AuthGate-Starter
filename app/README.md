
# Example Application

This directory represents **your application**.

In the Authgate starter setup, this is a simple placeholder served by Nginx.
It exists only to demonstrate how Authgate routes traffic.

---

## Routing

With the default configuration:

- Requests to `/auth/*` are handled by **Authgate**
- Requests to `/` are handled by **this application**

You can verify this by visiting:

    http://localhost
    http://localhost/auth/login

---

## Replacing this app

To use Authgate with your real application:

1. Replace the `app` service in `docker-compose.yml`
2. Point it to your backend (Go, Node, Python, etc.)
3. Add Authgate request validation middleware

Authgate handles authentication.  
Your app handles authorization and business logic.

---

## Important

This directory is **not** part of Authgate itself.

It is safe to delete or replace entirely.
