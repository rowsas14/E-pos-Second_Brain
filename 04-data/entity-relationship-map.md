<!--
meta:
  title: Entity Relationship Map
  owner: Engineering / Data
  status: active
  last_reviewed: 2026-04-22
  tags: [entity-relationship, er-map, schema-map, relationships]
-->

# Entity Relationship Map

## Purpose

This file provides a readable map of the major entity relationships in the revised schema.

It is not a full ERD export. It is a working guide so developers, architects, QA members, and AI assistants can quickly understand how the main data areas connect.

For table-level rules, also read:

- [database-overview.md](./database-overview.md)
- [schema-principles.md](./schema-principles.md)
- [tenant-consistency-rules.md](./tenant-consistency-rules.md)

## High-level map

```text id="t8dteo"
platform_users

tenants
  -> outlets -> outlet_addresses
  -> users -> tenant_user_roles / outlet_user_roles
  -> roles -> role_permissions -> permissions
  -> customers -> auth / memberships / addresses / otp
  -> catalog -> variants -> prices / inventory / sales / carts / orders
  -> payments / refunds
  -> returns / exchanges
  -> receipts / audit / feature_flags / ui_themes / tenant_settings
```

## 1. Platform administration and tenant foundation

### Platform administration

- `platform_users` is separate from tenant-side user storage

### Tenant foundation

- `tenants` is the root business entity
- `outlets` belongs to `tenants`
- `outlet_addresses` belongs to `outlets`
- `outlet_types` classifies `outlets`

## 2. Staff identity and access

```text id="nvv0fc"
tenants
  -> users
  -> roles
roles -> role_permissions -> permissions
users + roles -> tenant_user_roles
users + roles + outlets -> outlet_user_roles
```

### Main relationships

| Parent | Child | Notes |
|---|---|---|
| `tenants` | `users` | staff are tenant-bound |
| `tenants` | `roles` | roles are tenant-owned |
| `roles` | `role_permissions` | role-to-permission mapping |
| `permissions` | `role_permissions` | permission set is reused by roles |
| `users` + `roles` | `tenant_user_roles` | tenant-scope assignment |
| `users` + `roles` + `outlets` | `outlet_user_roles` | outlet-scope assignment |

## 3. Catalog and product model

```text id="r3d71k"
tenants
  -> brands
  -> suppliers -> supplier_addresses
  -> categories
  -> tax_classes
  -> products -> product_variants
products -> product_images
products <-> suppliers via product_suppliers
products/categories -> product_attributes / category_attributes / attribute_values / variant_attribute_values
```

### Key points

- `products` is the shared product master
- `product_variants` is the sellable unit
- category, brand, tax class, and return policy are linked at product level
- attributes support variant definition and category-driven setup
- product images can be product-level or variant-level
- suppliers relate through a junction table

## 4. Pricing

```text id="roq8k8"
tenants -> price_lists -> price_list_items -> product_variants
price_list_items -> outlets (optional override)
```

### Key points

- `price_lists` are tenant-owned
- `price_list_items` target variants
- outlet override is supported at item level

## 5. Inventory

```text id="a1ph4z"
product_variants + outlets -> inventory_balances
product_variants + outlets -> stock_movements -> stock_movement_types
orders -> stock_reservations
stock_transfers -> stock_transfer_lines
stocktakes -> stocktake_lines
```

### Key points

- balances are per outlet and variant
- movements are authoritative history
- reservations support order fulfillment readiness
- transfers and stocktakes use header-line structure

## 6. Customers and memberships

```text id="5f6zqf"
tenants -> customers
customers -> customer_auth_accounts -> customer_auth_identities
customers -> customer_memberships -> membership_tiers
customers -> customer_addresses
customer_auth_accounts -> customer_otp_verifications -> otp_channels / otp_purposes
```

### Key points

- customer identity is tenant-scoped
- auth accounts and auth identities remain tenant-aware
- memberships are one-per-customer-per-tenant
- addresses are reusable customer-owned records

## 7. POS sales

```text id="y1jj24"
tenants + outlets -> tills -> till_sessions
till_sessions -> sales -> sale_lines
till_sessions -> cash_movements -> cash_movement_types
sales -> payments via sale_payment_allocations
```

### Key points

- POS uses till and till-session structure
- sale lines target variants
- cash movements are separate from sale payment lines
- POS payment allocations are explicit

## 8. E-Commerce orders

```text id="4o13kw"
customers -> carts -> cart_items
customers -> orders -> order_items -> deliveries -> delivery_items -> delivery_tracking
orders -> order_addresses
orders -> order_status_history
orders -> payments via order_payment_allocations
```

### Key points

- carts support customer or guest flow
- orders carry status, payment status, and fulfillment status
- delivery data is separate from order header
- order items are variant-based

## 9. Discounts and coupons

```text id="zlgua7"
discount_requests -> source sale/order
discount_applications -> source sale/order
coupons -> coupon_redemptions
discount types / scopes support request and application flows
```

### Key points

- approval requests and actual applications are separate
- coupon master and coupon redemption are separate
- source document can be sale or order

## 10. Payments, refunds, and allocations

```text id="p43a4j"
payments -> payment_transactions
sales <-> payments via sale_payment_allocations
orders <-> payments via order_payment_allocations
refunds -> original_payment_id
refunds -> refund_payment_id
returns / exchanges -> refund or payment allocation tables
```

### Key points

- `payments` is the unified payment record
- provider events are stored in `payment_transactions`
- refunds are linked explicitly to original and outbound payment context
- sales, orders, returns, and exchanges use dedicated allocation records

## 11. Returns and exchanges

```text id="w4z17w"
returns -> return_lines
returns -> return_refund_allocations -> refunds
returns -> exchanges -> exchange_lines
exchanges -> exchange_payment_allocations -> payments
exchanges -> exchange_refund_allocations -> refunds
```

### Key points

- returns can originate from sale or order
- exchanges are created from returns
- stock and money movement remain explicit

## 12. Cross-cutting support data

| Area | Main entities |
|---|---|
| Tax | `tax_rates`, `tax_classes` |
| Receipts | `receipts` |
| Audit | `audit_logs` |
| Configuration | `feature_flags`, `ui_themes`, `tenant_settings` |
| Reviews | `reviews` |
| Delivery options | `delivery_option_types` |

## Related documents

- [database-overview.md](./database-overview.md)
- [schema-principles.md](./schema-principles.md)
- [tenant-consistency-rules.md](./tenant-consistency-rules.md)
- [../08-modules/README.md](../08-modules/README.md)
