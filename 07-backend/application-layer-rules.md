<!--
meta:
  title: Application Layer Rules
  owner: Backend Engineering
  status: active
  last_reviewed: 2026-04-23
  tags: [application-layer, services, validators, dto, orchestration]
-->

# Application Layer Rules

## Purpose

This file explains what belongs in the Application layer for this project.

The Application layer is the orchestration layer for backend use cases. It coordinates module workflows while preserving domain rules, tenant safety, access safety, and transaction boundaries.

## What belongs here

The Application layer should own:

- use-case orchestration
- service interfaces and service implementations for use cases
- repository contracts where needed
- Unit of Work contract
- action-specific DTOs
- validators
- coordination across repositories or modules
- permission- or capability-aware workflow checks before execution continues

## Typical contents

| Item | Example |
|---|---|
| application service | `ProductService.cs` |
| service interface | `IProductService.cs` |
| action DTO | `CreateProductDto.cs`, `UpdateProductDto.cs` |
| response DTO | `ProductResponseDto.cs`, `ProductListDto.cs` |
| validator | `ProductValidator.cs` |
| common contract | `IUnitOfWork.cs` |

## Application services

Application services should represent use cases or grouped workflow responsibilities.

Examples of acceptable responsibility:

- create or update product workflows
- checkout orchestration
- payment capture orchestration
- return initiation workflow
- exchange completion workflow
- tenant onboarding coordination

### Application services should do

- call repositories through interfaces
- coordinate multiple steps
- invoke domain behavior
- validate workflow preconditions
- use Unit of Work boundaries when required
- map DTOs to domain input forms and domain results back to DTOs
- resolve effective access before executing sensitive actions

### Application services should not become

- generic god services for an entire module
- controller substitutes
- persistence implementations
- dumping grounds for unrelated business rules

## DTO contract rule

Application DTOs must be **use-case specific** where needed.

Prefer:

- `CreateProductDto`
- `UpdateProductDto`
- `ProductResponseDto`
- `ProductListDto`

Avoid one oversized DTO that tries to serve create, update, list, and detail at the same time.

## Validator rule

Application validators should validate:

- shape and required field expectations not already handled at API model-binding level
- use-case preconditions
- business input consistency
- tenant or outlet scope assumptions when the use case depends on them

## Effective access rule

Application services must not treat a seeded or default role mapping as the final access decision.

When a feature supports default role mapping plus later override, Application logic should validate the **current effective access state**, including:

- current identity type
- current role scope
- current permission grant
- current platform-assigned capability
- current tenant-side configuration that affects feature behavior
- current tenant and outlet boundary

### Practical expectation

If a feature was originally seeded to `manager` but later reassigned to `supervisor`, the Application layer must honor the current mapping and must not continue to behave as if `manager` is still the automatic owner.

## Cross-module coordination

This platform has workflows that span more than one module, such as:

- payment + sale
- return + refund
- exchange + inventory + payment difference
- order + reservation + fulfillment progress

Application layer is the correct place to coordinate these flows.

## Related documents

- [clean-architecture-rules.md](./clean-architecture-rules.md)
- [service-layer-rules.md](./service-layer-rules.md)
- [dto-handling-rules.md](./dto-handling-rules.md)
- [mapping-rules.md](./mapping-rules.md)
- [validation-rules.md](./validation-rules.md)
- [transaction-handling-rules.md](./transaction-handling-rules.md)
- [../05-api/auth-and-authorization.md](../05-api/auth-and-authorization.md)
- [../02-architecture/role-permission-capability-model.md](../02-architecture/role-permission-capability-model.md)
