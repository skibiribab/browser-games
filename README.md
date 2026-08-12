# puzzle-arcade

All-in-one hub for old-school games and puzzles — like a *banca de jornal*. The **launcher** is the home page: one game selector that drops you into any game, all in this single monorepo.

Full-stack: a React + TypeScript frontend with per-game apps, a service-based backend, a game catalog, and per-game data.

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

The catalog (`catalog/games.yaml`) is the source of truth — every game maps to a GitHub issue and a `/play/<slug>` route:

| Game | Route |
|---|---|
| Sudoku | `/play/sudoku` |
| Crosswords | `/play/crosswords` |
| Logic Puzzles | `/play/logic-puzzles` |
| N-Queens | `/play/n-queens` |
| Numerox | `/play/numerox` |
| Numerox Letters | `/play/numerox-letters` |
| Tango | `/play/tango` |

More are planned in the catalog (chess, checkers, nonogram, and others) — see `docs/GAMES.md` for status.

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
