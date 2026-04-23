<!--
meta:
  title: Tenant Consistency Rules
  owner: Engineering / Data
  status: active
  last_reviewed: 2026-04-22
  tags: [tenant-consistency, multitenant, validation, data-integrity]
-->

# Tenant Consistency Rules

## Purpose

This file defines the **same-tenant consistency rules** that protect tenant isolation in the Unified Commerce Platform.

The revised schema explicitly notes that strict same-tenant validation is required. This file explains where that consistency can be enforced directly in schema design and where service-layer validation is still required.

## Core rule

For normal tenant-owned business activity, related records must belong to the **same tenant**.

This rule applies across:

- staff identity and role assignment
- customer ownership
- outlet ownership
- product and stock ownership
- configuration scope
- payments, returns, and exchanges
- audit actor ownership where tenant user activity is recorded

## What this rule does not mean

It does **not** mean platform-side administration is tenant-owned.

`platform_users` is intentionally separate from tenant-side users.

See [../02-architecture/multi-tenancy-model.md](../02-architecture/multi-tenancy-model.md).

## Enforcement layers

| Enforcement level | Use when |
|---|---|
| schema-level constraints | the rule can be expressed directly by keys, uniqueness, or checks |
| application / service validation | the rule spans multiple tables or business decisions that cannot be safely expressed as a simple database constraint |
| transaction handling | the operation changes several tenant-owned records together |

See also [../07-backend/transaction-handling-rules.md](../07-backend/transaction-handling-rules.md).

## Rule set by area

### 1. Platform admin separation

- `platform_users` must remain separate from tenant `users`
- tenant operational records must not depend on `platform_users` as if they were tenant staff
- setup, tenant creation, and support workflows should keep this identity split clear

### 2. Tenant-bound staff users

- each `users` row belongs to exactly one tenant
- a staff user from Tenant A must not be assigned roles, outlets, or operational activity under Tenant B

### 3. Tenant-scope role assignments

For `tenant_user_roles`:

- `tenant_id` must match the assigned user’s tenant
- `tenant_id` must match the assigned role’s tenant
- assigned role must be tenant-scope

For `outlet_user_roles`:

- `tenant_id` must match the user
- `tenant_id` must match the role
- `tenant_id` must match the outlet
- assigned role must be outlet-scope

### 4. Outlet boundaries

- outlets belong to one tenant
- outlet-level operations must not reference stock, users, or role assignments from another tenant
- outlet-scoped configuration must target outlets owned by the same tenant

### 5. Tenant-specific customers

- `customers` are tenant-owned
- the same email can exist across tenants, but each customer record remains separate
- customer auth accounts and identities must remain within the same tenant as the customer
- customer memberships, addresses, and OTP verification history remain within that customer’s tenant

### 6. Catalog and product ownership

- tenant-owned product records must not link across tenants
- category, brand, tax class, suppliers, and products should all remain within one tenant context
- variants inherit tenant ownership through product and explicit tenant-aware design

### 7. Inventory and outlet consistency

- `inventory_balances` must keep tenant, outlet, and variant ownership aligned
- stock movements must record outlet and variant that belong to the same tenant
- reservations, transfers, and stocktakes must remain inside one tenant even when they span multiple outlets

### 8. POS and order consistency

- sales belong to one tenant and one outlet context
- order records belong to one tenant and customer context
- line items must not reference variants from another tenant
- till sessions and cash movements must remain within outlet and till ownership of the same tenant

### 9. Payment, refund, return, and exchange consistency

- payment rows must remain tenant-owned
- sales and order payment allocation must not allocate a payment from another tenant
- refund rows must not cross tenant ownership
- return and exchange records must remain within one tenant even when they refer back to source documents
- return outlet and original outlet references, where present, must still respect tenant boundaries

### 10. Configuration scope consistency

For `feature_flags`:

- scope target must match declared scope
- if `user_id` is set, it must belong to the same tenant
- if `outlet_id` is set, it must belong to the same tenant

For `tenant_settings`:

- tenant / outlet / channel scope must be explicit
- any outlet-scoped setting must target an outlet of the same tenant

For `ui_themes`:

- themes are tenant-owned
- a tenant’s theme must not be assigned as another tenant’s active theme by direct record reuse

## What schema can enforce directly

Good schema-level candidates include:

- foreign keys
- composite uniqueness where ownership is obvious
- check constraints for allowed states
- partial unique indexes
- explicit tenant_id presence on tenant-owned tables

## What usually needs service-layer validation

Service logic is still needed when the rule spans several related rows.

Examples:

- confirming that `user`, `role`, `outlet`, and `tenant_id` all match during assignment
- validating that source sale, source order, return outlet, and exchange outlet remain in the same tenant context
- confirming that payment allocations do not cross tenant or purpose boundaries
- verifying same-tenant relationships when the database cannot express the rule cleanly through a simple FK

## Practical implementation expectation

For this project, repeating `tenant_id` on child tables is useful only when implementation also enforces consistency.

That means:

1. schema should carry tenant ownership clearly
2. migrations should add the relevant constraints and indexes
3. application services should validate cross-table same-tenant rules
4. transaction handling should preserve tenant-safe state changes

## Related documents

- [schema-principles.md](./schema-principles.md)
- [database-overview.md](./database-overview.md)
- [migration-strategy.md](./migration-strategy.md)
- [../02-architecture/multi-tenancy-model.md](../02-architecture/multi-tenancy-model.md)
- [../02-architecture/multi-tenant-architecture.md](../02-architecture/multi-tenant-architecture.md)
- [../02-architecture/role-permission-capability-model.md](../02-architecture/role-permission-capability-model.md)
- [../07-backend/transaction-handling-rules.md](../07-backend/transaction-handling-rules.md)
