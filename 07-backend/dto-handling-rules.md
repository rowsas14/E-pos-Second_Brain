<!--
meta:
  title: DTO Handling Rules
  owner: Backend Engineering
  status: active
  last_reviewed: 2026-04-22
  tags: [dto, contracts, application-layer, backend]
-->

# DTO Handling Rules

## Purpose

This file defines DTO usage rules for the backend.

The backend direction already separates:

- API request models
- API response models
- Application DTOs

This separation must stay intentional.

## DTO rule

Use DTOs as **use-case specific contracts** where appropriate.

Prefer explicit DTOs such as:

- `CreateProductDto.cs`
- `UpdateProductDto.cs`
- `ProductResponseDto.cs`
- `ProductListDto.cs`

These are clearer than a single oversized `ProductDto` that tries to cover every operation.

## Why separate DTOs

Create, update, response, and list shapes often differ in this platform because:

- creation may require validation-only fields
- update may allow partial or scoped changes
- list shape may be lighter for POS/admin grids
- response shape may include calculated or resolved data not accepted on input

## DTO placement

Recommended placement:

- API `Requests/` and `Responses/` for HTTP-facing models
- Application module area for DTOs used by use-case orchestration

Example:

```text
POS.API/Modules/Products/Requests/CreateProductRequest.cs
POS.Application/Modules/Products/CreateProductDto.cs
POS.Application/Modules/Products/ProductResponseDto.cs
POS.API/Modules/Products/Responses/ProductResponse.cs
```

## What belongs in DTOs

DTOs may contain:

- data needed for one use case
- transport-safe fields
- explicitly shaped response data
- list-friendly or detail-friendly fields depending on use case

## What must not be placed in DTOs

Do not put these into DTOs as owners:

- domain behavior
- repository logic
- EF Core entities
- HTTP context access
- permission decision logic

## API models vs Application DTOs

### API request/response models

Use these to shape HTTP contracts.

Examples:
- `CreateProductRequest`
- `ProductResponse`

### Application DTOs

Use these for the application workflow contract.

Examples:
- `CreateProductDto`
- `UpdateProductDto`
- `ProductResponseDto`
- `ProductListDto`

## Naming rule

Keep naming explicit and action-aware.

Good:
- `CreateProductDto`
- `UpdateProductDto`
- `ProductResponseDto`
- `ProductListDto`

Avoid:
- `ProductDto` for every operation
- `BaseProductDto` unless it has a real, justified contract purpose

## Related documents

- [application-layer-rules.md](./application-layer-rules.md)
- [mapping-rules.md](./mapping-rules.md)
- [naming-conventions.md](./naming-conventions.md)
- [../05-api/request-response-standard.md](../05-api/request-response-standard.md)
