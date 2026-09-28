# open-seo — Architecture Summary

> Generated from static analysis on 2026-09-28.

## Components

| Layer | Present | Evidence |
| --- | --- | --- |
| Presentation / UI | yes | 0 route module(s), 81 component file(s) |
| API / server | yes | 0 handler(s), entrypoints: src/client/features/keywords/components/index.ts, src/client/tanstack-db/index.ts, src/db/index.ts, src/server.ts |
| Domain / business logic | unclear | no dedicated layer detected |
| Persistence | yes | no database client |
| Authentication | yes |  |

## Detected frameworks and libraries

| Package | Purpose (inferred) |
| --- | --- |
| `@ai-sdk/react` | dependency |
| `@better-auth/api-key` | dependency |
| `@cloudflare/ai-chat` | dependency |
| `@cloudflare/think` | dependency |
| `@cloudflare/vite-plugin` | dependency |
| `@cloudflare/workers-oauth-provider` | dependency |
| `@cloudflare/workers-types` | dependency |
| `@distilled.cloud/cloudflare` | dependency |
| `@effect/platform-node` | dependency |
| `@every-app/sdk` | dependency |
| `@libsql/client` | dependency |
| `@modelcontextprotocol/client` | dependency |
| `@modelcontextprotocol/sdk` | dependency |
| `@modelcontextprotocol/server` | dependency |
| `@openrouter/ai-sdk-provider` | dependency |
| `@playwright/test` | dependency |
| `@tailwindcss/vite` | dependency |
| `@tanstack/devtools-vite` | dependency |
| `@tanstack/query-core` | dependency |
| `@tanstack/react-devtools` | dependency |
| `@tanstack/react-form` | dependency |
| `@tanstack/react-query` | dependency |
| `@tanstack/react-router` | dependency |
| `@tanstack/react-router-devtools` | dependency |
| `@tanstack/react-start` | dependency |
| `@tanstack/react-table` | dependency |
| `@types/mdx` | dependency |
| `@types/node` | dependency |
| `@types/papaparse` | dependency |
| `@types/react` | dependency |
| `@types/react-dom` | dependency |
| `@vitejs/plugin-react` | dependency |
| `agents` | dependency |
| `ai` | dependency |
| `alchemy` | dependency |
| `autumn-js` | dependency |
| `better-auth` | dependency |
| `chalk` | dependency |
| `cheerio` | dependency |
| `cloudflare` | dependency |
| `daisyui` | dependency |
| `drizzle-kit` | dependency |
| `drizzle-orm` | dependency |
| `effect` | dependency |
| `fast-xml-parser` | dependency |
| `fumadocs-core` | dependency |
| `fumadocs-mdx` | dependency |
| `fumadocs-ui` | dependency |
| `htmlparser2` | dependency |
| `jose` | dependency |
| `knip` | dependency |
| `lucide-react` | dependency |
| `oxlint` | dependency |
| `oxlint-tsgolint` | dependency |
| `papaparse` | dependency |
| `portless` | dependency |
| `postgres` | dependency |
| `posthog-js` | dependency |
| `posthog-node` | dependency |
| `prettier` | dependency |

## Runtime and delivery

| Concern | Finding |
| --- | --- |
| Language mix | TypeScript, SQL, JavaScript, CSS, Python, HTML |
| Package manager | npm |
| Container | Dockerfile and/or compose present |
| Serverless / PaaS | not configured for Vercel |
| CI | none detected |
| Tests | present |
| Type safety | TypeScript |

## Environment variables referenced

- `ALCHEMY_PROFILE`
- `AUTUMN_SECRET_KEY`
- `BETTER_AUTH_SECRET`
- `BETTER_AUTH_URL`
- `CI`
- `CLOUDFLARE_ACCOUNT_ID`
- `CLOUDFLARE_API_TOKEN`
- `CLOUDFLARE_D1_DATABASE_ID`
- `CLOUDFLARE_DATABASE_ID`
- `DATAFORSEO_API_KEY`
- `DEBUG_DEPTH`
- `DOMAIN_FILTER_ACTION_MS`
- `DOMAIN_FILTER_CPU_THROTTLE`
- `DOMAIN_FILTER_MAX_INPUT_MS`
- `DOMAIN_FILTER_MAX_LONG_TASK_MS`
- `DOMAIN_FILTER_MAX_RAF_GAP_MS`
- `DOMAIN_FILTER_TOTAL_LONG_TASK_MS`
- `DO_NOT_TRACK`
- `NODE_ENV`
- `OPENSEO_TELEMETRY_DISABLED`
- `PLAYWRIGHT_CHANNEL`
- `PORT`
- `POSTGRES_DATABASE_URL`
- `SITE_URL`
- `VITE_SITE_URL`
