<!--
meta:
  title: Discounts & Promotions / Discount Requests / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [discounts-promotions, discount-requests, validations]
-->
> Hub: [[10-modules/discounts-promotions/features/discount-requests/overview]]

# Discount Requests - Validations

## Purpose
This file records input, business, and **workflow** validations for **Discount Requests**.

## Validation rules
- validate source document and optional source line existence
- validate discount type/scope combination

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/discounts-promotions/features/discount-applications/overview|Discount Applications]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
