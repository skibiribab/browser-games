# backend

Rust REST API (axum) for browser-games.

- `auth/` — IAM-like: local accounts (register/login, argon2, JWT) + OAuth2 (Google and others).
- `games/` — puzzle endpoints, submit score, leaderboard.
- `db/` — PostgreSQL (games, puzzles, users, progress, scores).
