<!--
meta:
  title: Payments / Provider Transactions / Overview
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, provider-transactions, overview]
-->
# Provider Transactions

## Purpose
Gateway/provider event log for authorization, capture, refund, webhook, and failure events.

## Why this feature exists
External payment integrations need raw event storage for reconciliation and debugging.

## Scope
- store auth/capture response
- store webhook callback
- store failure/refund event

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
- [[10-modules/payments/features/payments/overview|Payments]]
- [[10-modules/payments/features/refunds/overview|Refunds]]

## Work this feature supports
- Product-specific implementation and change planning
- Business-rule clarification before coding
- API, database, backend, and frontend alignment for the same feature
- Bug analysis and controlled change history at feature level

## Recommended reading order
1. [[10-modules/payments/features/provider-transactions/overview]]
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
