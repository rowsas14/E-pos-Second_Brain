<!--
meta:
  title: Discounts & Promotions / Coupons / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [discounts-promotions, coupons, validations]
-->
> Hub: [[10-modules/discounts-promotions/features/coupons/overview]]

# Coupons - Validations

## Purpose
This file records input, business, and **workflow** validations for **Coupons**.

## Validation rules
- validate date window and usage limits
- validate rule_payload before redemption

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/discounts-promotions/features/discount-applications/overview|Discount Applications]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
