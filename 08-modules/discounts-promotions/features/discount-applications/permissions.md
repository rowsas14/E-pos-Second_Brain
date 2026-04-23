<!--
meta:
  title: Discounts & Promotions / Discount Applications / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [discounts-promotions, discount-applications, permissions]
-->
> Hub: [[10-modules/discounts-promotions/features/discount-applications/overview]]

# Discount Applications - Permissions

## Purpose
This file explains role and permission behavior for **Discount Applications**.

## Permission behavior
- authorized cashier/manager/system applies discount according to policy

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/discounts-promotions/features/discount-applications/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/discounts-promotions/features/discount-requests/overview|Discount Requests]]
- [[10-modules/discounts-promotions/features/coupons/overview|Coupons]]
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]

## Recommended reading order
Read after [[10-modules/discounts-promotions/features/discount-applications/overview]] and before exposing [[api]] or [[frontend]] changes.
