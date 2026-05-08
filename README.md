# Guardrail Frontend

Guardrail Frontend is the SolidStart web application for the Guardrail platform. It powers the public
asset feed, market and event discovery, search, and authenticated portfolio and asset-request
workflows.

## Highlights

- Public asset feed with featured, new, category, and tag filters
- Market and event detail pages with pricing, liquidity, and discussion data
- Market search and topic/category browsing
- Authenticated portfolio dashboard with balances and trade history
- Asset request submission and status tracking
- Google and wallet-based sign-in, plus a USDC faucet flow for test environments

## Tech stack

- [SolidStart](https://start.solidjs.com/) / [SolidJS](https://www.solidjs.com/)
- [Vite](https://vitejs.dev/)
- TypeScript
- [Visx](https://airbnb.io/visx/) for data visualization
- Nitro presets for Node and Vercel deployments

## Requirements

- Node.js **>= 22**
- pnpm (recommended, lockfile included)

## Getting started

```bash
pnpm install
pnpm dev
```

The app runs at `http://localhost:3000` by default.

## Environment variables

Create a `.env` file in the project root as needed.

| Variable | Required | Purpose |
| --- | --- | --- |
| `VITE_API_BASE_URL` | Yes (non-proxy) | Base URL for the Guardrail API. |
| `VITE_DEV_API_PROXY_TARGET` | Optional | Dev-only proxy target. When set, `/api` requests are proxied to this target. |
| `VITE_GOOGLE_CLIENT_ID` | Optional | Google OAuth client ID for Google sign-in. |

### Test-only variables

| Variable | Purpose |
| --- | --- |
| `MARKET_INTEGRATION_BASE_URL` | Overrides the API base URL for integration tests. |
| `AUTH_INTEGRATION_BASE_URL` | Alternate integration base URL for auth/market tests. |

## Available scripts

| Command | Description |
| --- | --- |
| `pnpm dev` | Start the local development server. |
| `pnpm build` | Build the production bundle. |
| `pnpm start` | Start the production server (after build). |
| `pnpm preview` | Preview the production build locally. |
| `pnpm test` | Run the Node-based unit tests. |

## Project structure

```
src/
  components/      Reusable UI components and modals
  lib/             API clients, domain logic, and utilities
  routes/          File-based routes
public/            Static assets
test/              Test helpers and fixtures
```

## Deployment

- `pnpm build` produces a Nitro output configured for Node or Vercel.
- When the `VERCEL` environment variable is present, the app builds with the Vercel preset.

## Troubleshooting

- Ensure you are running Node.js 22+ (the build and tests rely on newer Node APIs).
- If API calls fail in development, set `VITE_DEV_API_PROXY_TARGET` and restart the dev server.

## License

No license file is currently included. Unless a license is added, assume all rights are reserved by the
repository owner.
