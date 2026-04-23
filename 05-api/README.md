<!--
meta:
  title: API Documentation Overview
  owner: Engineering / API
  status: active
  last_reviewed: 2026-04-22
  tags: [api, overview, navigation, unified-commerce]
-->

# API Documentation Overview

## Purpose

This folder contains the **shared API rules** for the Unified Commerce Platform.

The APIs in this project support a single multi-tenant platform that combines:

- touchscreen-first **E-POS**
- **E-Commerce** customer flows
- tenant administration and configuration
- platform-side administration
- shared operational foundations such as products, variants, stock, orders, payments, returns, exchanges, reporting, themes, and settings

This folder does **not** replace feature-level API documentation inside [../08-modules/](../08-modules/).  
This folder defines the common API rules that every module must follow.

## Why this section matters

In this system, API behavior cannot be documented feature by feature only.

Shared API documentation matters because the platform must keep these rules consistent across modules:

- tenant isolation
- separation of platform admin and tenant staff access
- tenant-bound staff authorization
- tenant-specific customer access
- variant-level sellable flows
- payment-sensitive operations
- inventory-sensitive operations
- return and exchange document flows
- configuration-sensitive behavior such as feature capabilities and tenant settings

Without shared rules, different modules will return different response shapes, expose inconsistent routes, or apply tenant and permission checks differently.

## What this folder covers

| File | Purpose |
|---|---|
| [api-overview.md](./api-overview.md) | explains the role of the API layer in the platform |
| [auth-and-authorization.md](./auth-and-authorization.md) | explains API authentication, authorization, tenant checks, and capability impact |
| [request-response-standard.md](./request-response-standard.md) | defines request and response consistency rules |
| [error-contract.md](./error-contract.md) | defines the API error model |
| [endpoint-design-rules.md](./endpoint-design-rules.md) | defines route and endpoint design rules |
| [pagination-filtering-sorting.md](./pagination-filtering-sorting.md) | defines list endpoint query behavior |
| [idempotency-rules.md](./idempotency-rules.md) | defines duplicate-safe behavior for retry-sensitive writes |
| [concurrency-rules.md](./concurrency-rules.md) | defines conflict handling expectations |
| [versioning-strategy.md](./versioning-strategy.md) | defines API versioning approach using path-based versioning |
| [api-change-checklist.md](./api-change-checklist.md) | practical checklist before shipping an API change |

## Read this section first when

Read this folder before changing or creating APIs for:

- POS checkout flows
- order flows
- payment, refund, or exchange-difference operations
- stock-sensitive endpoints
- return and exchange workflows
- tenant configuration endpoints
- permission-sensitive admin or staff operations
- customer-facing e-commerce APIs

## Recommended reading order by task

### For a new API

1. [api-overview.md](./api-overview.md)
2. [endpoint-design-rules.md](./endpoint-design-rules.md)
3. [request-response-standard.md](./request-response-standard.md)
4. [error-contract.md](./error-contract.md)
5. [auth-and-authorization.md](./auth-and-authorization.md)
6. [versioning-strategy.md](./versioning-strategy.md)

### For a payment or refund API

1. [api-overview.md](./api-overview.md)
2. [auth-and-authorization.md](./auth-and-authorization.md)
3. [idempotency-rules.md](./idempotency-rules.md)
4. [concurrency-rules.md](./concurrency-rules.md)
5. [error-contract.md](./error-contract.md)

### For a list/query endpoint

1. [endpoint-design-rules.md](./endpoint-design-rules.md)
2. [request-response-standard.md](./request-response-standard.md)
3. [pagination-filtering-sorting.md](./pagination-filtering-sorting.md)

### For an API change

1. [api-change-checklist.md](./api-change-checklist.md)
2. [versioning-strategy.md](./versioning-strategy.md)
3. [error-contract.md](./error-contract.md)
4. [auth-and-authorization.md](./auth-and-authorization.md)

## Connected documentation

This folder should be read together with:

- [../02-architecture/README.md](../02-architecture/README.md)
- [../02-architecture/system-overview.md](../02-architecture/system-overview.md)
- [../02-architecture/role-permission-capability-model.md](../02-architecture/role-permission-capability-model.md)
- [../04-data/README.md](../04-data/README.md)
- [../04-data/tenant-consistency-rules.md](../04-data/tenant-consistency-rules.md)
- [../07-backend/README.md](../07-backend/README.md)
- [../08-modules/README.md](../08-modules/README.md)

## Scope boundary

This folder owns **shared API rules**.  
Feature-specific endpoint details still belong under the relevant module and feature folder in [../08-modules/](../08-modules/).
