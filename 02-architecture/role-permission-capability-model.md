<!--
meta:
  title: Role Permission Capability Model
  owner: Architecture / Engineering
  status: active
  last_reviewed: 2026-04-23
  tags: [architecture, access-control, permissions, capabilities, configuration]
-->

# Role Permission Capability Model

## Purpose

This document explains the access-control model used by the Unified Commerce Platform.

The platform does not use a fixed hard-coded role list as the complete access model. Instead, it combines **roles**, **permissions**, **feature capabilities**, **default role mappings**, and **tenant-side configuration**.

## Why this model exists

The platform is customer-specific per tenant.

That means access behavior cannot stop at a static list such as `cashier`, `manager`, or `admin`. The platform must allow platform governance over feature capability assignment while still allowing each customer tenant to configure approved features inside its own operating context.

## Core terms

| Term | Meaning in this project |
|---|---|
| Role | a named access grouping owned by a tenant and scoped to tenant or outlet |
| Permission | a granular action or authorization unit |
| Feature capability | platform-governed feature availability that can be mapped into the tenant-facing access model |
| Default role mapping | an initial or seeded feature-to-role starting point, not the final runtime access rule |
| Tenant-side configuration | tenant-owned configuration that controls how an approved feature behaves inside tenant, outlet, user, or channel context |

## Separation of concerns

### Roles

Roles describe who is allowed to act within a tenant operating model.

The source model supports two role scopes:

- **tenant scope**
- **outlet scope**

### Permissions

Permissions represent granular control over actions.

They are system-managed definitions that roles can map to.

### Feature capabilities

Feature capability sits above ordinary role mapping.

The platform admin controls feature availability assignment into the role model. This allows the platform to decide which feature areas are available to the tenant-facing operating model without forcing a single hard-coded role structure for all customers.

### Default role mappings

Some features may start with a default role mapping during seeding, onboarding, or first-time configuration.

Examples of what a default mapping means:

- a starting assignment for a newly enabled feature
- a recommended role for a common operating model
- an onboarding convenience so the tenant does not start from a blank mapping

A default mapping does **not** mean:

- the feature is permanently owned by that role
- runtime authorization can trust the default without checking current assignment
- the tenant can use the feature if platform capability assignment has not approved it

### Tenant-side configuration

Once a feature is approved into the tenant-facing model, the tenant can configure behavior within its own boundary.

That configuration may be tenant-, outlet-, user-, or channel-scoped depending on the feature and configuration model.

## Default role mapping vs effective access

This distinction must stay explicit across architecture, API, backend, and feature documentation.

| Concept | Meaning |
|---|---|
| Default role mapping | initial starter assignment |
| Effective access | the current runtime result of platform-admin capability assignment plus current tenant-side configuration and normal permission checks |

### Required rule

**Default role mapping does not determine final access by itself. Final access is determined by platform-admin capability assignment plus tenant-side configuration, role scope, permission checks, and tenant-boundary validation.**

## Role scopes in this project

| Scope | Meaning |
|---|---|
| Tenant scope | role applies across the tenant context |
| Outlet scope | role applies to a specific outlet within the same tenant |

This allows the same tenant to support both broad administrative control and localized store operation.

## Sensitive action control

Certain actions require stronger control and traceability.

Examples clearly supported by the project direction include:

- discounts
- refunds
- stock adjustments
- approvals
- feature-configuration changes

These actions must not depend only on UI visibility or on a seeded default role. They must be controlled through effective capability and permission checks and recorded through auditability expectations.

## Capability assignment boundary

The key project rule is:

- **platform admin** controls feature capability assignment
- **tenant** configures approved features inside its own environment

That boundary matters because it prevents uncontrolled tenant behavior while still supporting customer-specific operation.

Default role mappings may exist, but they operate only as a platform-approved starting point inside this boundary.

## How the model affects backend behavior

Backend services must:

- evaluate tenant-scope and outlet-scope assignments correctly
- validate sensitive actions through current permission checks
- enforce capability and configuration boundaries before executing workflows
- avoid trusting seeded role assumptions as the final runtime authority
- prevent cross-tenant role, outlet, and user misuse
- record sensitive actions in auditable ways

For technical enforcement direction, see [multi-tenant-architecture.md](./multi-tenant-architecture.md).

## How the model affects frontend behavior

Frontend should not assume that every tenant sees the same feature surface or that the default role still owns the feature.

Frontend behavior must support:

- feature visibility based on approved capabilities
- action visibility based on current permissions
- screen behavior shaped by tenant configuration where applicable
- different operating views for platform admin, tenant admin, outlet staff, and customer-facing flows

For frontend standards, see [../06-frontend/permissions-in-ui.md](../06-frontend/permissions-in-ui.md).

## How the model affects tenant configuration

Configuration documents should not be written as if a tenant can enable any feature without platform approval or as if a seeded default role guarantees access.

Tenant-side configuration should be documented in relation to:

- [../11-config-and-customization/feature-flags.md](../11-config-and-customization/feature-flags.md)
- [../11-config-and-customization/permission-configuration.md](../11-config-and-customization/permission-configuration.md)
- [../11-config-and-customization/tenant-settings.md](../11-config-and-customization/tenant-settings.md)

## Practical model summary

```text
Platform Admin
  -> approves and assigns feature capability

Default Role Mapping
  -> optional starting assignment only

Tenant Roles and Permissions
  -> current effective runtime access path

Tenant Configuration
  -> controls how the approved feature behaves inside tenant boundary
```

## What this file does not cover

This file does not define:

- table-by-table schema structure for roles and permissions
- frontend component composition details
- backend class-level implementation rules

For those topics, see:

- [../04-data/database-overview.md](../04-data/database-overview.md)
- [backend-architecture.md](./backend-architecture.md)
- [frontend-architecture.md](./frontend-architecture.md)

## Related documents

- [multi-tenancy-model.md](./multi-tenancy-model.md)
- [multi-tenant-architecture.md](./multi-tenant-architecture.md)
- [../05-api/auth-and-authorization.md](../05-api/auth-and-authorization.md)
- [../07-backend/application-layer-rules.md](../07-backend/application-layer-rules.md)
- [../07-backend/validation-rules.md](../07-backend/validation-rules.md)
- [../12-security-and-compliance/authorization-model.md](../12-security-and-compliance/authorization-model.md)
