<!--
meta:
  title: Data Documentation
  owner: Engineering / Data
  status: active
  last_reviewed: 2026-04-22
  tags: [data, database, schema, postgres, ef-core]
-->

# Data Documentation

## Purpose

This section documents the **data model and schema rules** for the Unified Commerce Platform.

The platform combines **E-POS + E-Commerce** on one multi-tenant foundation. Because tenant isolation, cashier speed, pricing accuracy, stock correctness, payment allocation, returns, exchanges, and reporting all depend on the data model, this section exists to keep schema work aligned with the approved business and architecture direction.

This folder is grounded in:

- the approved business requirements for the unified commerce platform
- the revised logical schema
- the project direction for **PostgreSQL + EF Core**
- the cleaned 2nd Brain structure used across this project

## Why this section matters

For this project, data design is not only a storage concern.

The schema directly controls whether the platform can safely support:

- separate platform admin and tenant staff identities
- tenant-specific customers and memberships
- flexible role and permission assignment inside a tenant
- variant-level sellable flows
- inventory ledger + balance projection
- separate return and exchange business documents
- tenant-scoped configuration, themes, and feature flags

A weak schema here would create cross-tenant leakage risk, pricing inconsistency, stock mismatch, or incorrect payment / refund behavior.

## Files in this folder

| File | Purpose | Read when |
|---|---|---|
| [database-overview.md](./database-overview.md) | explains the major data areas and how they fit together | you need a practical map of the database |
| [schema-principles.md](./schema-principles.md) | defines the core design rules behind the schema | you are creating or revising tables |
| [entity-relationship-map.md](./entity-relationship-map.md) | shows how major entities connect | you need to trace relationships quickly |
| [tenant-consistency-rules.md](./tenant-consistency-rules.md) | defines same-tenant consistency expectations | you are working on tenant-sensitive logic |
| [migration-strategy.md](./migration-strategy.md) | explains how logical schema turns into EF Core migrations | you are planning or reviewing migrations |
| [seed-data-strategy.md](./seed-data-strategy.md) | defines what should be globally seeded vs tenant-created | you are preparing initial data |
| [enum-and-reference-data-policy.md](./enum-and-reference-data-policy.md) | explains reference tables and enumerated value handling | you are adding value sets or master data |
| [naming-conventions.md](./naming-conventions.md) | defines naming rules for tables and columns | you are creating or renaming schema objects |

## Recommended reading paths

### If you are new to the database model

1. [database-overview.md](./database-overview.md)
2. [entity-relationship-map.md](./entity-relationship-map.md)
3. [schema-principles.md](./schema-principles.md)
4. [tenant-consistency-rules.md](./tenant-consistency-rules.md)

### If you are changing tenant-sensitive schema

1. [schema-principles.md](./schema-principles.md)
2. [tenant-consistency-rules.md](./tenant-consistency-rules.md)
3. [migration-strategy.md](./migration-strategy.md)
4. [../02-architecture/multi-tenant-architecture.md](../02-architecture/multi-tenant-architecture.md)

### If you are adding new reference or lookup data

1. [enum-and-reference-data-policy.md](./enum-and-reference-data-policy.md)
2. [seed-data-strategy.md](./seed-data-strategy.md)
3. [naming-conventions.md](./naming-conventions.md)

### If you are changing a feature data model

1. read the relevant feature `data-model.md` under [../08-modules/](../08-modules/)
2. read [schema-principles.md](./schema-principles.md)
3. read [tenant-consistency-rules.md](./tenant-consistency-rules.md)
4. then review [migration-strategy.md](./migration-strategy.md)

## Related sections outside this folder

- [../01-product/README.md](../01-product/README.md)
- [../02-architecture/system-overview.md](../02-architecture/system-overview.md)
- [../02-architecture/multi-tenancy-model.md](../02-architecture/multi-tenancy-model.md)
- [../02-architecture/multi-tenant-architecture.md](../02-architecture/multi-tenant-architecture.md)
- [../02-architecture/role-permission-capability-model.md](../02-architecture/role-permission-capability-model.md)
- [../07-backend/README.md](../07-backend/README.md)
- [../05-api/README.md](../05-api/README.md)

## What should not go here

Do not place these here unless the document is specifically about data behavior:

- generic product descriptions
- frontend screen layout rules
- backend service orchestration that does not affect schema
- detailed endpoint contract rules that belong in [../05-api/](../05-api/)
- feature implementation steps that belong in [../08-modules/](../08-modules/)

## Scope boundary

This folder documents the **data structure and data-governance direction**.

It does **not** replace:

- product intent in [../01-product/](../01-product/)
- architecture intent in [../02-architecture/](../02-architecture/)
- backend implementation rules in [../07-backend/](../07-backend/)
- feature-specific data details under [../08-modules/](../08-modules/)

## Related documents

- [database-overview.md](./database-overview.md)
- [schema-principles.md](./schema-principles.md)
- [entity-relationship-map.md](./entity-relationship-map.md)
- [tenant-consistency-rules.md](./tenant-consistency-rules.md)
- [migration-strategy.md](./migration-strategy.md)
- [seed-data-strategy.md](./seed-data-strategy.md)
- [enum-and-reference-data-policy.md](./enum-and-reference-data-policy.md)
- [naming-conventions.md](./naming-conventions.md)
