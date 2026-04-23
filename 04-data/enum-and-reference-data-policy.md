<!--
meta:
  title: Enum And Reference Data Policy
  owner: Engineering / Data
  status: active
  last_reviewed: 2026-04-22
  tags: [reference-data, enums, master-data, schema-policy]
-->

# Enum And Reference Data Policy

## Purpose

This file defines how value sets and reference data should be handled in this project.

The revised schema shows a clear pattern: many important value sets are modeled as **reference tables** instead of being treated only as code enums. This policy keeps implementation aligned with that pattern.

## Core rule

If the schema models a value set as a table, implementation should treat it as reference/master data, not silently collapse it into a hard-coded enum.

## Why reference tables are used here

This platform has many operational states and classification values that are reused across modules and documents.

Reference tables help by providing:

- stable IDs and codes
- readable names
- safer relational links
- clear seed strategy
- future extensibility without rewriting transactional table shapes

## Examples already modeled as reference/master tables

| Area | Reference tables |
|---|---|
| outlet classification | `outlet_types` |
| returnability | `return_policy_types` |
| inventory movement | `stock_movement_types` |
| OTP | `otp_channels`, `otp_purposes` |
| payment | `payment_method_types`, `payment_statuses` |
| discounts | `discount_types`, `discount_scopes` |
| delivery | `delivery_option_types` |
| order / fulfillment statuses | `order_statuses`, `fulfillment_statuses` |
| cash events | `cash_movement_types` |

## When a value set should be a reference table

Prefer a reference table when the value set:

- is reused by many operational records
- needs stable identifiers and human-readable labels
- may need active/inactive control
- is part of seed or controlled initialization
- benefits from future extension without changing every dependent table

## When a hard-coded enum may still be acceptable

A small code enum may still be acceptable in application code when it is only an implementation convenience **and** it does not replace a schema-owned reference set.

That means:

- code enums may mirror the database reference set
- code enums should not become the source of truth when the table already exists

## Code and name usage

Use this pattern consistently:

| Field type | Purpose |
|---|---|
| `code` | stable machine-friendly identifier |
| `name` | human-readable label |
| `status` or `is_active` | whether the value is currently usable |
| primary key | relational reference target |

`code` should be stable because business logic, integrations, or reporting may rely on it.

## Active status handling

Not every reference table in the schema has an active flag, but when the schema includes one, implementation should respect it.

Typical use:

- keep historical operational rows valid
- allow future deactivation without deleting the record
- support controlled rollout or retirement of values

## Future extensibility

Reference tables are preferred in this project because business growth is expected across:

- tenants
- outlets
- payments
- order and fulfillment handling
- discounting
- stock events
- returns and exchanges

Using a table now avoids forcing disruptive schema redesign later for value sets that were incorrectly hard-coded.

## Tenant-owned vs platform-wide reference data

Not every controlled value set is global.

### Platform-wide reference data

Examples:

- payment statuses
- stock movement types
- OTP purposes

### Tenant-owned controlled data

Examples:

- tax classes
- membership tiers
- return reason codes
- permissions are system-managed, but roles are tenant-owned
- themes and settings are tenant-owned configuration, not generic reference tables

Do not confuse tenant-owned master/configuration data with global reference values.

## Practical implementation rule

When adding a new value set, decide:

1. is it platform-wide or tenant-owned?
2. does it need relational control?
3. does the schema already express it as a table?
4. will operational rows need stable long-term references?

If the answer points to durable relational use, model it as a reference/master table.

## Related documents

- [seed-data-strategy.md](./seed-data-strategy.md)
- [naming-conventions.md](./naming-conventions.md)
- [schema-principles.md](./schema-principles.md)
- [migration-strategy.md](./migration-strategy.md)
- [../05-api/request-response-standard.md](../05-api/request-response-standard.md)
