# Contributing

Thanks for contributing to `browser-games`.

## Conventions

- Editor rules live in `.editorconfig` + `.vscode/settings.json`.
- Games are added via the catalog first: `src/catalog/games.yaml` (each game = one issue + one `/play/<slug>` route).
- Package scope is `@browser-games/*`.
- No TypeScript outside `frontend/launcher`.
- `test.yml` gates pull requests — keep it green.

## PR workflow

1. Branch from `main`.
2. Make a focused change.
3. Open a PR into `main`.
