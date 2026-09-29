# Open SEO — Delivery Roadmap (v3)

> **Provenance note.** This roadmap was produced on **2026-09-29** from the same
> static analysis as the rest of `documents/` (see `00-index.md`). Backlog items are
> derived from the functional requirements in `02-functional-requirements.md`, the
> non-functional targets in `03-non-functional-requirements.md`, and the market
> findings in `01-market-analysis.md`. Timeline targets are `[TO BE VALIDATED]`
> where they depend on future estimates rather than shipped code.
>
> **Correction carried from the analysis.** `01-market-analysis.md` positions this
> build in the *website-template* category, against Webflow and Framer. The
> repository is an SEO data platform — MCP server, Agent Skills, DataForSEO client,
> Drizzle schema, D1/Postgres — competing with Semrush and Ahrefs. The competitive
> table does not describe this product. Sprint 0 re-writes it before any positioning
> decision is taken on top of it.
>
> **Repo-state note.** `landing/index.html` has an uncommitted redesign in the
> working tree. It was left untouched by this documentation pass and must land as
> its own reviewed commit.

## 1. Objective & horizon

SEO managed-service landing/template. This roadmap plans the next **2–3 week**
horizon of incremental delivery in lockstep with the SDLC phases and traceability
rules in `07-sdlc-lifecycle.md` (Requirements → Design → Implement → Verify →
Release/Operate → Improve).

Current shipped state: https://open-seo-gules.vercel.app (production), source
committed, v2 documentation set complete. Underneath the managed-service surface
sits the full platform: `src/server.ts`, an MCP server, keyword-research and
DataForSEO services, a Drizzle schema that runs on both SQLite/libSQL and Postgres,
Better Auth, and a Cloudflare Worker/D1 deployment path alongside the container.

## 2. Product backlog

Prioritised with MoSCoW. Items are phrased as outcomes (not tasks) and map to FR/NFR ids.

| ID | Item (outcome) | Source | Priority |
| --- | --- | --- | --- |
| PBI-01 | The managed-service landing converts: what the service includes, what it costs and what happens next are stated on the page, and every CTA resolves to a real destination on the deployed URL — no dead anchors, no placeholder links | market gap (no competitive template surface today) | Must |
| PBI-02 | Landing and README copy claims match the code: the SEO workflows, the MCP/Agent Skills integration, the bring-your-own-DataForSEO-key model and the self-host path are exactly what the repository ships | market risk "claims ahead of code" (`01-market-analysis.md` §7) | Must |
| PBI-03 | Three core workflows are proven end to end on a staging deployment — keyword research, rank tracking, site audit — each executed with a test DataForSEO key and written into `05-use-cases.md` (currently empty) | FR-1.05, FR-1.06, FR-7 | Must |
| PBI-04 | A first-time operator can self-host from the README alone: one documented sequence of commands and env vars (`BETTER_AUTH_*`, D1 or `POSTGRES_DATABASE_URL`, `DATAFORSEO_API_KEY`) yields a working instance, verified on a clean machine | FR-8, FR-6 | Should |
| PBI-05 | CI runs lint, typecheck, unit and e2e smoke suites on every push, and `01-market-analysis.md` is corrected to describe this category | NFR-6.3, NFR-6.1 | Should |
| PBI-06 | The deployed landing is measured and audited as a site — LCP/CLS baseline plus title/meta/OG/canonical/robots/sitemap check — and the numbers replace the `[TO BE MEASURED]` markers | NFR-1.1–NFR-1.5, NFR-5.6 | Won't (this horizon) |

## 3. Sprint plan

**Sprint cadence:** 1 week = 1 sprint; stand-up daily (15 min), sprint review + retrospective at the end of each sprint.

| Sprint | Goal | PBI delivered | Done/exit criteria | Phase (SDLC) |
| --- | --- | --- | --- | --- |
| Sprint 0 | Fix the market analysis before it drives decisions | — | `01-market-analysis.md` names the real category and competitors; `05-use-cases.md` carries one use case per core workflow | Requirements |
| Sprint 1 | Make the landing true and convertible | PBI-01, PBI-02 | every CTA resolved on https://open-seo-gules.vercel.app, copy checked line by line against the source | Design → Implement |
| Sprint 2 | Prove the product works, then make it reproducible | PBI-03, PBI-04 | three workflows captured in `05-use-cases.md`; self-host sequence walked on a clean machine | Implement → Verify |
| Sprint 3 | Lock it in, then measure it | PBI-05, PBI-06 | release cut deployed, CI green, audit numbers recorded with commit SHA; remaining week is the buffer | Release & Operate |

## 4. Ceremonies

- **Daily stand-up (15 min):** what shipped since yesterday, what's blocked, what's next — tied to the active sprint's PBI board.
- **Sprint review (30 min, end of sprint):** demo PBI outcomes against the sprint goal; update `05-use-cases.md` walkthrough where behavior changed.
- **Retrospective (30 min, end of sprint):** inspect + adapt; record one actionable improvement per sprint in git notes.
- **Backlog refinement (before sprint 1):** re-prioritise PBIs against latest market findings.

## 5. Burndown (planned)

Tracked as PBI points remaining per sprint. Planned trajectory below; the team records actuals at each sprint review. `[TO BE MEASURED]` until the first sprint completes.

Total 14 points: PBI-01 3, PBI-02 2, PBI-03 5, PBI-04 2, PBI-05 1, PBI-06 1. Sprint 0 is unpointed re-baselining.

| Sprint | Planned remaining points |
| --- | --- |
| Start | 14 |
| Sprint 1 | 7 |
| Sprint 2 | 0 |
| Done (0) | 0 |

Sprint 2 carries PBI-05 and PBI-06, which close the horizon at 0 points; any overrun moves into the tail of sprint 3.

## 6. Rollout & deploy

- Build/deploy per `07-sdlc-lifecycle.md` §5 (release policy) — containerised or Cloudflare Worker path, with the static landing deployed to the managed-service host.
- Production: https://open-seo-gules.vercel.app
- Health: a broken build blocks the next sprint's first commit; security findings are release blockers.

## 7. Risks

| Risk | Mitigation |
| --- | --- |
| Requirements drift vs. implemented code | PBI↔FR↔use-case traceability check per change (`07-sdlc-lifecycle.md` §3) |
| Unmeasured NFRs treated as done | `[TO BE MEASURED]` targets stay visible until instrumented |
| Burndown actuals fall off plan | Over-plan cut scope in the retrospective, not mid-sprint |
| A 2–3 week horizon against a 1,300-file platform invites shallow, unverifiable claims | Only three PBIs are point-bearing, and each requires an executed artifact — a captured workflow, a clean-machine install, a green CI run |
| Wrong category in the market analysis leads to a wrong pricing and positioning bet | Sprint 0 rewrites it; PBI-05 gates on the correction landing |
| Uncommitted `landing/index.html` redesign lands unreviewed and the deployed page diverges from the repo | It stays out of the docs commit and is reviewed on its own before deploy |
