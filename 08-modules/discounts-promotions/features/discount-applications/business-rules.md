<!--
meta:
  title: Discounts & Promotions / Discount Applications / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [discounts-promotions, discount-applications, business-rules]
-->
> Hub: [[10-modules/discounts-promotions/features/discount-applications/overview]]

# Discount Applications - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Discount Applications** feature inside the **Discounts & Promotions** module.

## Core rules
- application records computed amount_applied, not only configured value
- may reference a request or coupon
- scope can be line, sale, or order

## Why these rules matter
Approved intent and applied financial effect must be stored separately for auditability.

## Related feature files
- [[10-modules/discounts-promotions/features/discount-applications/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/discounts-promotions/features/discount-requests/overview|Discount Requests]]
- [[10-modules/discounts-promotions/features/coupons/overview|Coupons]]
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]

## Recommended reading order
Read after [[10-modules/discounts-promotions/features/discount-applications/overview]], then before [[application]], [[api]], and [[validations]].
