<!--
meta:
  title: Reporting / Payment & Return Reporting / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [reporting, payment-return-reporting, edge-cases]
-->
> Hub: [[10-modules/reporting/features/payment-return-reporting/overview]]

# Payment & Return Reporting - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Payment & Return Reporting**.

## Edge cases
- partial refund and exchange difference create confusing net views if not separated

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/reporting/features/payment-return-reporting/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/payments/features/refunds/overview|Refunds]]
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/discounts-promotions/features/discount-applications/overview|Discount Applications]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
