<!--
meta:
  title: Discounts & Promotions / Discount Applications / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [discounts-promotions, discount-applications, edge-cases]
-->
> Hub: [[10-modules/discounts-promotions/features/discount-applications/overview]]

# Discount Applications - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Discount Applications**.

## Edge cases
- line removed after discount applied
- multiple discount sources compete on same line

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/discounts-promotions/features/discount-applications/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/discounts-promotions/features/discount-requests/overview|Discount Requests]]
- [[10-modules/discounts-promotions/features/coupons/overview|Coupons]]
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
