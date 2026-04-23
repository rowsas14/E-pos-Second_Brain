<!--
meta:
  title: Request and Response Standard
  owner: Engineering / API
  status: active
  last_reviewed: 2026-04-22
  tags: [api, request-response, dto, contracts, frontend-integration]
-->

# Request and Response Standard

## Purpose

This file defines the request and response consistency rules for APIs in this platform.

The goal is to keep contract behavior predictable for React frontends and aligned with the backend direction that uses:

- request models
- response models
- DTOs
- shared response wrappers

Related backend direction:

- [../02-architecture/backend-architecture.md](../02-architecture/backend-architecture.md)
- [../07-backend/dto-handle-rules.md](../07-backend/dto-handle-rules.md)

## Contract design principles

API contracts should be:

- clear to the caller
- stable across modules
- explicit about validation and business failures
- suitable for POS, admin, and e-commerce UI consumption
- separate from internal persistence models

Do not expose raw domain or database structures directly as API contracts.

## Request rules

### Use explicit request models

Write operations should use explicit request models instead of loosely typed payloads.

Examples of route style:

- `POST /api/v1/products`
- `POST /api/v1/orders`
- `POST /api/v1/payments`
- `POST /api/v1/returns`

### Keep request payloads purpose-specific

A request model should represent the intention of the endpoint, not every possible field of the underlying entity.

### Avoid overloaded write endpoints

Do not use one large request model to cover unrelated actions such as create, approve, refund, cancel, and configure.

Prefer action-specific contract separation where the workflow differs.

## Response rules

Use consistent success structures across modules.

At minimum, clients should be able to predict:

- whether the request succeeded
- what data object or list is returned
- whether a user-facing message is present when useful

A simple wrapper style is acceptable where the backend direction already supports shared API response handling.

Example shape:

```json
{
  "success": true,
  "message": "Product created successfully.",
  "data": {
    "id": "uuid-value"
  }
}
```

### Single-resource responses

Return a focused resource contract or operation result, not unrelated extra payload.

### List responses

List endpoints should return predictable collection shapes.

Example shape:

```json
{
  "success": true,
  "data": {
    "items": [],
    "page": 1,
    "pageSize": 20,
    "totalCount": 0
  }
}
```

See [pagination-filtering-sorting.md](./pagination-filtering-sorting.md).

## Validation response expectations

Validation failures should return structured information that the frontend can map to fields or workflow steps.

Example shape:

```json
{
  "success": false,
  "error": {
    "code": "validation_failed",
    "message": "One or more validation errors occurred.",
    "details": [
      { "field": "sku", "message": "SKU is required." }
    ]
  }
}
```

The exact shape may be implemented through shared response wrappers and middleware, but the client-visible structure should remain stable.

## Business failure responses

Business rule failures are not the same as technical validation failures.

Examples:

- exchange cannot complete because difference collection is incomplete
- till session is not open
- return quantity exceeds original sale quantity
- feature is not available in this tenant context

These should use the shared error contract rather than silently returning success with warning text.

See [error-contract.md](./error-contract.md).

## DTO separation rules

DTOs should sit between API contracts and deeper layers.

| Concern | Preferred contract type |
|---|---|
| inbound API payload | request model |
| application transfer shape | DTO |
| outbound API payload | response model or wrapped response DTO |

Do not let EF entities or persistence-oriented models become your API contract.

## Consistency rules for React clients

Because this project uses React with TypeScript, response predictability matters.

The frontend should not need custom parsing rules for each module for basic concerns such as:

- success detection
- error extraction
- list pagination
- validation detail mapping

## Optional vs required fields

Request and response models should distinguish clearly between required values, optional values, and intentionally omitted values. Do not rely on ambiguous payload interpretation for business-critical writes.

## Document-specific ownership

Shared request/response rules belong here. Feature-specific examples and fields belong in the relevant feature `api.md` file under [../08-modules/](../08-modules/).

## Related documents

- [api-overview.md](./api-overview.md)
- [error-contract.md](./error-contract.md)
- [pagination-filtering-sorting.md](./pagination-filtering-sorting.md)
- [../02-architecture/backend-architecture.md](../02-architecture/backend-architecture.md)
- [../07-backend/service-layer-rules.md](../07-backend/service-layer-rules.md)
