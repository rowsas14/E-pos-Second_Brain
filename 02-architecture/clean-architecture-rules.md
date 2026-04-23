<!--
meta:
  title: Clean Architecture Rules
  owner: Backend / Architecture
  status: active
  last_reviewed: 2026-04-22
  tags: [architecture, clean-architecture, backend-rules, dependency-direction]
-->

# Clean Architecture Rules

## Purpose

This document defines the practical Clean Architecture rules used by the backend of the Unified Commerce Platform.

It should be read with [backend-architecture.md](./backend-architecture.md) and the backend standards in [../07-backend/README.md](../07-backend/README.md).

## Why Clean Architecture matters here

This project has:

- tenant-aware access rules
- channel-specific workflows on shared foundations
- transaction-sensitive inventory and payment behavior
- feature capability governance
- configuration-driven tenant behavior

Because of that, the backend cannot be organized as controller-heavy logic with direct database coupling everywhere. The architecture must preserve clear responsibilities and dependency direction.

## Dependency direction

The dependency direction is inward.

```text id="507922"
API / Presentation
  -> Application
     -> Domain
Infrastructure
  -> Application and Domain implementations through abstractions
```

The Domain layer should not depend on Application, Infrastructure, or API concerns.

## Layer rules

### API / Presentation

Allowed responsibilities:

- controllers
- request and response contracts
- middleware and filters
- composition and endpoint exposure

Do not place here:

- business rule decisions
- tenant consistency decisions
- direct EF Core workflow logic
- orchestration for transactions

### Application

Allowed responsibilities:

- use-case orchestration
- validators
- workflow coordination
- DTO handling
- transaction coordination through abstractions
- calling repositories and external services through interfaces

Do not place here:

- ASP.NET controller concerns
- raw SQL or EF Core-specific code
- presentation formatting logic

### Domain

Allowed responsibilities:

- business entities and aggregates
- value objects
- enums and domain-specific concepts
- domain rules that are not infrastructure-dependent
- domain services where needed

Do not place here:

- HTTP concerns
- database access concerns
- UI concerns
- infrastructure integration code

### Infrastructure

Allowed responsibilities:

- EF Core persistence
- repository implementations
- external integrations
- provider-specific or storage-specific logic
- transaction infrastructure

Do not place here:

- business meaning that belongs to Domain
- endpoint behavior that belongs to API
- use-case orchestration that belongs to Application

## Module boundary rules

The backend follows feature or module grouping.

That means code should stay close to its owning module, but module grouping does not cancel layer rules.

For example:

- a payment module can have API, Application, Domain, and Infrastructure parts
- a return/exchange module can have API, Application, Domain, and Infrastructure parts
- cross-module behavior must still respect dependency direction

## Transaction-sensitive workflow rules

Some workflows cross multiple data changes and must remain coordinated.

Examples supported by the project direction:

- POS sale completion
- order creation with reservation behavior
- payment allocation
- refund handling
- return and exchange flows
- stock movement posting

These workflows should be coordinated in the **Application layer** while using Domain rules and Infrastructure persistence without collapsing everything into one layer.

## Tenant and access rules inside Clean Architecture

Tenant awareness and access control are not excuses to bypass architecture boundaries.

Expected pattern:

- API receives tenant-aware requests and identity context
- Application validates scope and orchestrates workflow
- Domain enforces business meaning where the rule belongs there
- Infrastructure persists the result correctly

## Common mixing mistakes to avoid

- controller directly updates many tables for a business workflow
- repository decides business approval rules
- domain entity reads HTTP or persistence concerns
- infrastructure classes become the real business service layer
- one “service” class mixes API mapping, domain rules, EF Core access, and permission logic together

## Practical rule summary

| Concern | Preferred home |
|---|---|
| endpoint exposure | API |
| use-case workflow | Application |
| business rule meaning | Domain |
| persistence and integration | Infrastructure |
| transaction coordination | Application using infrastructure abstractions |
| tenant-aware storage implementation | Infrastructure with rules enforced through Application and data constraints |

## Related documents

- [backend-architecture.md](./backend-architecture.md)
- [multi-tenant-architecture.md](./multi-tenant-architecture.md)
- [../07-backend/application-layer-rules.md](../07-backend/application-layer-rules.md)
- [../07-backend/domain-layer-rules.md](../07-backend/domain-layer-rules.md)
- [../07-backend/infrastructure-layer-rules.md](../07-backend/infrastructure-layer-rules.md)
- [../07-backend/transaction-handling-rules.md](../07-backend/transaction-handling-rules.md)
