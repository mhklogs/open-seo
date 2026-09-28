# open-seo — Functional Requirements

> Derived from static analysis of the source tree on 2026-09-28. Each requirement cites
> the file that evidences it, so any claim can be checked. Requirements marked
> *inferred* are derived from naming and structure rather than an explicit
> specification.

## FR-1 Route and page behaviour

No file-system-routed pages were detected. This project appears to be a library, CLI, notebook collection, or a single-page entrypoint.

| ID | Requirement | Evidence |
| --- | --- | --- |
| FR-1.01 | The system shall provide the entrypoint `src/client/features/keywords/components/index.ts` | `src/client/features/keywords/components/index.ts` |
| FR-1.02 | The system shall provide the entrypoint `src/client/tanstack-db/index.ts` | `src/client/tanstack-db/index.ts` |
| FR-1.03 | The system shall provide the entrypoint `src/db/index.ts` | `src/db/index.ts` |
| FR-1.04 | The system shall provide the entrypoint `src/server.ts` | `src/server.ts` |
| FR-1.05 | The system shall provide the entrypoint `src/server/features/keywords/services/research/index.ts` | `src/server/features/keywords/services/research/index.ts` |
| FR-1.06 | The system shall provide the entrypoint `src/server/lib/dataforseo/index.ts` | `src/server/lib/dataforseo/index.ts` |
| FR-1.07 | The system shall provide the entrypoint `src/server/mcp/server.ts` | `src/server/mcp/server.ts` |

## FR-2 Programmatic interface

*No API route handlers detected.*

## FR-3 Presentation components

The interface is composed of 81 component module(s) under `components/`. Each shall render without server-side state leakage between routes.

## FR-6 Access control

An authentication or session library is a dependency. The system shall authenticate before serving protected resources, and shall reject unauthenticated requests with a 401/403 rather than a redirect loop. *(inferred)*

## FR-7 Persistence

A database or storage client is a dependency. The system shall persist domain records durably, and shall not lose writes on transient failure. *(inferred)*

## FR-8 Configuration

The following environment variables are referenced in source. Each shall be
validated at startup with a clear error when missing.

| Variable | Referenced in |
| --- | --- |
| `ALCHEMY_PROFILE` | see source |
| `AUTUMN_SECRET_KEY` | see source |
| `BETTER_AUTH_SECRET` | see source |
| `BETTER_AUTH_URL` | see source |
| `CI` | see source |
| `CLOUDFLARE_ACCOUNT_ID` | see source |
| `CLOUDFLARE_API_TOKEN` | see source |
| `CLOUDFLARE_D1_DATABASE_ID` | see source |
| `CLOUDFLARE_DATABASE_ID` | see source |
| `DATAFORSEO_API_KEY` | see source |
| `DEBUG_DEPTH` | see source |
| `DOMAIN_FILTER_ACTION_MS` | see source |
| `DOMAIN_FILTER_CPU_THROTTLE` | see source |
| `DOMAIN_FILTER_MAX_INPUT_MS` | see source |
| `DOMAIN_FILTER_MAX_LONG_TASK_MS` | see source |
| `DOMAIN_FILTER_MAX_RAF_GAP_MS` | see source |
| `DOMAIN_FILTER_TOTAL_LONG_TASK_MS` | see source |
| `DO_NOT_TRACK` | see source |
| `NODE_ENV` | see source |
| `OPENSEO_TELEMETRY_DISABLED` | see source |
| `PLAYWRIGHT_CHANNEL` | see source |
| `PORT` | see source |
| `POSTGRES_DATABASE_URL` | see source |
| `SITE_URL` | see source |
| `VITE_SITE_URL` | see source |
