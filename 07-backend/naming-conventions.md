<!--
meta:
  title: Backend Naming Conventions
  owner: Backend Engineering
  status: active
  last_reviewed: 2026-04-22
  tags: [naming, dto, services, repositories, validators, dotnet]
-->

# Backend Naming Conventions

## Purpose

This file defines naming rules for backend classes and contracts.

The goal is consistency across modules and layers so that a reader can identify responsibility from the name alone.

## General rule

Use names that communicate:

- layer
- role
- module ownership
- use-case intent

Avoid vague names like `Manager`, `Helper`, or `CommonDto` unless the responsibility is genuinely shared and clearly bounded.

## Service naming

| Type | Pattern | Example |
|---|---|---|
| application service interface | `I{Name}Service` | `IProductService` |
| application service implementation | `{Name}Service` | `ProductService` |
| infrastructure integration interface | `I{Name}Gateway` or contract-specific name | `IPaymentGateway` |
| infrastructure integration implementation | provider or role-specific name | `StripePaymentGateway` |

## Repository naming

| Type | Pattern | Example |
|---|---|---|
| repository interface | `I{Name}Repository` | `IProductRepository` |
| repository implementation | `{Name}Repository` | `ProductRepository` |

## Unit of Work naming

| Type | Pattern | Example |
|---|---|---|
| contract | `IUnitOfWork` | `IUnitOfWork` |
| implementation | `UnitOfWork` | `UnitOfWork` |

## DTO naming

Use action- or purpose-specific names.

Good:
- `CreateProductDto`
- `UpdateProductDto`
- `ProductResponseDto`
- `ProductListDto`

Avoid:
- `ProductDto` as the universal DTO
- `BaseProductDto` unless it is truly justified

## API request and response model naming

| Type | Pattern | Example |
|---|---|---|
| request model | `{Action}{Entity}Request` | `CreateProductRequest` |
| response model | `{Entity}Response` or action-specific response | `ProductResponse` |

## Validator naming

Use:
- `{Action}{Entity}Validator`
- `{Entity}Validator` when the validator scope is clearly one entity/use case

Examples:
- `CreateProductValidator`
- `UpdateProductValidator`

## Domain naming

Use business names directly.

Examples:
- `Product`
- `Order`
- `OrderItem`
- `Payment`
- `Customer`

Value objects and domain services should also stay explicit:
- `PaymentStatus`
- `OrderDomainService`

## Related documents

- [backend-folder-structure.md](./backend-folder-structure.md)
- [dto-handling-rules.md](./dto-handling-rules.md)
- [service-layer-rules.md](./service-layer-rules.md)
- [repository-rules.md](./repository-rules.md)
