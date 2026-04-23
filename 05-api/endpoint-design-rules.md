<!--
meta:
  title: Endpoint Design Rules
  owner: Engineering / API
  status: active
  last_reviewed: 2026-04-22
  tags: [api, endpoints, routes, versioning, design]
-->

# Endpoint Design Rules

## Purpose

This file defines how routes and endpoints should be designed across the platform.

The goal is to keep APIs consistent across POS, e-commerce, admin, payments, inventory, returns, and configuration areas without inventing arbitrary route styles per module.

## Versioned base path

Use path-based versioning for versioned API routes.

Examples:

- `/api/v1/products`
- `/api/v1/orders`
- `/api/v1/payments`
- `/api/v1/returns`

See [versioning-strategy.md](./versioning-strategy.md).

## Route design principles

- use resource-oriented routes by default
- use action endpoints when the action represents a distinct workflow step
- keep naming predictable and plural where the resource is a collection
- avoid exposing backend layer names in routes
- align route ownership with module boundaries

## Resource-oriented route examples

Examples of route style:

- `GET /api/v1/products`
- `GET /api/v1/products/{productId}`
- `POST /api/v1/products`
- `PUT /api/v1/products/{productId}`
- `GET /api/v1/orders/{orderId}`
- `GET /api/v1/payments/{paymentId}`
- `GET /api/v1/returns/{returnId}`

These examples show route style, not a promise of the full endpoint inventory.

## Action endpoints

Use action-oriented endpoints only when the operation is not well represented as simple CRUD and the workflow matters.

Examples of justified action style:

- `POST /api/v1/till-sessions/{sessionId}/close`
- `POST /api/v1/discount-requests/{requestId}/approve`
- `POST /api/v1/returns/{returnId}/refund`
- `POST /api/v1/exchanges/{exchangeId}/collect-difference`

These are better than forcing everything through generic update payloads.

## Nested routes

Use nested routes only when the relationship is part of the request identity and helps clarity.

Acceptable examples:

- `GET /api/v1/orders/{orderId}/items`
- `GET /api/v1/products/{productId}/variants`
- `GET /api/v1/tenants/{tenantId}/outlets` for platform-side context if such route ownership is appropriate

Avoid unnecessary deep nesting that duplicates filterable parent context.

## Tenant-sensitive route rules

Do not encode tenant identity into routes unless the route is truly platform-admin driven and operates on tenants as first-class resources.

For normal tenant staff or customer operations, tenant context should usually come from authenticated scope and validated request context rather than route duplication.

## POS-sensitive endpoint rules

POS flows prioritize fast, operationally clear endpoints.

That means endpoints for scan/search, sale completion, till/session actions, payment submission, and return/exchange work should reflect real cashier workflows rather than generic admin CRUD naming.

## Naming rules

- use lowercase path segments
- use hyphen-separated action words when needed
- avoid verbs in base collection routes
- keep route names aligned with business terms already used in the project

Preferred examples:

- `/api/v1/stocktakes`
- `/api/v1/stock-transfers`
- `/api/v1/discount-requests`
- `/api/v1/feature-flags`

## Avoid these route mistakes

- route names based on controller class names only
- route names based on database table names that do not match business language
- mixing singular and plural naming randomly
- exposing internal workflow hacks as public route shape
- using one generic `/save` or `/execute` route for unrelated actions

## Route ownership and module docs

Shared route design rules belong here.  
Actual route inventory, request meaning, and per-feature notes belong in feature `api.md` files under [../08-modules/](../08-modules/).

## Related documents

- [api-overview.md](./api-overview.md)
- [request-response-standard.md](./request-response-standard.md)
- [versioning-strategy.md](./versioning-strategy.md)
- [auth-and-authorization.md](./auth-and-authorization.md)
- [../02-architecture/backend-architecture.md](../02-architecture/backend-architecture.md)
- [../08-modules/README.md](../08-modules/README.md)
