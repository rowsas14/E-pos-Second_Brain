<!--
meta:
  title: Repository Rules
  owner: Backend Engineering
  status: active
  last_reviewed: 2026-04-23
  tags: [repositories, persistence, tenant-aware-data-access, unit-of-work]
-->

# Repository Rules

## Purpose

This file defines repository usage for the backend.

Repositories exist to isolate persistence access and keep application services from depending directly on EF Core implementation details.

## Repository contract direction

The uploaded backend direction supports:

- repository interfaces documented where relevant
- repository implementations in Infrastructure
- Unit of Work integration for coordinated commits

Recommended contract placement:

- module-specific repository interfaces in Application module `Interfaces/`
- shared repository contracts only when the abstraction is genuinely shared

## What belongs in repositories

Repositories may handle:

- entity retrieval
- tenant-aware query filtering
- persistence lookups
- list queries needed by application services
- aggregate loading for business operations
- data existence checks
- save/update/remove operations as defined by the contract

## What should not belong in repositories

Repositories should not own:

- endpoint formatting
- controller logic
- use-case orchestration
- permission decision flow
- effective feature-capability resolution
- multi-module transaction orchestration

## Tenant-aware access rule

Repositories in this project must respect tenant-aware access expectations.

That includes queries involving:

- tenant_id scoped records
- outlet_id scoped records
- user assignments inside the same tenant
- customer data that is tenant-specific
- capability or configuration rows scoped by tenant, outlet, or user

## Default role mapping note

A repository may read role, permission, capability, or configuration data as part of a query.

However, the repository must not decide final authorization based only on a seeded default role mapping.

Resolving **effective access** is a higher-layer concern and belongs in Application and validation flow.

## Repository and Unit of Work

Repositories should not commit independently when the workflow belongs to a larger transaction boundary.

Application service coordinates:

- repository calls
- Unit of Work commit
- rollback behavior through exception flow

## Naming rule

Prefer module-specific names:

- `IProductRepository`
- `IOrderRepository`
- `IPaymentRepository`
- `IInventoryRepository`

Avoid vague abstractions such as `IGenericRepository` when they obscure business intent.

## Related documents

- [infrastructure-layer-rules.md](./infrastructure-layer-rules.md)
- [transaction-handling-rules.md](./transaction-handling-rules.md)
- [service-layer-rules.md](./service-layer-rules.md)
- [validation-rules.md](./validation-rules.md)
- [naming-conventions.md](./naming-conventions.md)
- [../04-data/tenant-consistency-rules.md](../04-data/tenant-consistency-rules.md)
