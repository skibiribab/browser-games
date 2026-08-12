# Add a game — boilerplate

browser-games is a full-stack monorepo. Adding a game follows a fixed pattern; the game logic itself is tracked as issues.

## Steps

1. **Catalog** — add/update the entry in `catalog/games.yaml` (title, slug, `/play/<slug>` route, status, tags).
2. **Frontend app** — a React + Vite app under `frontend/apps/<slug>/`, scoped `@browser-games/<slug>`. Copy an existing app shell as the starting boilerplate (Vite + tailwind + tsconfig).
3. **Launcher** — the launcher routes to `/play/<slug>`; the catalog is the source of truth for the game list.
4. **Backend service (optional)** — under `backend/services/<slug>`, wired through the gateway.
5. **Data** — per-game data under `data/<slug>/`.
6. **Issue** — open a GitHub issue (label `game`) for the game logic (generator/solver/etc.), referencing the catalog entry.

## Keep it focused

The daily pillars are **sudoku · logic grid · crosswords**. Other game ideas live as issues, not in the active catalog.
