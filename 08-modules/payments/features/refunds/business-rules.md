<!--
meta:
  title: Payments / Refunds / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, refunds, business-rules]
-->
> Hub: [[10-modules/payments/features/refunds/overview]]

# Refunds - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Refunds** feature inside the **Payments** module.

## Core rules
- refund total against original payment cannot exceed captured amount
- refund may reference outbound refund payment row
- refund payment status is tracked independently

## Why these rules matter
Returns and cancellation flows need auditable refund state separate from the original payment capture.

## Related feature files
- [[10-modules/payments/features/refunds/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]
- [[10-modules/payments/features/payments/overview|Payments]]

## Recommended reading order
Read after [[10-modules/payments/features/refunds/overview]], then before [[application]], [[api]], and [[validations]].
