# browser-games

All-in-one hub for old-school games and puzzles — like a *banca de jornal*. The **launcher** is the home page: one game selector that drops you into any game, all in this single monorepo.

Full-stack: a React + TypeScript frontend with per-game apps, a service-based backend, a game catalog, and per-game data.

## Focus

Three daily pillars:

- **Sudoku** — generator + auto-solve.
- **Logic grid** — grid deduction with green-check marking (the phrases game).
- **Crosswords** — solver-first with a curated puzzle bank.

Other game ideas live as issues, not in the active catalog. See [docs/ADD-A-GAME.md](docs/ADD-A-GAME.md) for the add-a-game boilerplate.

## Structure

```text
frontend/   React + TypeScript
  apps/
    launcher/        all-in-one game selector (home page)
    <game>/          one app per game
backend/    services — gateway + one service per game
catalog/    games.yaml (the roadmap) + tags
data/       per-game datasets
docs/       GAMES / GOALS / REQUIREMENTS
```

## Games

The catalog (`catalog/games.yaml`) is the source of truth — the active games are the three pillars, each mapped to a `/play/<slug>` route:

| Game | Route |
|---|---|
| Sudoku | `/play/sudoku` |
| Logic Grid | `/play/logic-puzzles` |
| Crosswords | `/play/crosswords` |

Other game ideas (n-queens, numerox, tango, chess, checkers, nonogram, and others) are tracked as issues — see `docs/GAMES.md`.

## Quick start

```bash
./start.sh
```

or, with Docker Compose:

```bash
docker compose up --build
```

`docker-compose.yml` wires the DynamoDB local + backend services; the frontend runs per-app via Vite.

## Docs

- [`docs/GAMES.md`](docs/docs/GAMES.md) — game issue roadmap
- [`docs/REQUIREMENTS.md`](docs/docs/REQUIREMENTS.md) — game requirements
- [`docs/GOALS.md`](docs/docs/GOALS.md) — project goals
