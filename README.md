# World Cup 2026 Bracket Predictor

A static FIFA World Cup 2026 bracket predictor that can be hosted on Vercel and shared without a database.

## Features

- All 48 FIFA World Cup 2026 teams grouped from A to L.
- Group ranking selectors for 1st, 2nd, 3rd, and 4th place.
- Round of 32 through Final prediction flow.
- Third-place knockout slots are selected from their eligible group pools.
- Shareable prediction links using URL hash state.
- No backend, API routes, authentication, cookies, or database.

## How sharing works

Predictions are encoded into the URL hash:

```text
/#p=<encoded-prediction>
```

The hash is read by the browser and reconstructed locally. Nothing is stored on a server.

## Local preview

Open `index.html` directly in a browser, or serve the folder with any static server.

```bash
npx serve .
```

## Vercel

This repository is static. Vercel can deploy it directly with no build command.

## Data notes

The app includes the 2026 group draw and the Round of 32 bracket slot structure. The official table for third-place allocations depends on which eight third-place teams qualify, so the app keeps those selections explicit for the user.