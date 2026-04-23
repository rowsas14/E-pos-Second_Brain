<!--
meta:
  title: API Overview
  owner: Engineering / API
  status: active
  last_reviewed: 2026-04-22
  tags: [api, overview, platform, tenants]
-->

# API Overview

## Purpose

The API layer is the contract boundary between the platform’s clients and its backend application logic.

For this project, the API exists to serve one unified platform that supports:

- POS user interfaces for cashier and store operations
- tenant admin and operational back-office interfaces
- e-commerce customer-facing interfaces
- platform administration functions
- future system integrations only where the product direction eventually requires them

## What the API serves in this platform

| Client area | API purpose |
|---|---|
| POS frontend | fast product lookup, billing, till/session work, payment submission, returns, exchanges, receipt-related actions |
| Admin frontend | catalog, inventory, users, roles, outlets, settings, pricing, reports, approvals |
| E-commerce frontend | customer account, catalog browsing, cart, checkout, orders, reviews |
| Platform admin area | tenant onboarding, tenant lifecycle control, platform-governed capability assignment |

## What this file does not cover

This file stays high-level.

It does not define:

- exact request/response payloads — see [request-response-standard.md](./request-response-standard.md)
- detailed route design — see [endpoint-design-rules.md](./endpoint-design-rules.md)
- error payload rules — see [error-contract.md](./error-contract.md)
- auth and authorization details — see [auth-and-authorization.md](./auth-and-authorization.md)

## API role in the platform

```text
Frontend clients
  -> HTTP API
  -> Application layer
  -> Domain rules
  -> Persistence / external integrations
```

The API must expose platform behavior without breaking these core project rules:

- staff users are tenant-bound
- customers are tenant-specific
- platform admin is separate from tenant staff
- sellable flows operate at variant level
- returns and exchanges are separate business documents
- payment-sensitive operations must be safe against duplicate processing
- inventory-sensitive operations must respect stock and document boundaries
- feature access is assignable by platform admin and configurable within the tenant

## How API rules connect to platform concerns

### Tenant isolation

APIs must never behave like a global shared-store application.  
A request must operate inside the correct platform or tenant context and must not cross tenant boundaries accidentally.

Related docs:

- [auth-and-authorization.md](./auth-and-authorization.md)
- [../04-data/tenant-consistency-rules.md](../04-data/tenant-consistency-rules.md)
- [../02-architecture/multi-tenancy-model.md](../02-architecture/multi-tenancy-model.md)

### Permission-sensitive operations

Sensitive operations such as discount approval, refund handling, stock adjustments, and configuration changes require more than basic authentication.  
The API must enforce the correct access checks before the request reaches business execution.

Related docs:

- [auth-and-authorization.md](./auth-and-authorization.md)
- [../02-architecture/role-permission-capability-model.md](../02-architecture/role-permission-capability-model.md)

### Transaction-sensitive operations

Payment capture, refund handling, exchange-difference collection, till/session transitions, and stock-sensitive updates require safe write behavior.

Related docs:

- [idempotency-rules.md](./idempotency-rules.md)
- [concurrency-rules.md](./concurrency-rules.md)
- [error-contract.md](./error-contract.md)

### Configuration-sensitive behavior

APIs for features, permissions, themes, flags, and tenant settings must respect platform-governed capability assignment and tenant-side configuration boundaries.

Related docs:

- [../11-config-and-customization/README.md](../11-config-and-customization/README.md)
- [../08-modules/settings-configuration/](../08-modules/settings-configuration/)
- [auth-and-authorization.md](./auth-and-authorization.md)

## Shared API rules vs module API docs

| Type | Where it belongs |
|---|---|
| shared route naming rules | this folder |
| shared response rules | this folder |
| shared error model | this folder |
| one feature’s endpoints and payload intent | relevant module feature `api.md` |
| one feature’s business rules | relevant feature `business-rules.md` |
| one feature’s validations | relevant feature `validations.md` |

## Design expectations

The API should be:

- tenant-aware
- permission-aware
- module-consistent
- predictable for React clients
- safe for retry-prone financial operations
- clear for support and debugging without leaking internals
- aligned with the backend’s Clean Architecture direction

## Related documents

- [README.md](./README.md)
- [auth-and-authorization.md](./auth-and-authorization.md)
- [endpoint-design-rules.md](./endpoint-design-rules.md)
- [request-response-standard.md](./request-response-standard.md)
- [error-contract.md](./error-contract.md)
- [../02-architecture/backend-architecture.md](../02-architecture/backend-architecture.md)
- [../08-modules/README.md](../08-modules/README.md)
