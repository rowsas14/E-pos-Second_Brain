<!--
meta:
  title: Multi-Tenant Architecture
  owner: Architecture / Engineering
  status: active
  last_reviewed: 2026-04-22
  tags: [architecture, multitenant-architecture, tenant-enforcement, implementation]
-->

# Multi-Tenant Architecture

## Purpose

This document explains the **technical architecture direction** used to implement multitenancy in the Unified Commerce Platform.

It focuses on tenant-aware data design, enforcement direction, same-tenant validation, access-control scoping, and tenant-owned configuration mechanics.

For the operating meaning of tenancy, see [multi-tenancy-model.md](./multi-tenancy-model.md).

## Technical architecture intent

The platform must support multiple tenants through one shared system while enforcing correct ownership and preventing cross-tenant leakage.

The source documents already establish these rules:

- platform admin is separate from tenant users
- staff users are tenant-bound
- customers are tenant-specific
- operational transactions belong to exactly one tenant
- configuration is scoped by tenant, outlet, user, or channel where applicable

The technical architecture must therefore make tenant context explicit and enforceable across data, services, APIs, and UI behavior.

## Core implementation direction

### 1. Separate platform administration from tenant users

Platform-side administration must be represented separately from tenant-bound staff users.

This separation reduces accidental mixing of platform governance and tenant operation, and it gives tenant onboarding and platform control a distinct identity path.

### 2. Use tenant-aware data design

Most operational and business-owned tables carry `tenant_id` because tenant ownership is not implied; it must be explicit.

That includes tenant-owned areas such as:

- users and roles
- outlets
- catalog and pricing
- inventory balances and stock movements
- customers and memberships
- sales, orders, returns, exchanges, payments, refunds, receipts
- feature flags, themes, and tenant settings

### 3. Enforce same-tenant validation

Repeating `tenant_id` is useful only when the database and application also enforce consistency.

The architecture direction already supports:

- composite foreign keys where practical
- check constraints for simple enumerated rules
- service-layer validation for cross-table tenant consistency and business rules

This is especially important when records reference users, outlets, roles, customers, products, or documents across multiple tables.

## Tenant-aware access design

Access-control data is tenant-aware by design.

| Element | Technical expectation |
|---|---|
| users | tenant-bound staff identities |
| roles | tenant-owned roles with tenant or outlet scope |
| tenant_user_roles | role assignment inside one tenant |
| outlet_user_roles | outlet-specific assignment inside one tenant |
| permissions | system-defined permission definitions |
| feature capability assignment | platform-governed mapping into tenant-facing access model |

This means access control is not only a UI concern and not only a database concern. It must be enforced consistently across the stack.

## Configuration scope concepts

The architecture supports tenant-owned configuration with scoped application.

Main scope concepts already present in the source material:

- **tenant scope**
- **outlet scope**
- **user scope** for feature flags where relevant
- **channel scope** for settings where relevant

Examples of tenant-owned configuration structures already supported by the project direction:

- `feature_flags`
- `ui_themes`
- `tenant_settings`

These structures allow per-tenant behavior without hard-coding configuration per customer in source code.

## Data-level enforcement expectations

The multi-tenant architecture depends on strict ownership enforcement.

Expected enforcement patterns:

- child records must belong to the same tenant as their parent business context
- role, user, outlet, and assignment records must agree on tenant ownership
- customer auth records must stay aligned to the tenant of the customer
- pricing, inventory, order, sale, return, exchange, and payment records must preserve tenant document ownership
- audit logs and sensitive actions must remain attributable inside the tenant boundary when tenant actors are involved

For schema ownership and consistency rules, see [../04-data/tenant-consistency-rules.md](../04-data/tenant-consistency-rules.md).

## API and service expectations

APIs and backend services must not treat tenant ownership as optional filtering.

Tenant context must influence:

- query scope
- mutation permission checks
- same-tenant relationship validation
- configuration resolution
- reporting visibility
- audit and sensitive action logging

This is especially important for areas such as payments, refunds, stock movements, returns, exchanges, and role assignment.

## Frontend expectations

Frontend architecture must reflect tenant-aware behavior rather than acting like a generic public website.

Frontend enforcement expectations include:

- render only allowed features and actions
- resolve theme and tenant-specific UI behavior correctly
- respect outlet-specific and tenant-specific role assignments
- distinguish between platform-level and tenant-level user experiences
- surface only tenant-owned data in admin, POS, and customer contexts

For frontend structure direction, see [frontend-architecture.md](./frontend-architecture.md).

## Relationship to module design

Multitenancy is not one isolated module.

It affects almost every platform area, especially:

- `platform-administration`
- `tenant-management`
- `identity-access`
- `settings-configuration`
- `sales-pos`
- `orders-ecommerce`
- `payments`
- `returns-exchanges`
- `reporting`

That is why tenant rules should be defined centrally and then reflected by module-level documentation instead of being reinvented per feature.

## What this file does not cover

This file does not redefine the business meaning of a tenant or the product reasons for multitenancy.

Read these files for that:

- [multi-tenancy-model.md](./multi-tenancy-model.md)
- [../01-product/business-goal.md](../01-product/business-goal.md)
- [../01-product/business-objectives.md](../01-product/business-objectives.md)

## Related documents

- [multi-tenancy-model.md](./multi-tenancy-model.md)
- [role-permission-capability-model.md](./role-permission-capability-model.md)
- [../04-data/tenant-consistency-rules.md](../04-data/tenant-consistency-rules.md)
- [../04-data/schema-principles.md](../04-data/schema-principles.md)
- [../05-api/auth-and-authorization.md](../05-api/auth-and-authorization.md)
- [../07-backend/transaction-handling-rules.md](../07-backend/transaction-handling-rules.md)
