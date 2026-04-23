<!--
meta:
  title: Discounts & Promotions / Coupons / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [discounts-promotions, coupons, permissions]
-->
> Hub: [[10-modules/discounts-promotions/features/coupons/overview]]

# Coupons - Permissions

## Purpose
This file explains role and permission behavior for **Coupons**.

## Permission behavior
- marketing/admin configures coupons
- customer or cashier applies code subject to rules

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/discounts-promotions/features/coupons/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/discounts-promotions/features/discount-applications/overview|Discount Applications]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/discounts-promotions/features/coupons/overview]] and before exposing [[api]] or [[frontend]] changes.
