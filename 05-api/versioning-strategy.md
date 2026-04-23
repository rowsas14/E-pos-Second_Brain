<!--
meta:
  title: API Versioning Strategy
  owner: Engineering / API
  status: active
  last_reviewed: 2026-04-22
  tags: [api, versioning, contracts, breaking-changes]
-->

# API Versioning Strategy

## Purpose

This file defines the API versioning approach for the platform.

For this project, use **path-based versioning**.

Examples:

- `/api/v1/products`
- `/api/v1/orders`
- `/api/v1/payments`
- `/api/v1/returns`

## Why path-based versioning fits this project

This platform has:

- multiple client types
- transaction-sensitive APIs
- long-lived admin and operational workflows
- a growing module set across POS, e-commerce, payments, returns, inventory, and configuration

Path-based versioning keeps contracts explicit and easy for frontend and support teams to reason about.

## Current strategy

Use `/api/v1/...` as the default versioned route format for current APIs.

Examples:

- `GET /api/v1/products`
- `POST /api/v1/orders`
- `POST /api/v1/payments`
- `POST /api/v1/returns`

## When versioning matters

Versioning becomes materially important when a change is **breaking** for an existing client contract.

## Breaking vs non-breaking changes

### Breaking changes

Examples of breaking changes include:

- removing a field relied on by clients
- renaming a field without compatibility handling
- changing field meaning in a way that breaks frontend assumptions
- changing route shape in a non-compatible way
- changing required request data for an existing endpoint
- changing error or list response structure in a client-breaking way

### Non-breaking changes

Examples of non-breaking changes include:

- adding optional response fields
- adding optional filters
- adding new endpoints
- improving internal processing without changing the external contract

## Module change handling

Module-level API docs in [../08-modules/](../08-modules/) should document feature-specific contract changes.

When a contract change is breaking:

1. evaluate whether it needs a new version path
2. update the relevant module `api.md`
3. update shared API docs if the change affects shared standards
4. update [api-change-checklist.md](./api-change-checklist.md)
5. update broader history or ADRs when required

## Version example pattern

```text
/api/v1/products
/api/v1/orders
/api/v2/orders
```

Use a new major path version only when compatibility requires it.  
Do not create new versions for every minor internal change.

## Documentation requirement

Any versioned change must be reflected in:

- the feature `api.md`
- this shared versioning file if the rule changed
- [api-change-checklist.md](./api-change-checklist.md)
- related frontend or backend docs if client impact exists

## Scope boundary

This file defines the versioning approach.  
It does not define public release programs, external partner lifecycle policy, or unsupported distribution models.

## Related documents

- [endpoint-design-rules.md](./endpoint-design-rules.md)
- [request-response-standard.md](./request-response-standard.md)
- [api-change-checklist.md](./api-change-checklist.md)
- [../02-architecture/backend-architecture.md](../02-architecture/backend-architecture.md)
- [../19-project-history/breaking-changes.md](../19-project-history/breaking-changes.md)
