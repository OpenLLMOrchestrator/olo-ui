# Olo (frontend)

REST-oriented frontend for Olo. Built with React, TypeScript, and Vite. Proxies `/api` to the backend (olo-be).

## Requirements

- Node.js 18+
- npm or pnpm

## Setup

```bash
npm install
```

## Run

```bash
npm run dev
```

App runs at `http://localhost:3000`. Ensure olo-be is running on port 8082 for API calls.

## Build

```bash
npm run build
npm run preview
```

## Storybook (UI in isolation)

Develop and review UI components without running the backend or Redis:

```bash
npm run storybook
```

Stories for TenantConfigurationList, TenantConfigForm, and ToolsPanel use mock data. Add stories in `src/**/*.stories.tsx` for new components.

## Docs

- **Architecture (contributors):** [docs/ARCHITECTURE.md](../docs/ARCHITECTURE.md) — state philosophy, naming, store vs local state, store creation guidelines.
- **UI/UX and implementation:** [docs/UI-UX-AND-IMPLEMENTATION.md](../docs/UI-UX-AND-IMPLEMENTATION.md).
