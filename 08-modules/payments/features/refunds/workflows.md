<!--
meta:
  title: Payments / Refunds / Workflows
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, refunds, workflows]
-->
> Hub: [[10-modules/payments/features/refunds/overview]]

# Refunds - Workflows

## Purpose
This file captures the operational **workflow** for **Refunds** across user, system, and integration steps.

## Main workflows
- create refund request/result from return or cancellation
- issue outbound payment
- allocate refund to return or exchange document

## Workflow dependencies
- [[business-rules]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[edge-cases]]

## Related features
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]
- [[10-modules/payments/features/payments/overview|Payments]]

## Recommended reading order
Read after [[10-modules/payments/features/refunds/overview]] and [[business-rules]]; combine with [[application]] for end-to-end implementation.
