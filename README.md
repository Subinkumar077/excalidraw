# Collab Board

Realtime collaborative whiteboard with web and Next.js clients, backed by HTTP and WebSocket services. This repo is a Turbo + pnpm monorepo.

## Apps

- [apps/excelidraw-frontend](apps/excelidraw-frontend): Primary Next.js whiteboard UI.
- [apps/web](apps/web): Additional Next.js client (chat/room UI).
- [apps/http-backend](apps/http-backend): Express HTTP API.
- [apps/ws-backend](apps/ws-backend): WebSocket collaboration server.

## Packages

- [packages/db](packages/db): Prisma schema, migrations, and DB client.
- [packages/common](packages/common): Shared types.
- [packages/backend-common](packages/backend-common): Backend shared helpers.
- [packages/ui](packages/ui): Reusable UI components.
- [packages/eslint-config](packages/eslint-config): Shared lint rules.
- [packages/typescript-config](packages/typescript-config): Shared TS configs.

## Tech Stack

- Next.js 15 + React 19
- Express + WebSocket (ws)
- Prisma
- Turbo + pnpm workspaces

## Getting Started

### Prerequisites

- Node.js >= 18
- pnpm (repo uses pnpm workspaces)

### Install

```bash
pnpm install
```

### Run All Apps (Dev)

```bash
pnpm dev
```

### Run a Single App

```bash
pnpm --filter excelidraw-frontend dev
pnpm --filter web dev
pnpm --filter http-backend dev
pnpm --filter ws-backend dev
```

## Environment Variables

Create `.env` files where needed (typically per app). For frontend configuration, see:

- [apps/excelidraw-frontend/config.ts](apps/excelidraw-frontend/config.ts)
- [apps/web/app/config.ts](apps/web/app/config.ts)

Backend services may require database credentials and auth secrets depending on deployment.

## Database

Prisma schema and migrations live in [packages/db/prisma](packages/db/prisma). Use standard Prisma workflows to migrate and generate clients based on your environment.

## Repo Scripts

From the repo root:

- `pnpm dev`: run all dev servers via Turbo
- `pnpm build`: build all packages/apps
- `pnpm lint`: lint all packages/apps
- `pnpm format`: format TS/TSX/MD files

## Project Structure

```
apps/
	excelidraw-frontend/   # Next.js whiteboard UI
	web/                   # Next.js chat/room UI
	http-backend/          # Express API
	ws-backend/            # WebSocket server
packages/
	db/                    # Prisma schema + client
	common/                # Shared types
	backend-common/        # Backend shared helpers
	ui/                    # UI component library
	eslint-config/         # Shared lint config
	typescript-config/     # Shared TS config
```

## License

MIT
