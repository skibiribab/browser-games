# Browser-games conventions

Browser games, Rust-first. Front-end only — no backend, no database, no accounts. Ephemeral: state lives in the browser and disappears when the tab closes.

## Structure

- `src/rust/engines/` — wasm32 crates (single-threaded, GitHub Pages–compatible): `sudoku` · `logic-grid` · `crosswords`.
- `src/frontend/launcher/` — React + TS (the only TS UI): game selector + play routes.
- `src/catalog/games.yaml` — the game roadmap (source of truth); each game maps to an issue + `/play/<slug>`.
- `src/data/` — per-game static datasets.

## Rules

- Games render via Rust → wasm to canvas; keep wasm single-threaded (GitHub Pages–compatible).
- No TypeScript outside `frontend/launcher`.
- New games: catalog entry first, then a wasm engine crate + data.
- No persistence, no network, no auth — play and it's gone when closed.
- Theme: `GitHub Dark Default`.

## CI

- `test.yml` — PR gate: `cli repo lint`.
- `pages.yml` — build launcher (+ engines) and publish to GitHub Pages.
- `release.yml` — main: validate + timestamp tag + GitHub release.
