# Security policy

## Reporting a vulnerability

Please **do not open a public issue** for security problems. Use GitHub's private reporting instead: **Security → Report a vulnerability** on this repository.

## Deployment notes

- Mandate is a **local, single-process workspace without user authentication**. Waitress binds to loopback (`127.0.0.1`). Do not expose it to the public internet.
- API keys belong in `.env`, which is ignored by Git. `/api/health` reports the names of missing settings, never their values. Rotate any key that has been exposed.
- Allocations are paper transactions. The app never places brokerage orders.
