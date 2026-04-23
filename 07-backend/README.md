<!--
meta:
  title: Backend Documentation
  owner: Backend Engineering
  status: active
  last_reviewed: 2026-04-22
  tags: [backend, clean-architecture, dotnet, navigation]
-->

# Backend Documentation

## Purpose

This section documents the backend engineering direction for the **Unified Commerce Platform**.

The project backend is built on **.NET Web API with Clean Architecture** and must support one platform that combines:

- tenant-aware E-POS operations
- tenant-aware E-Commerce operations
- platform administration separated from tenant staff access
- customer-specific per-tenant behavior
- variant-level sellable flows
- inventory, payment, return, exchange, and reporting workflows that are sensitive to data consistency and transaction boundaries

This section exists so backend changes do not drift away from the approved business model, schema rules, API rules, and module boundaries.

## Why this section matters

In this project, backend mistakes do not stay local.

A poor backend decision can break:

- tenant isolation
- permission boundaries
- POS speed
- inventory correctness
- payment allocation integrity
- return / exchange behavior
- configuration ownership between platform and tenant

The backend must therefore follow both **Clean Architecture rules** and **project-specific commerce rules**.

## What this section covers

| File | Purpose |
|---|---|
| [backend-overview.md](./backend-overview.md) | high-level backend role and responsibilities |
| [backend-folder-structure.md](./backend-folder-structure.md) | expected codebase structure and folder ownership |
| [clean-architecture-rules.md](./clean-architecture-rules.md) | dependency direction and layer separation rules |
| [application-layer-rules.md](./application-layer-rules.md) | orchestration, DTO contracts, interfaces, validators, and workflow coordination |
| [domain-layer-rules.md](./domain-layer-rules.md) | entities, aggregates, value objects, domain services, and invariants |
| [infrastructure-layer-rules.md](./infrastructure-layer-rules.md) | EF Core, repositories, integrations, persistence, and Unit of Work implementation direction |
| [service-layer-rules.md](./service-layer-rules.md) | service design rules and separation of service types |
| [repository-rules.md](./repository-rules.md) | repository contract and query responsibilities |
| [transaction-handling-rules.md](./transaction-handling-rules.md) | transaction boundaries for sensitive workflows |
| [validation-rules.md](./validation-rules.md) | request, business, and tenant consistency validation |
| [exception-handling-rules.md](./exception-handling-rules.md) | backend exception strategy and global handling |
| [dto-handling-rules.md](./dto-handling-rules.md) | DTO patterns, placement, and naming |
| [mapping-rules.md](./mapping-rules.md) | Request -> DTO -> Domain -> Response mapping rules |
| [naming-conventions.md](./naming-conventions.md) | class and contract naming rules |

## Read first by task

| Task | Read first |
|---|---|
| understand backend direction | [backend-overview.md](./backend-overview.md), [backend-folder-structure.md](./backend-folder-structure.md) |
| create a new use case | [application-layer-rules.md](./application-layer-rules.md), [dto-handling-rules.md](./dto-handling-rules.md), [mapping-rules.md](./mapping-rules.md) |
| define or change domain rules | [domain-layer-rules.md](./domain-layer-rules.md), [transaction-handling-rules.md](./transaction-handling-rules.md) |
| add or change persistence logic | [infrastructure-layer-rules.md](./infrastructure-layer-rules.md), [repository-rules.md](./repository-rules.md) |
| add validators or business checks | [validation-rules.md](./validation-rules.md) |
| change API error behavior | [exception-handling-rules.md](./exception-handling-rules.md), [../05-api/error-contract.md](../05-api/error-contract.md) |
| review naming and file placement | [naming-conventions.md](./naming-conventions.md), [backend-folder-structure.md](./backend-folder-structure.md) |

## Read with these related sections

Backend work in this project should not be done in isolation.

Read with:

- [../02-architecture/backend-architecture.md](../02-architecture/backend-architecture.md)
- [../02-architecture/clean-architecture-rules.md](../02-architecture/clean-architecture-rules.md)
- [../04-data/database-overview.md](../04-data/database-overview.md)
- [../04-data/tenant-consistency-rules.md](../04-data/tenant-consistency-rules.md)
- [../05-api/api-overview.md](../05-api/api-overview.md)
- [../05-api/request-response-standard.md](../05-api/request-response-standard.md)
- relevant feature docs in [../08-modules/](../08-modules/)

## Project-specific backend priorities

The backend is expected to preserve these platform rules:

- platform admin is separate from tenant staff
- staff users are tenant-bound
- customers are tenant-specific
- variant is the sellable unit for price, stock, sale, cart, and order flows
- inventory follows ledger + projection principles
- returns and exchanges are separate documents, not normal sales rows
- feature access is assignable by platform admin and configurable inside the customer tenant
- POS-sensitive workflows must stay fast and predictable

## Related documents

- [backend-overview.md](./backend-overview.md)
- [backend-folder-structure.md](./backend-folder-structure.md)
- [clean-architecture-rules.md](./clean-architecture-rules.md)
- [../02-architecture/backend-architecture.md](../02-architecture/backend-architecture.md)
- [../04-data/schema-principles.md](../04-data/schema-principles.md)
- [../05-api/README.md](../05-api/README.md)
