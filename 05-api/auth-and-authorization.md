<!--
meta:
  title: API Authentication and Authorization
  owner: Engineering / Security / API
  status: active
  last_reviewed: 2026-04-23
  tags: [api, auth, authorization, tenants, permissions]
-->

# API Authentication and Authorization

## Purpose

This file defines how API-level authentication and authorization should be understood for this platform.

It distinguishes:

- who the caller is
- what scope the caller belongs to
- what the caller is allowed to do
- whether the feature is available in that tenant context
- whether the requested resource belongs to the same allowed boundary

## Core access model

The platform has three materially different access contexts:

| Access context | Meaning |
|---|---|
| platform admin access | platform-side administration, separate from tenant staff |
| tenant staff access | tenant-bound operational and admin access within one tenant only |
| customer access | tenant-specific customer-facing access within customer scope |

These must not be treated as one shared user model.

Related docs:

- [../02-architecture/multi-tenancy-model.md](../02-architecture/multi-tenancy-model.md)
- [../02-architecture/role-permission-capability-model.md](../02-architecture/role-permission-capability-model.md)
- [../04-data/tenant-consistency-rules.md](../04-data/tenant-consistency-rules.md)

## Authentication vs authorization vs capability vs tenant check

| Concern | Question answered |
|---|---|
| authentication | who is making the request |
| authorization | does that caller have the required permission or role scope |
| capability check | is the feature assigned and available in the current operating model |
| tenant boundary check | does the target resource belong to the same allowed tenant or outlet boundary |

All four may be required in one request.

## Platform admin access

Platform admin access is separate from tenant staff identity.

API endpoints intended for platform administration must not rely on tenant staff assumptions. They support platform-side actions such as tenant lifecycle control, onboarding support, and capability governance.

Examples of platform-side route style:

- `/api/v1/platform/tenants`
- `/api/v1/platform/capabilities`
- `/api/v1/platform/onboarding`

These examples show route style only. Exact endpoint inventory must be defined in module-level docs.

## Tenant staff access

Tenant staff users belong to exactly one tenant.

Tenant staff APIs must enforce:

- authenticated staff identity
- same-tenant resource access
- role or permission eligibility
- outlet scope where applicable
- capability and configuration checks when the feature depends on tenant-side setup

Examples of tenant staff route style:

- `/api/v1/products`
- `/api/v1/inventory/stocktakes`
- `/api/v1/sales`
- `/api/v1/returns`
- `/api/v1/settings/themes`

## Customer access

Customer APIs are tenant-specific.

The same email may exist across tenants as separate customer identities, so API-level assumptions must remain tenant-aware.

Customer-facing endpoints must not collapse customer identity into a global cross-tenant account model.

Examples of customer route style:

- `/api/v1/storefront/products`
- `/api/v1/storefront/cart`
- `/api/v1/storefront/orders`
- `/api/v1/storefront/account`

## Default role mapping vs effective API access

Some features may be seeded with a default role mapping such as `cashier`, `manager`, or `tenant-admin`.

That default mapping is not the final runtime API rule.

API authorization must evaluate the **current effective access state**, which means:

- current authenticated identity type
- current role scope
- current permission grants
- current platform-assigned feature capability
- current tenant-side configuration that affects feature availability or behavior
- current tenant and outlet boundary

### API rule

**Do not authorize a request only because the feature once had a default role mapping. The API must honor the current assigned mapping and current tenant configuration.**

### Practical example

A feature may be seeded with a default `manager` mapping.

Later:

- platform admin changes it to `supervisor`
- the tenant restricts it to one outlet
- the tenant disables one action path inside configuration

The API must enforce the **current** mapping and configuration, not the earlier default mapping.

## Role and permission checks

Role checks and permission checks are not the same as tenant checks.

A request may pass authentication but still fail because:

- the user lacks the required permission
- the role scope is wrong
- the target outlet is outside the user’s active outlet scope
- the feature is not assigned or not configured for that tenant context
- the resource belongs to another tenant

## Capability enforcement impact

Feature capability enforcement matters for APIs that support:

- discount workflows
- refund workflows
- stock-sensitive actions
- tenant settings and configuration
- role-sensitive management features
- approval-sensitive features

When a feature is not assigned into the current tenant-facing access model, the API should not behave as if a default role still grants access.

## Tenant-aware authorization impact

Authorization must stay tenant-aware in all cases where records are tenant-owned or outlet-owned.

That includes operations against:

- users and role assignments
- customers and memberships
- products, variants, and pricing
- inventory balances, movements, reservations, and stocktakes
- sales, orders, payments, refunds, returns, and exchanges
- settings, themes, and feature flags

## Where this check belongs

At API level, the pipeline may perform authentication and route-level guard behavior.

Application and backend rules must still perform effective access validation when the operation is sensitive or stateful.

See:

- [../07-backend/application-layer-rules.md](../07-backend/application-layer-rules.md)
- [../07-backend/validation-rules.md](../07-backend/validation-rules.md)

## Related documents

- [api-overview.md](./api-overview.md)
- [error-contract.md](./error-contract.md)
- [../02-architecture/role-permission-capability-model.md](../02-architecture/role-permission-capability-model.md)
- [../02-architecture/multi-tenancy-model.md](../02-architecture/multi-tenancy-model.md)
- [../07-backend/application-layer-rules.md](../07-backend/application-layer-rules.md)
- [../07-backend/validation-rules.md](../07-backend/validation-rules.md)
