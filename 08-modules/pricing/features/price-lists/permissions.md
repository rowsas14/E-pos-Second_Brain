<!--
meta:
  title: Pricing / Price Lists / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [pricing, price-lists, permissions]
-->
> Hub: [[10-modules/pricing/features/price-lists/overview]]

# Price Lists - Permissions

## Purpose
This file explains role and permission behavior for **Price Lists**.

## Permission behavior
- pricing or tenant admin manages price lists

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/pricing/features/price-lists/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/catalog/features/variants/overview|Variants]]
- [[10-modules/pricing/features/outlet-price-overrides/overview|Outlet Price Overrides]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/pricing/features/price-lists/overview]] and before exposing [[api]] or [[frontend]] changes.
