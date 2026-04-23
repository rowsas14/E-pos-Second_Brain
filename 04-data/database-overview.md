<!--
meta:
  title: Database Overview
  owner: Engineering / Data
  status: active
  last_reviewed: 2026-04-22
  tags: [database-overview, schema, unified-commerce, postgres]
-->

# Database Overview

## Purpose

This file explains the **overall database shape** of the Unified Commerce Platform.

It is a practical overview of the revised logical schema. It does not replace table-level detail in module `data-model.md` files, and it does not replace the rules in [schema-principles.md](./schema-principles.md).

## Platform shape

The database supports one platform that serves:

- in-store **POS**
- online **E-Commerce**
- tenant-scoped business operations
- platform-side administration
- shared operational foundations such as catalog, stock, pricing, customers, payments, returns, exchanges, receipts, and reporting

The data model is designed so those areas can work together without mixing tenant ownership.

## Major data areas

| Area | Main concern | Example entities |
|---|---|---|
| Platform administration | platform-side control separate from tenant users | `platform_users` |
| Core tenant structure | tenants and outlets | `tenants`, `outlets`, `outlet_addresses`, `outlet_types` |
| Identity and access | staff users, roles, permissions, assignments | `users`, `roles`, `permissions`, `role_permissions`, `tenant_user_roles`, `outlet_user_roles` |
| Catalog and pricing | sellable products, variants, prices | `products`, `product_variants`, `price_lists`, `price_list_items` |
| Inventory | stock ledger and balance projection | `inventory_balances`, `stock_movements`, `stock_reservations`, `stock_transfers`, `stocktakes` |
| Customers and memberships | tenant-specific customer identity | `customers`, `customer_auth_accounts`, `customer_auth_identities`, `customer_memberships` |
| POS sales | cashier-side sale and till data | `tills`, `till_sessions`, `sales`, `sale_lines`, `cash_movements` |
| E-Commerce orders | carts, orders, fulfillment states | `carts`, `cart_items`, `orders`, `order_items`, `order_status_history` |
| Discounts and coupons | approval, application, redemption | `discount_requests`, `discount_applications`, `coupons`, `coupon_redemptions` |
| Payments and refunds | inbound/outbound money movement | `payments`, `payment_transactions`, allocation tables, `refunds` |
| Returns and exchanges | reverse-flow business documents | `returns`, `return_lines`, `exchanges`, exchange allocation tables |
| Logistics | order delivery and tracking | `deliveries`, `delivery_items`, `delivery_tracking` |
| Tax, receipts, audit, configuration | cross-cutting operational support | `tax_rates`, `receipts`, `audit_logs`, `feature_flags`, `ui_themes`, `tenant_settings` |

## Identity split

A critical database rule is that **platform administration is not stored in the same identity model as tenant staff**.

### Platform-side administration

- `platform_users` stores platform-side or developer-side admin identities
- these users exist outside tenant staff ownership
- they support tenant creation, setup, support intervention, and system-level control

### Tenant-side staff

- `users` stores tenant-bound staff identities
- every staff user belongs to exactly one tenant
- tenant and outlet role assignments remain within that same tenant boundary

### Tenant-side customers

- `customers` are also tenant-scoped
- the same email may exist across different tenants as separate customer records
- membership and customer auth are tenant-scoped as well

See also:

- [../02-architecture/multi-tenancy-model.md](../02-architecture/multi-tenancy-model.md)
- [tenant-consistency-rules.md](./tenant-consistency-rules.md)

## Sellable commerce model

This platform uses a **variant-level sellable model**.

That means price, stock, cart lines, sale lines, and order lines all operate on `variant_id`, not only on the product header.

Main implications:

- every sellable product must have at least one active variant
- SKU and barcode live at the variant level
- stock is tracked per outlet and variant
- pricing is resolved per price list item and variant

See:

- [schema-principles.md](./schema-principles.md)
- [../02-architecture/system-overview.md](../02-architecture/system-overview.md)

## Inventory model

Inventory is split into two complementary structures:

| Structure | Purpose |
|---|---|
| ledger | authoritative movement history |
| projection | fast current-balance view |

### Ledger

`stock_movements` records movement events such as sale out, return in, transfer, stocktake gain/loss, reservation hold/release, and adjustment.

### Projection

`inventory_balances` holds current on-hand, reserved, and available quantities per outlet and variant.

This model supports both auditability and operational speed.

See:

- [schema-principles.md](./schema-principles.md)
- [entity-relationship-map.md](./entity-relationship-map.md)

## POS and E-Commerce on shared foundations

POS and E-Commerce are not separate product silos in the data model.

They share:

- products and variants
- pricing foundation
- tax foundation
- stock foundation
- customer foundation
- payments
- receipts
- reporting inputs

They differ in transaction shapes:

| Channel | Primary documents |
|---|---|
| POS | `sales`, `sale_lines`, till and cash movement entities |
| E-Commerce | `carts`, `orders`, `order_items`, delivery entities |

That shared model is what allows unified reporting and common operational rules.

## Payments, refunds, returns, and exchanges

The schema separates these clearly.

### Payments

`payments` is the unified money-movement record for sale collection, order collection, refund payout, and exchange difference settlement.

### Refunds

`refunds` exists as a business refund record linked to original payment and outbound refund payment.

### Returns and exchanges

Returns and exchanges are not modeled as ordinary sales rows.

- `returns` and `return_lines` handle return events
- `exchanges` and `exchange_lines` handle exchange flows
- exchange payment and refund allocations remain explicit

This keeps reverse-flow logic auditable and controlled.

## Operational vs reference vs configurable data

### Operational data

Data created by normal business activity.

Examples:

- sales
- orders
- stock movements
- payments
- returns
- exchanges
- deliveries

### Reference data

Controlled value sets used by operational records.

Examples:

- outlet types
- payment statuses
- discount types
- stock movement types
- OTP channels and purposes

### Configurable data

Tenant-owned settings and business controls.

Examples:

- feature flags
- UI themes
- tenant settings
- membership tiers
- tax classes
- price lists

See:

- [seed-data-strategy.md](./seed-data-strategy.md)
- [enum-and-reference-data-policy.md](./enum-and-reference-data-policy.md)

## Related documents

- [schema-principles.md](./schema-principles.md)
- [entity-relationship-map.md](./entity-relationship-map.md)
- [tenant-consistency-rules.md](./tenant-consistency-rules.md)
- [../02-architecture/system-overview.md](../02-architecture/system-overview.md)
- [../02-architecture/multi-tenant-architecture.md](../02-architecture/multi-tenant-architecture.md)
