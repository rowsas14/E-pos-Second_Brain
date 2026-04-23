<!--
meta:
  title: Payments / Provider Transactions / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, provider-transactions, business-rules]
-->
> Hub: [[10-modules/payments/features/provider-transactions/overview]]

# Provider Transactions - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Provider Transactions** feature inside the **Payments** module.

## Core rules
- transaction belongs to one payment
- event_type describes provider action or callback
- raw_payload should be stored for operational review

## Why these rules matter
External payment integrations need raw event storage for reconciliation and debugging.

## Related feature files
- [[10-modules/payments/features/provider-transactions/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/payments/features/payments/overview|Payments]]
- [[10-modules/payments/features/refunds/overview|Refunds]]

## Recommended reading order
Read after [[10-modules/payments/features/provider-transactions/overview]], then before [[application]], [[api]], and [[validations]].
