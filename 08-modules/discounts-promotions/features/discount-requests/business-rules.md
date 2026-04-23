<!--
meta:
  title: Discounts & Promotions / Discount Requests / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [discounts-promotions, discount-requests, business-rules]
-->
> Hub: [[10-modules/discounts-promotions/features/discount-requests/overview]]

# Discount Requests - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Discount Requests** feature inside the **Discounts & Promotions** module.

## Core rules
- request can target sale or order, and optionally a line
- status is pending, approved, rejected, or expired
- request stores requested value, scope, type, and reason

## Why these rules matter
The business wants approval-based discounting rather than uncontrolled manual reductions.

## Related feature files
- [[10-modules/discounts-promotions/features/discount-requests/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/discounts-promotions/features/discount-applications/overview|Discount Applications]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/discounts-promotions/features/discount-requests/overview]], then before [[application]], [[api]], and [[validations]].
