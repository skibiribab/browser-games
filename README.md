# browser-games

Browser games with a Rust + WASM focus — like a *banca de jornal*. The **launcher** is the home page: one game selector that drops you into any game. Rust-first, no TypeScript outside the launcher.

## Focus

Three daily pillars:

- **Sudoku** — generator + auto-solve.
- **Logic grid** — grid deduction with green-check marking (the phrases game).
- **Crosswords** — solver-first with a curated puzzle bank.

Other game ideas live as issues, not in the active catalog. See [docs/ADD-A-GAME.md](docs/ADD-A-GAME.md) for the add-a-game boilerplate.

## Structure

```text
src/
  rust/            Rust workspace
    backend/       axum API — auth (local + oauth) · games · db (postgres)
    engines/       wasm32 crates (single-threaded, canvas) — sudoku · logic-grid · crosswords
  frontend/
    launcher/      React + TS (the only TS UI) — login + game selector
  catalog/         games.yaml (the roadmap) + tags
  data/            per-game datasets
docker/            Dockerfile + docker-compose.yml (backend + postgres)
docs/              GAMES / GOALS / REQUIREMENTS
```

## Games

The catalog (`src/catalog/games.yaml`) is the source of truth — the active games are the three pillars, each mapped to a `/play/<slug>` route:

| Game | Route |
|---|---|
| Sudoku | `/play/sudoku` |
| Logic Grid | `/play/logic-puzzles` |
| Crosswords | `/play/crosswords` |

Other game ideas (n-queens, numerox, tango, chess, checkers, nonogram, and others) are tracked as issues — see `docs/GAMES.md`.

## Quick start

```bash
docker compose -f docker/docker-compose.yml up --build
```

## Docs

- [`docs/GAMES.md`](docs/docs/GAMES.md) — game issue roadmap
- [`docs/REQUIREMENTS.md`](docs/docs/REQUIREMENTS.md) — game requirements
- [`docs/GOALS.md`](docs/docs/GOALS.md) — project goals
