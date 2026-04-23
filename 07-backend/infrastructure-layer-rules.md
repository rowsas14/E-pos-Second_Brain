<!--
meta:
  title: Infrastructure Layer Rules
  owner: Backend Engineering
  status: active
  last_reviewed: 2026-04-22
  tags: [infrastructure, ef-core, persistence, repositories, unit-of-work]
-->

# Infrastructure Layer Rules

## Purpose

This file defines what belongs in the Infrastructure layer.

Infrastructure exists to implement contracts and technical access patterns without owning the business meaning of the platform.

## What belongs here

Infrastructure should contain:

- EF Core DbContext
- entity configurations
- migrations
- repository implementations
- Unit of Work implementation
- external integration service implementations
- persistence-specific query logic

## Typical structure

```text
Infrastructure/
  Persistence/
    ApplicationDbContext.cs
    Configurations/
    Migrations/
  Repositories/
    Products/
    Orders/
    Payments/
  Services/
    PaymentGateway/
    Notifications/
  UnitOfWork/
    UnitOfWork.cs
```

## EF Core responsibility

EF Core usage belongs here, including:

- table mapping
- relationships
- indexes and constraints expressed through model configuration
- query implementation details
- transaction and save coordination through Unit of Work

## Repository implementation rule

Infrastructure implements repository contracts defined in the Application layer.

Infrastructure repositories may contain:

- tenant-aware filtering logic
- query composition
- eager loading decisions
- lookup helpers
- persistence commands

They must not become hidden business orchestration layers.

## Unit of Work implementation rule

The backend direction explicitly allows **Unit of Work** where relevant.

Recommended pattern:

- contract in Application common interfaces
- implementation in Infrastructure
- used by Application services during multi-step workflows

## What should stay out of Infrastructure

Do not put these here as owners:

- controller behavior
- use-case orchestration
- permission decisions that belong in Application workflow logic
- domain invariants

## Related documents

- [repository-rules.md](./repository-rules.md)
- [transaction-handling-rules.md](./transaction-handling-rules.md)
- [mapping-rules.md](./mapping-rules.md)
- [../04-data/migration-strategy.md](../04-data/migration-strategy.md)
- [../04-data/tenant-consistency-rules.md](../04-data/tenant-consistency-rules.md)
