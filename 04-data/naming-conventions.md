<!--
meta:
  title: Naming Conventions
  owner: Engineering / Data
  status: active
  last_reviewed: 2026-04-22
  tags: [naming, schema, conventions, postgres, ef-core]
-->

# Naming Conventions

## Purpose

This file defines database naming rules for the Unified Commerce Platform.

The guidance follows the naming patterns already visible in the revised schema and is intended for **PostgreSQL + EF Core** implementation.

## General style

Use:

- lowercase
- snake_case
- plural table names for entity collections
- singular-style column names only where that is already part of the field pattern, such as `tenant_id`, `created_at`, or `status`

## Table naming rules

### Entity tables

Use plural nouns for main tables.

Examples:

- `tenants`
- `outlets`
- `users`
- `customers`
- `products`
- `product_variants`
- `payments`
- `returns`
- `exchanges`

### Reference tables

Use plural nouns that describe the value set.

Examples:

- `payment_statuses`
- `discount_types`
- `stock_movement_types`
- `return_policy_types`

### Junction / mapping tables

Use descriptive plural names that show both sides or the purpose of the mapping.

Examples:

- `role_permissions`
- `tenant_user_roles`
- `outlet_user_roles`
- `product_suppliers`
- `variant_attribute_values`

### Header / line patterns

When a business document has line items, use a clear header-line pair.

Examples:

- `sales` / `sale_lines`
- `stock_transfers` / `stock_transfer_lines`
- `stocktakes` / `stocktake_lines`
- `returns` / `return_lines`
- `exchanges` / `exchange_lines`

## Primary key naming

Use `id` as the primary key column for entity tables.

This pattern is consistent across the schema and keeps EF Core mapping predictable.

## Foreign key naming

Use `<referenced_entity>_id`.

Examples:

- `tenant_id`
- `outlet_id`
- `user_id`
- `role_id`
- `variant_id`
- `payment_id`
- `stocktake_id`

### Multiple references to the same entity type

When the same table is referenced more than once, qualify the role clearly.

Examples:

- `from_outlet_id`
- `to_outlet_id`
- `source_sale_id`
- `source_order_id`
- `original_payment_id`
- `refund_payment_id`
- `opened_by`
- `closed_by`
- `approved_by`

## Tenant-scoped naming

For tenant-owned tables, use explicit `tenant_id` when the schema includes direct tenant ownership.

Do not hide tenant ownership in ambiguous field names.

Examples:

- `tenant_id` on users, customers, products, payments, settings, themes, and many operational tables

## Code, name, and status fields

Use these consistently:

| Column | Meaning |
|---|---|
| `code` | stable short identifier |
| `name` | human-readable label |
| `status` | lifecycle state when the table uses stateful records |
| `is_active` | active flag when binary activity state is sufficient |
| `is_default` | explicit default marker when needed |
| `is_primary` | explicit primary marker when needed |

Do not use several overlapping columns for the same meaning unless the schema already requires that distinction.

## Timestamp naming

Use `_at` suffix for timestamps.

Examples:

- `created_at`
- `updated_at`
- `opened_at`
- `closed_at`
- `completed_at`
- `changed_at`
- `resolved_at`
- `verified_at`

Use descriptive verb-based naming when the time represents a business event, not just record creation.

## Business number naming

Use descriptive document number fields separate from primary keys.

Examples:

- `sale_number`
- `order_number`
- `return_number`
- `exchange_number`
- `receipt_number`
- `membership_no`

## Quantity and amount naming

Use names that describe the business meaning clearly.

Examples:

- `on_hand_qty`
- `reserved_qty`
- `available_qty`
- `requested_qty`
- `counted_qty`
- `captured_amount`
- `refund_total`
- `grand_total`

Do not shorten business-critical amount or quantity names so much that intent becomes ambiguous.

## Status and scope naming

When a table uses a scope or directional field, use direct and readable names.

Examples:

- `scope`
- `channel`
- `payment_direction`
- `payment_purpose`
- `source_domain`
- `source_channel`
- `reference_type`

## JSONB field naming

When JSONB is intentionally used, the field name should describe what the payload means.

Examples:

- `setting_value`
- `theme_tokens`
- `metadata`
- `raw_payload`
- `rule_payload`
- `pricing_snapshot`
- `payload`

Avoid vague names such as `data` or `json` when the business meaning is known.

## Practical EF Core note

Keep names stable and explicit so EF Core configuration remains readable and database intent stays clear.

Do not rely on automatic naming conventions to hide unclear model design.

## Related documents

- [schema-principles.md](./schema-principles.md)
- [migration-strategy.md](./migration-strategy.md)
- [enum-and-reference-data-policy.md](./enum-and-reference-data-policy.md)
- [tenant-consistency-rules.md](./tenant-consistency-rules.md)
