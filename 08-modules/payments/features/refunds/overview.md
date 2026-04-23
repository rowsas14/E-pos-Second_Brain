<!--
meta:
  title: Payments / Refunds / Overview
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, refunds, overview]
-->
# Refunds

## Purpose
Business refund records linked to original payment and optional outbound refund payment row.

## Why this feature exists
Returns and cancellation flows need auditable refund state separate from the original payment capture.

## Scope
- create refund request/result from return or cancellation
- issue outbound payment
- allocate refund to return or exchange document

## Navigation hub
- [[business-rules]]
- [[data-model]]
- [[application]]
- [[api]]
- [[workflows]]
- [[permissions]]
- [[validations]]
- [[edge-cases]]
- [[bugs]]
- [[changelog]]
- [[backend]]
- [[frontend]]

## Related features
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]
- [[10-modules/payments/features/payments/overview|Payments]]

## Work this feature supports
- Product-specific implementation and change planning
- Business-rule clarification before coding
- API, database, backend, and frontend alignment for the same feature
- Bug analysis and controlled change history at feature level

## Recommended reading order
1. [[10-modules/payments/features/refunds/overview]]
2. [[business-rules]]
3. [[data-model]]
4. [[application]]
5. [[api]]
6. [[permissions]]
7. [[validations]]
8. [[workflows]]
9. [[edge-cases]]
10. [[backend]]
11. [[frontend]]
12. [[bugs]]
13. [[changelog]]
