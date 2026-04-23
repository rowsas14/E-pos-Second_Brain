<!--
meta:
  title: Multi-Tenancy Model
  owner: Architecture / Engineering
  status: active
  last_reviewed: 2026-04-23
  tags: [architecture, multitenancy, operating-model, tenant-isolation]
-->

# Multi-Tenancy Model

## Purpose

This document explains what **multitenancy means in this project** from an operating-model and system-behavior perspective.

It focuses on **meaning, ownership, and platform behavior**. For technical enforcement details, see [multi-tenant-architecture.md](./multi-tenant-architecture.md).

## What multitenancy means here

In this platform, multitenancy means the system serves multiple customer businesses through one platform while keeping each tenant’s operation, staff access, customer records, and business configuration isolated.

This is not only a database concept. It is the base operating model for the platform.

## Core tenancy rules

### 1. A tenant is the business boundary

Every operational transaction belongs to exactly one tenant.

That includes business documents such as sales, orders, returns, exchanges, payments, inventory records, receipts, settings, and audit history.

### 2. Platform admin is not a tenant staff user

Platform administration is separate from tenant operation.

Platform admin exists to:

- create tenants
- activate or suspend tenants
- support onboarding
- control feature capability assignment at platform level

Platform admin is not the same identity model as tenant staff.

### 3. Staff users are tenant-bound

A staff user belongs to exactly one tenant.

A staff user assigned to one tenant must not operate under another tenant through the same staff identity.

### 4. Customers are tenant-specific

Customers are not global platform customers.

The same email address may appear under different tenants as separate customer identities. Membership is also tenant-specific.

### 5. Configuration is tenant-owned inside platform rules

Tenants control their own business configuration within approved boundaries.

That includes tenant-scoped settings, themes, outlet-level configuration, channel-specific behavior, and approved feature behavior.

### 6. Capability assignment is platform-governed

Feature access is not a fixed hard-coded role list.

The platform must support a model where the platform administrator assigns feature capabilities into the tenant-facing role model, and the tenant then configures approved behavior within its own context.

## Default role mapping inside tenancy

Some features may have a default role mapping during onboarding or initial platform setup.

In this tenancy model, that default mapping means:

- a platform-approved starting assignment
- a convenience for setup
- a recommendation for the first operating model

It does **not** mean:

- the tenant can use the feature without platform capability assignment
- the tenant can treat the default role as a permanent entitlement
- the platform loses control over later reassignment
- the feature is no longer subject to tenant boundary, scope, or configuration checks

### Important boundary rule

A tenant cannot claim final access to a feature only because the feature once had a default role mapping.

Final feature access still depends on the current platform-governed assignment and the current tenant-side configuration within the tenant boundary.

## What tenancy affects in real operation

| Area | Tenancy effect |
|---|---|
| Staff access | staff identities, role assignments, and outlet assignments stay inside one tenant |
| Customers | customer identity and membership stay tenant-specific |
| Catalog and pricing | products, variants, brands, categories, pricing, and tax classes are tenant-owned |
| Inventory | balances, movements, reservations, and transfers stay inside tenant ownership |
| POS and E-Commerce | both channels operate under the same tenant business boundary |
| Payments and refunds | money movement records belong to the tenant context that produced them |
| Reporting | reports are scoped to the tenant, outlet, or channel inside the tenant |
| Configuration | settings, themes, and feature flags are tenant-owned or tenant-scoped |

## Customer-specific per-tenant operation

The platform is customer-specific per tenant.

That means the same software foundation can serve multiple tenants, but each tenant can run its own business configuration, outlet structure, pricing setup, theme, and approved feature behavior.

This does **not** mean a tenant can break platform governance. It means tenant-specific operation exists **inside** platform-approved architecture and capability boundaries.

## Role and scope meaning inside tenancy

The access model uses tenant and outlet scopes.

- **tenant-scope role**: applies across the tenant context
- **outlet-scope role**: applies to a specific outlet inside the same tenant

This scope behavior only makes sense because the tenant is the primary operating boundary.

For the full access-control model, see [role-permission-capability-model.md](./role-permission-capability-model.md).

## Tenancy and channel behavior

The platform supports POS, E-Commerce, or hybrid operation per tenant.

That means:

- one tenant may operate POS only
- another may operate E-Commerce only
- another may operate both

But whichever mode is active, the tenant remains the business boundary for identity, configuration, data ownership, and reporting.

## Tenancy and sellable model

Sellable flows operate at variant level.

This matters for tenancy because products, variants, pricing, stock, sale lines, cart items, and order items are all owned and evaluated inside tenant context.

## Tenancy and reverse-flow documents

Returns and exchanges are separate business documents.

This matters because reverse-flow logic must still preserve tenant ownership, traceability, and outlet/channel context inside the same tenant boundary.

## What this file does not cover

This file does not define:

- table-by-table schema enforcement
- API validation mechanics
- backend transaction implementation details
- frontend permission rendering logic

Those are covered in:

- [multi-tenant-architecture.md](./multi-tenant-architecture.md)
- [../04-data/tenant-consistency-rules.md](../04-data/tenant-consistency-rules.md)
- [../07-backend/README.md](../07-backend/README.md)
- [../06-frontend/permissions-in-ui.md](../06-frontend/permissions-in-ui.md)

## Related documents

- [multi-tenant-architecture.md](./multi-tenant-architecture.md)
- [role-permission-capability-model.md](./role-permission-capability-model.md)
- [../04-data/tenant-consistency-rules.md](../04-data/tenant-consistency-rules.md)
- [../11-config-and-customization/tenant-settings.md](../11-config-and-customization/tenant-settings.md)
- [../11-config-and-customization/feature-flags.md](../11-config-and-customization/feature-flags.md)
