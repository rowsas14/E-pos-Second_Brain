<!--
meta:
  title: Discounts & Promotions / Discount Requests / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [discounts-promotions, discount-requests, permissions]
-->
> Hub: [[10-modules/discounts-promotions/features/discount-requests/overview]]

# Discount Requests - Permissions

## Purpose
This file explains role and permission behavior for **Discount Requests**.

## Permission behavior
- cashier/operator requests
- manager approves or rejects

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/discounts-promotions/features/discount-requests/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/discounts-promotions/features/discount-applications/overview|Discount Applications]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/discounts-promotions/features/discount-requests/overview]] and before exposing [[api]] or [[frontend]] changes.
