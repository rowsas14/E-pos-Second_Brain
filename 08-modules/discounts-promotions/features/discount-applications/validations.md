<!--
meta:
  title: Discounts & Promotions / Discount Applications / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [discounts-promotions, discount-applications, validations]
-->
> Hub: [[10-modules/discounts-promotions/features/discount-applications/overview]]

# Discount Applications - Validations

## Purpose
This file records input, business, and **workflow** validations for **Discount Applications**.

## Validation rules
- ensure compatible scope and source document
- prevent duplicate application of same approved request where not allowed

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/discounts-promotions/features/discount-requests/overview|Discount Requests]]
- [[10-modules/discounts-promotions/features/coupons/overview|Coupons]]
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
