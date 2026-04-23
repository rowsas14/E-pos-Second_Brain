<!--
meta:
  title: Reporting / Daily Sales Reporting / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [reporting, daily-sales-reporting, edge-cases]
-->
> Hub: [[10-modules/reporting/features/daily-sales-reporting/overview]]

# Daily Sales Reporting - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Daily Sales Reporting**.

## Edge cases
- sales completed near day boundary with outlet timezone difference

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/reporting/features/daily-sales-reporting/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/payments/features/payments/overview|Payments]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
