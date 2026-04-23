<!--
meta:
  title: Domain Layer Rules
  owner: Backend Engineering
  status: active
  last_reviewed: 2026-04-22
  tags: [domain-layer, entities, aggregates, invariants, business-rules]
-->

# Domain Layer Rules

## Purpose

This file defines what belongs in the Domain layer for this project.

The Domain layer contains the pure business model and must protect the rules that should remain true regardless of API shape or persistence strategy.

## What belongs here

The Domain layer may contain:

- entities
- aggregates
- value objects
- domain services
- invariant-protecting behavior
- shared base domain concepts where justified

Examples visible in the uploaded backend direction include:

- `Product.cs`
- `ProductCategory.cs`
- `Order.cs`
- `OrderItem.cs`
- `OrderDomainService.cs`
- `Payment.cs`
- `Customer.cs`
- `StockItem.cs`

## Domain responsibilities in this platform

The domain model should help preserve rules around:

- variant-level sellable behavior
- payment state integrity
- return and exchange document meaning
- inventory-sensitive business meaning
- status transitions that should not become arbitrary updates

## Domain invariants

Use the Domain layer for rules that should hold even if the caller changes.

Examples of suitable invariant style in this project:

- an aggregate cannot move into an invalid status transition
- business documents cannot be mutated in ways that violate their meaning
- sellable behaviors remain tied to the approved model
- domain objects should not silently accept impossible values

## Domain services

Use domain services only when business logic does not fit naturally inside one entity or aggregate.

A domain service is appropriate when:

- the behavior is domain-specific
- it is not about HTTP or persistence
- it coordinates domain reasoning across objects

## What must not live here

The Domain layer must not depend on:

- controllers
- request/response models
- DTOs
- repository implementations
- EF Core DbContext
- external service SDKs

## Related documents

- [clean-architecture-rules.md](./clean-architecture-rules.md)
- [application-layer-rules.md](./application-layer-rules.md)
- [repository-rules.md](./repository-rules.md)
- [../04-data/schema-principles.md](../04-data/schema-principles.md)
- [../08-modules/](../08-modules/)
