<!--
meta:
  title: Migration Strategy
  owner: Engineering / Data
  status: active
  last_reviewed: 2026-04-22
  tags: [migrations, ef-core, postgres, schema-change]
-->

# Migration Strategy

## Purpose

This file explains how the approved logical schema should be turned into **PostgreSQL + EF Core** migration work.

The revised schema document is a logical design. It is **not** itself a migration script. Migration work must convert that design into implementable database changes with correct sequencing, constraints, indexes, and seed/reference handling.

## Core rule

Do not treat the schema document as if it can be copied directly into production DDL without implementation review.

Migration work must translate logical intent into safe, incremental database changes.

## Main migration goals

- preserve tenant isolation
- implement stable identity and relationship structure
- add check constraints and partial unique indexes where the schema requires them
- protect transaction-sensitive areas such as stock, payments, refunds, returns, and exchanges
- keep migrations reviewable and reversible where possible

## Recommended migration sequencing

### 1. Foundation tables first

Create stable root structures first:

- `platform_users`
- `tenants`
- reference tables such as outlet types
- `outlets`
- address and core ownership structures

### 2. Identity and access next

Create:

- `users`
- `roles`
- `permissions`
- role assignment tables

This allows later operational tables to reference valid staff ownership and permission structures.

### 3. Catalog and pricing foundation

Create:

- categories
- brands
- suppliers
- products
- variants
- attributes
- product images
- price lists and price list items

Because sellable flows operate at variant level, this foundation must stabilize before stock, sale, and order flows are added.

### 4. Inventory structures

Create:

- `inventory_balances`
- `stock_movement_types`
- `stock_movements`
- reservation, transfer, and stocktake tables

### 5. Customer and membership structures

Create:

- customers
- auth accounts and identities
- memberships and tiers
- customer addresses
- OTP related structures

### 6. POS and E-Commerce transaction structures

Create:

- POS sale, till, and cash movement tables
- cart, order, order item, and order status history tables

### 7. Discounts, payments, refunds, returns, exchanges

These areas are transaction-sensitive and should be introduced after foundational entities exist.

### 8. Cross-cutting support tables

Create:

- tax rates
- receipts
- audit logs
- feature flags
- themes
- tenant settings

## Constraint planning

### Check constraints

Use migrations to implement the allowed value rules that are expressed as checks in the logical schema, such as:

- status values
- scope values
- channel values
- payment direction
- document exclusivity where a logical check is defined

### Partial unique indexes

The schema includes several cases that depend on partial uniqueness.

Examples include:

- unique normalized email per tenant when not null
- unique normalized phone per tenant when not null
- unique active open till session
- unique optional barcode when present
- unique scope-sensitive records where nullability matters

These should be planned carefully because they are part of correctness, not only optimization.

### Foreign keys

Use foreign keys wherever ownership and relationships are explicit and stable.

When the same-tenant rule spans more than a simple foreign key can enforce, supplement with application validation.

See [tenant-consistency-rules.md](./tenant-consistency-rules.md).

## Seed and reference planning inside migrations

Do not mix all data creation into one migration style.

### Suitable for migration-time seeding

Stable reference sets such as:

- outlet types
- payment method types
- payment statuses
- discount types
- discount scopes
- OTP channels
- OTP purposes
- return policy types
- stock movement types
- delivery option types

### Not suitable for global migration-time seeding

Tenant-created business data such as:

- tenant users
- customers
- products
- price lists owned by a tenant
- outlets owned by a tenant
- membership tiers owned by a tenant
- tenant settings and themes that are customer-specific

See [seed-data-strategy.md](./seed-data-strategy.md).

## Migration caution areas

| Area | Why it needs care |
|---|---|
| tenant-sensitive relationships | cross-tenant mistakes are difficult to repair later |
| variant-level sellable design | many downstream tables depend on variant identity |
| inventory ledger and balances | movement correctness must remain audit-safe |
| payment and refund structures | purpose, direction, and allocation rules must remain explicit |
| returns and exchanges | source references and reverse-flow logic are easy to model incorrectly |
| partial unique indexes | correctness often depends on them, not just performance |

## EF Core implementation direction

Migration implementation should stay aligned with the actual project stack:

- PostgreSQL as database
- EF Core for migrations
- backend services enforcing business-sensitive cross-table validation
- Clean Architecture keeping persistence details out of domain logic

Do not push every business rule into migration code. Use migrations for schema shape, constraints, indexes, and stable seed/reference records. Use application services for complex business transaction rules.

## Change discipline

For a schema change:

1. update the owning data documentation
2. update relevant feature `data-model.md`
3. review tenant-consistency impact
4. review migration order and dependency impact
5. implement migration
6. verify affected indexes, checks, and seed/reference assumptions
7. update project history when the change is broad or breaking

## Related documents

- [schema-principles.md](./schema-principles.md)
- [tenant-consistency-rules.md](./tenant-consistency-rules.md)
- [seed-data-strategy.md](./seed-data-strategy.md)
- [enum-and-reference-data-policy.md](./enum-and-reference-data-policy.md)
- [naming-conventions.md](./naming-conventions.md)
- [../07-backend/README.md](../07-backend/README.md)
- [../07-backend/transaction-handling-rules.md](../07-backend/transaction-handling-rules.md)
