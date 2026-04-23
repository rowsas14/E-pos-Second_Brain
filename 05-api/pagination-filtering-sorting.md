<!--
meta:
  title: Pagination Filtering and Sorting
  owner: Engineering / API
  status: active
  last_reviewed: 2026-04-22
  tags: [api, pagination, filtering, sorting, list-endpoints]
-->

# Pagination Filtering and Sorting

## Purpose

This file defines list endpoint behavior for the platform.

These rules matter for tenant-scoped operational and admin APIs such as:

- products and variants
- customers
- orders
- returns and exchanges
- inventory history
- reporting lists
- audit-like operational lists where exposed through APIs

## Core rules

- large operational lists should support pagination
- filtering should follow consistent query parameter rules
- sorting should be explicit and predictable
- list endpoints must stay tenant-scoped and permission-aware
- response shape should be consistent for React clients

See [request-response-standard.md](./request-response-standard.md).

## Pagination model

Use explicit page-based pagination unless a feature’s API doc defines a justified alternative.

Preferred query style:

- `page`
- `pageSize`

Example:

`GET /api/v1/products?page=1&pageSize=20`

## List response shape

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

Keep this predictable across modules.

## Filtering rules

Use query parameters for filtering.

Examples by business area:

- `/api/v1/products?status=active&categoryId=...`
- `/api/v1/orders?orderStatus=placed&customerId=...`
- `/api/v1/returns?status=approved&returnOutletId=...`
- `/api/v1/stock-movements?variantId=...&movementType=reservation_hold`

Use business terms already present in the platform’s documentation and schema direction.

## Sorting rules

Use explicit sort fields and direction.

Example style:

- `sortBy=name&sortDirection=asc`
- `sortBy=createdAt&sortDirection=desc`

Avoid undocumented free-form sort expressions.

## Practical expectations by endpoint type

| Endpoint type | Expected behavior |
|---|---|
| product and catalog lists | support status, category, brand, channel-related filters where the feature supports them |
| order and return lists | support status, date, outlet, customer, and number-based search where appropriate |
| inventory movement lists | support outlet, variant, movement type, and date filters |
| reporting-like lists | support date range and scope filters appropriate to the report |

The exact filter inventory belongs in module-level `api.md`, not here.

## Default limits

This shared file does not fix one global numeric default.  
Module-level docs may define appropriate defaults based on workload and usage pattern.

What matters here is consistency of shape and parameter style.

## Tenant and permission impact

List APIs must not leak cross-tenant information.

Filtering and sorting rules must operate inside the caller’s valid scope only.

A caller should not be able to use a query parameter to escape tenant or outlet boundaries.

## Frontend considerations

Because the frontend uses React and TypeScript, list APIs should keep:

- stable query parameter names
- stable response wrappers
- predictable empty-list behavior
- consistent count metadata for pagination controls

## Related documents

- [request-response-standard.md](./request-response-standard.md)
- [endpoint-design-rules.md](./endpoint-design-rules.md)
- [auth-and-authorization.md](./auth-and-authorization.md)
- [../04-data/database-overview.md](../04-data/database-overview.md)
- [../08-modules/README.md](../08-modules/README.md)
