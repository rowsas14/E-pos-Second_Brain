<!--
meta:
  title: Clean Architecture Rules
  owner: Backend Engineering
  status: active
  last_reviewed: 2026-04-22
  tags: [clean-architecture, backend-rules, dependency-direction, dotnet]
-->

# Clean Architecture Rules

## Purpose

This file defines the Clean Architecture rules for the backend.

The backend must use Clean Architecture in a way that supports real unified commerce workflows, not just folder separation.

## Dependency direction

Dependencies must move inward.

```text
API -> Application -> Domain
Infrastructure -> Application / Domain contracts
Domain -> no dependency on API or Infrastructure
```

### Practical rule

- API can depend on Application
- Infrastructure can depend on Application and Domain to implement contracts
- Application can depend on Domain
- Domain must not depend on API or Infrastructure

## Layer responsibilities

| Layer | Owns |
|---|---|
| API | HTTP endpoints, request/response models, middleware, filters |
| Application | use cases, orchestration, interfaces, validators, DTO contracts |
| Domain | business model, invariants, aggregates, value objects, domain services |
| Infrastructure | persistence, EF Core, repositories, integrations, Unit of Work implementation |

## What must not be mixed

### API must not contain

- repository logic
- DbContext access
- workflow orchestration
- domain mutation rules

### Application must not contain

- direct HTTP concerns
- controller-specific formatting
- EF Core implementation details
- infrastructure registration logic

### Domain must not contain

- DTOs
- request/response models
- repository implementations
- EF Core DbContext
- external service SDKs

### Infrastructure must not contain

- controller behavior
- business ownership of use-case rules
- domain rule ownership

## Module boundary rule

Feature/module grouping must exist inside layers, but modules must still respect layer direction.

Correct approach:

- module exists in each relevant layer
- each layer keeps only its own responsibility

## Commerce-specific rule

Because this platform has transaction-sensitive operations, Clean Architecture must still preserve:

- same-tenant validation
- payment safety
- stock movement correctness
- return / exchange document separation
- capability-based access boundaries

## Interface rule

Where contracts are needed, define them in the Application layer.

Common examples:

- service interfaces
- repository interfaces
- Unit of Work contract
- user/context contracts

Implement them in Infrastructure or API-adjacent composition, not in Domain.

## Related documents

- [backend-folder-structure.md](./backend-folder-structure.md)
- [application-layer-rules.md](./application-layer-rules.md)
- [domain-layer-rules.md](./domain-layer-rules.md)
- [infrastructure-layer-rules.md](./infrastructure-layer-rules.md)
- [../02-architecture/clean-architecture-rules.md](../02-architecture/clean-architecture-rules.md)
