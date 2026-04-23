<!--
meta:
  title: Mapping Rules
  owner: Backend Engineering
  status: active
  last_reviewed: 2026-04-22
  tags: [mapping, request-to-dto, dto-to-domain, response-mapping, backend]
-->

# Mapping Rules

## Purpose

This file explains mapping rules between request models, DTOs, domain entities, and response models.

Mapping must stay clear so responsibilities do not blur across layers.

## Mapping path

Preferred flow:

```text
API Request Model
  -> Application DTO
  -> Domain Entity / Domain Input
  -> Domain Result / Persistence Result
  -> Application Response DTO
  -> API Response Model
```

Not every use case requires every step, but the direction should stay clear.

## Where mapping should happen

| Mapping step | Preferred location |
|---|---|
| request model -> application DTO | API or Application boundary |
| application DTO -> domain input/entity | Application service or dedicated mapper used by Application |
| domain -> response DTO | Application layer |
| response DTO -> API response model | API layer or boundary mapping |

## Allowed transformations

### Request model -> DTO

Allowed:
- field renaming for application clarity
- normalization needed for use-case input
- shaping transport input into use-case contract

### DTO -> Domain

Allowed:
- creating or updating domain objects through permitted flows
- translating simple transport values into domain values
- applying action-specific data into aggregate operations

### Domain -> Response DTO

Allowed:
- response shaping
- list/detail contract shaping
- flattening safe read values for clients

## Mapping rule for this project

Because this platform includes:

- tenant-sensitive behavior
- POS-sensitive read models
- payment and inventory-sensitive workflows
- separate return / exchange documents

mapping should stay explicit for important use cases rather than being hidden inside random constructors or controllers.

## Related documents

- [dto-handling-rules.md](./dto-handling-rules.md)
- [application-layer-rules.md](./application-layer-rules.md)
- [repository-rules.md](./repository-rules.md)
- [../05-api/request-response-standard.md](../05-api/request-response-standard.md)
- [../05-api/error-contract.md](../05-api/error-contract.md)
