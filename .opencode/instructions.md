# Puzzle-arcade conventions

All-in-one hub for old-school games and puzzles (a *banca de jornal*): a launcher home page that routes into each game. Full-stack monorepo.

## Structure

- `frontend/` — React + TypeScript; `apps/launcher` is the game selector, one app per game.
- `backend/` — services; gateway + one service per game.
- `catalog/games.yaml` — the game roadmap (source of truth); each game maps to an issue and a `/play/<slug>` route.
- `data/` — per-game datasets.
- `docs/` — GAMES / GOALS / REQUIREMENTS.

## Rules

- New games: add a catalog entry first (`catalog/games.yaml`), then the frontend app + backend service + data.
- Package scope is `@browser-games/*`.
- Theme: `GitHub Dark Default`.

## CI

- `test.yml` — PR gate: `cli repo lint`.
- `release.yml` — main: validate + timestamp tag + GitHub release. No deployments.
