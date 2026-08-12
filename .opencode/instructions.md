# Browser-games conventions

Browser games, Rust-first. No TypeScript outside the launcher.

## Structure

- `src/rust/backend/` — axum API: `auth/` (local + OAuth2), `games/`, `db/` (PostgreSQL).
- `src/rust/engines/` — wasm32 crates (single-threaded, canvas): `sudoku` · `logic-grid` · `crosswords`.
- `src/frontend/launcher/` — React + TS (the only TS UI): login + game selector.
- `src/catalog/games.yaml` — the game roadmap (source of truth); each game maps to an issue + `/play/<slug>`.
- `src/data/` — per-game datasets.

## Rules

- Games render via Rust → wasm to canvas; keep wasm single-threaded (GitHub Pages–compatible).
- No TypeScript outside `frontend/launcher`.
- New games: catalog entry first, then a wasm engine crate + data.
- Theme: `GitHub Dark Default`.

## CI

- `test.yml` — PR gate: `cli repo lint`.
- `release.yml` — main: validate + timestamp tag + GitHub release. No deployments.
