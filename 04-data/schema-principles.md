<!--
meta:
  title: Schema Principles
  owner: Engineering / Data
  status: active
  last_reviewed: 2026-04-22
  tags: [schema-principles, data-design, multitenant, postgres]
-->

# Schema Principles

## Purpose

This file defines the core schema design principles for the Unified Commerce Platform.

These principles are derived from the approved business requirements and the revised logical schema. They should guide table design, relationship design, migration work, and feature-level data modeling.

## Principle 1: tenant-aware design is mandatory

Operational data belongs to exactly one tenant.

This is not optional metadata. It is a core ownership rule.

Implications:

- tenant-owned business entities should carry tenant-aware ownership directly
- cross-tenant references must not be allowed in normal operational flows
- tenant-scoped validation is required in both schema and service logic

See [tenant-consistency-rules.md](./tenant-consistency-rules.md).

## Principle 2: platform-side admin is separate from tenant staff

Platform administration must not be mixed into the tenant `users` model.

Use separate storage and separate control flow for:

- platform-side admin identities
- tenant-bound staff identities

This separation protects tenant isolation and keeps support / setup activity distinct from tenant operations.

Related:
- [../02-architecture/multi-tenancy-model.md](../02-architecture/multi-tenancy-model.md)
- [../02-architecture/multi-tenant-architecture.md](../02-architecture/multi-tenant-architecture.md)

## Principle 3: customers are tenant-specific

Customer identity is not globally unified across tenants.

Implications:

- the same email can exist in multiple tenants
- memberships are tenant-specific
- customer auth is tenant-aware
- customer profile ownership is tenant-bound

This supports customer-specific business operation per tenant.

## Principle 4: sellable flows operate at variant level

This project does not treat the product header alone as the sellable unit.

Use `variant_id` for:

- pricing rows
- inventory balances
- stock movements
- cart items
- sale lines
- order items
- returns and exchange lines

This rule keeps SKU, barcode, stock, and pricing behavior precise.

## Principle 5: inventory uses ledger + projection

Do not use only a single current-stock field as the full inventory model.

Use:

- a ledger for authoritative movement history
- a projection for fast balance reads

In this project:

- `stock_movements` is the movement history
- `inventory_balances` is the projection state

This supports audit, stock correction, reservations, and operational speed together.

## Principle 6: reverse flows are separate business documents

Returns and exchanges must not be hidden inside standard sale or order rows.

Model them explicitly because they have different:

- approval behavior
- stock behavior
- money-flow behavior
- audit behavior
- reporting behavior

This is why the schema uses separate return and exchange structures.

## Principle 7: explicit tables are preferred over overly generic storage

Prefer explicit relational tables when the business concept has stable structure, ownership, and rules.

Use explicit tables for:

- roles
- permissions
- memberships
- payments
- refunds
- returns
- exchanges
- deliveries
- price list items

Do not collapse those into one generic document table or one generic flexible relation table.

## Principle 8: reference tables are preferred over hard-coded value sets when the schema already models them

Many value sets in this project are modeled as reference tables, not just code enums.

Examples include:

- outlet types
- return policy types
- stock movement types
- payment method types
- payment statuses
- discount types
- OTP channels and purposes

If the schema already models a value set as a table, implementation should respect that pattern.

See [enum-and-reference-data-policy.md](./enum-and-reference-data-policy.md).

## Principle 9: JSONB is allowed only where flexibility is part of the approved design

JSONB is useful in this project, but only in specific approved cases.

### Appropriate JSONB uses in this project

- `tenant_settings.setting_value`
- `feature_flags.config`
- `ui_themes.theme_tokens`
- `stock_movements.metadata`
- `payment_transactions.raw_payload`
- `receipts.payload`
- `discounts` rule/config payloads where the schema already allows it
- pricing or tax snapshots captured at transaction time

### Do not use JSONB when relational structure is the real owner

Do not replace stable relational design with JSONB for:

- tenant identity
- role assignments
- outlet assignments
- variants
- payments
- returns
- exchanges
- stock balances
- core customer relationships

If a structure has consistent joins, constraints, and reporting needs, it should remain explicit.

## Principle 10: document numbers and business identifiers are separate from primary keys

Keep UUID primary keys for identity and separate business-facing numbers when required.

Examples:

- `sale_number`
- `order_number`
- `return_number`
- `exchange_number`
- `receipt_number`

This lets the system keep stable internal identity while presenting business-friendly document references.

## Principle 11: configuration is tenant-owned and scope-aware

Configuration in this project is not a global free-form blob.

Configuration must remain within approved scope patterns such as:

- tenant
- outlet
- user
- channel

Use explicit scope fields and matching scope targets.

Examples:

- feature flags by tenant / outlet / user
- tenant settings by tenant / outlet / channel
- UI themes owned by a tenant

## Principle 12: schema design must support traceability

Sensitive actions must be traceable.

The model therefore keeps explicit support for:

- payment transactions
- refund allocation
- return and exchange documents
- cash movements
- audit logs
- status history
- approval links

## Related documents

- [database-overview.md](./database-overview.md)
- [entity-relationship-map.md](./entity-relationship-map.md)
- [tenant-consistency-rules.md](./tenant-consistency-rules.md)
- [migration-strategy.md](./migration-strategy.md)
- [enum-and-reference-data-policy.md](./enum-and-reference-data-policy.md)
- [../02-architecture/multi-tenant-architecture.md](../02-architecture/multi-tenant-architecture.md)
