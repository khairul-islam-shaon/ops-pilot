# Roadmap

8-week build plan. Ships in phases; each phase ends with something deployed
and working rather than a half-finished layer.

| Phase | Focus | Key deliverable |
|---|---|---|
| 1 | Product & design | Scope, user stories, architecture, data model |
| 2 | Backend core | Ticket API with search/filter/pagination, deployed |
| 3 | Auth & RBAC | JWT + refresh rotation, Agent/Manager/Admin |
| 4 | Frontend shell | Dashboard, ticket table, protected routes |
| 5 | Product complete | Ticket detail, customers, UX states, E2E |
| 6 | AI intelligence | Structured ticket analysis, reply drafts, cost logging |
| 7 | AI copilot | Tool calling, natural-language ticket queries |
| 8 | Harden & ship | Security audit, perf, AI eval, docs |

## Principles

- **Deploy from phase 2.** CORS, env, connection pooling and migrations break
  early or they break late — early is cheaper.
- **Phase 5 is a checkpoint.** The product must be complete and useful with
  zero AI features before AI work starts.
- **No new features after phase 7.** Phase 8 is hardening only.
- **The AI never writes SQL.** It selects from a fixed set of tools; parameters
  are validated with Zod and authorization is re-checked inside each tool.

## Explicitly out of scope

Notifications · Slack/email integration · RAG & vector search · SLA tracking ·
Multi-tenancy · Ticket deletion (archive instead)

See [adr/](./adr/) for the reasoning behind key technical decisions.
