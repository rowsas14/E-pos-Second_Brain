<!--
meta:
  title: Backend Overview
  owner: Backend Engineering
  status: active
  last_reviewed: 2026-04-22
  tags: [backend, overview, clean-architecture, unified-commerce]
-->

# Backend Overview

## Purpose

This file explains the overall backend role in the Unified Commerce Platform.

The backend is responsible for turning the platform’s business model into enforceable, tenant-safe, transaction-aware behavior for both **POS** and **E-Commerce**.

## Backend direction

The approved backend direction is:

- **.NET Web API**
- **Clean Architecture**
- **feature/module-based organization**
- **PostgreSQL with EF Core**
- explicit support for interfaces where contracts matter
- explicit support for **Unit of Work** where transaction coordination matters

This backend is not a generic CRUD API.

It must support:

- tenant-aware access and data ownership
- cashier-sensitive POS workflows
- online order flows
- payments and allocations
- inventory movement and reservation logic
- returns and exchanges as separate business documents
- tenant-scoped configuration and feature behavior

## What the backend serves

| Consumer | Backend responsibility |
|---|---|
| POS frontend | fast product lookup, cart/sale workflows, till/session handling, payments, returns, exchanges, receipts |
| admin/frontend | tenant setup, roles/permissions, catalog, pricing, inventory, reporting, configuration |
| e-commerce frontend | catalog, cart, checkout, customer account, order handling, fulfillment-ready flows |
| platform administration | tenant onboarding, activation, oversight, capability assignment |

## Backend responsibilities in this platform

### 1. Protect tenant boundaries

The backend must enforce that:

- platform admin behavior is separated from tenant staff behavior
- staff users operate only within their tenant
- customer records remain tenant-specific
- role assignments stay within the same tenant
- configuration is applied inside allowed tenant, outlet, user, or channel scope

### 2. Enforce business-sensitive workflows

The backend must support workflows that are not simple row updates, including:

- POS checkout
- payment capture and allocation
- stock movement creation and balance updates
- order status progression
- refunds
- returns
- exchanges
- till session open / close behavior

### 3. Keep shared foundations consistent

The same backend foundation supports both POS and E-Commerce through shared rules for:

- catalog
- variants
- pricing
- customers
- inventory
- payments
- receipts
- reporting inputs
- configuration and auditability

## Layer view

```text
API            -> controllers, request models, response models, middleware
Application    -> use-case orchestration, interfaces, DTOs, validators
Domain         -> business entities, aggregates, value objects, domain rules
Infrastructure -> EF Core, repositories, integrations, Unit of Work implementations
```

Use detailed rules from:

- [clean-architecture-rules.md](./clean-architecture-rules.md)
- [application-layer-rules.md](./application-layer-rules.md)
- [domain-layer-rules.md](./domain-layer-rules.md)
- [infrastructure-layer-rules.md](./infrastructure-layer-rules.md)

## How backend aligns with core platform areas

| Area | Backend expectation |
|---|---|
| tenant and platform separation | separate access paths, checks, and data boundaries |
| permissions and capability model | permission-sensitive and feature-capability-aware orchestration |
| POS | low-latency operational APIs and reliable workflow execution |
| inventory | authoritative movement logic and consistent projection updates |
| payments | safe state changes, allocation rules, retry-safe handling |
| returns / exchanges | explicit reverse-flow behavior, not hidden inside sales logic |
| reporting | write model correctness so downstream reporting is reliable |
| tenant configuration | scoped settings, flags, and themes enforced by backend rules |

## What this file does not cover

This file stays high-level.

Use these for detail:

- structure and placement: [backend-folder-structure.md](./backend-folder-structure.md)
- application use-case rules: [application-layer-rules.md](./application-layer-rules.md)
- DTO rules: [dto-handling-rules.md](./dto-handling-rules.md)
- transactions: [transaction-handling-rules.md](./transaction-handling-rules.md)

## Related documents

- [backend-folder-structure.md](./backend-folder-structure.md)
- [clean-architecture-rules.md](./clean-architecture-rules.md)
- [transaction-handling-rules.md](./transaction-handling-rules.md)
- [../02-architecture/system-overview.md](../02-architecture/system-overview.md)
- [../04-data/database-overview.md](../04-data/database-overview.md)
- [../05-api/api-overview.md](../05-api/api-overview.md)
