<!--
meta:
  title: System Overview
  owner: Architecture / Engineering
  status: active
  last_reviewed: 2026-04-23
  tags: [architecture, system-overview, unified-commerce, platform]
-->

# System Overview

## Purpose

This document explains the overall system structure of the Unified Commerce Platform at a practical level.

It connects the product intent, architecture direction, data model direction, and implementation-facing documentation so the platform can be understood as **one system**, not as disconnected POS, admin, and E-Commerce parts.

## What the system is

The project is a **multi-tenant unified commerce platform** that combines:

- **E-POS** for in-store retail operation
- **E-Commerce** for online selling
- **shared foundations** for catalog, pricing, tax, stock, customer, payment, returns, exchanges, reporting, and configuration

This is not a POS attached to a storefront later. It is one platform with shared operational foundations and separate channel-specific workflows.

## Core operating model

### 1. Platform governance

The platform includes a platform-side administration layer that is separate from tenant staff operation.

Platform-side responsibilities include:

- tenant onboarding
- tenant lifecycle control
- platform-level support and governance
- feature capability assignment into the tenant-facing model

### 2. Tenant operation

Each tenant runs inside its own business boundary.

That tenant boundary applies to:

- staff users
- customers and memberships
- products, variants, pricing, and tax setup
- inventory and stock movement
- POS and E-Commerce operation
- payments and reverse-flow operation
- tenant-scoped configuration
- reporting and audit visibility

### 3. Shared commerce foundations

Both channels depend on shared foundations, not isolated duplicates.

| Shared foundation | Why it matters |
|---|---|
| Catalog and variants | sellable flows operate at variant level across channels |
| Pricing | supports channel-aware and outlet-aware selling behavior |
| Inventory | supports stock visibility, reservations, transfers, and movement history |
| Customer | keeps customer records tenant-specific while supporting both channels |
| Payments | supports sale, order, refund, and exchange-difference money flows |
| Returns and exchanges | keeps reverse-flow logic explicit and auditable |
| Reporting | supports outlet-wise and channel-wise visibility |
| Configuration | allows tenant-owned themes, settings, and feature behavior |

### 4. Channel execution

The platform supports two main execution environments.

#### POS

POS is optimized for:

- touchscreen-first use
- barcode-first and scan/search-driven product entry
- low typing
- fast cashier action
- visible totals and clear payment flow
- till and session control
- hold/recall, discount, payment, receipt, return, and exchange behavior

#### E-Commerce

E-Commerce supports:

- product listing and detail views
- cart and checkout
- customer account handling
- order status and fulfillment progress
- reservations and fulfillment readiness

## Feature access inside the system

Feature access is not modeled as one fixed hard-coded role list.

The system supports:

- optional default role mappings for some features
- platform-admin capability assignment
- tenant-side configuration after approval

### Important rule

A default role mapping is only a starter mapping when it exists.

Final runtime feature access is determined by the current platform-admin assignment, current role/permission model, current scope rules, and tenant-side configuration.

For the detailed model, see [role-permission-capability-model.md](./role-permission-capability-model.md).

## System areas represented in the documentation

The platform areas reflected in the 2nd Brain are consistent with the project’s schema and module structure.

| Area | Primary documentation home |
|---|---|
| Product intent | [../01-product/](../01-product/README.md) |
| Architecture and operating models | [./README.md](./README.md) |
| Decisions | [../03-decisions/](../03-decisions/ADR-index.md) |
| Data and schema rules | [../04-data/](../04-data/README.md) |
| API standards | [../05-api/](../05-api/README.md) |
| Frontend standards | [../06-frontend/](../06-frontend/README.md) |
| Backend standards | [../07-backend/](../07-backend/README.md) |
| Feature documentation | [../08-modules/README.md](../08-modules/README.md) |

## Relationship between documentation layers

```text
01-product
  -> defines business intent and scope
02-architecture
  -> defines operating and system structure
03-decisions
  -> records major design commitments
04-data
  -> defines schema and data-governance direction
05/06/07
  -> define API, frontend, and backend standards
08-modules
  -> define feature-level documentation
```

That relationship matters because implementation should follow product intent, architecture boundaries, and data rules instead of inventing a local solution inside one module.

## Practical platform composition

The platform should be read as one system made of connected areas:

- **platform admin** governs tenant lifecycle and capability assignment
- **tenant administration** manages business operation inside the tenant boundary
- **identity and access** controls who can act and at what scope
- **catalog, pricing, and tax** control what can be sold and under what pricing/tax context
- **inventory** controls stock position and stock movement history
- **POS and E-Commerce** execute channel-specific selling flows on shared foundations
- **payments** control inbound and outbound money movement
- **returns and exchanges** handle controlled reverse-flow documents
- **reporting and audit** support operational visibility and traceability
- **settings, themes, and feature configuration** allow customer-specific operation without breaking platform governance

## Related documents

- [multi-tenancy-model.md](./multi-tenancy-model.md)
- [multi-tenant-architecture.md](./multi-tenant-architecture.md)
- [role-permission-capability-model.md](./role-permission-capability-model.md)
- [../01-product/README.md](../01-product/README.md)
- [../04-data/database-overview.md](../04-data/database-overview.md)
- [../08-modules/README.md](../08-modules/README.md)
