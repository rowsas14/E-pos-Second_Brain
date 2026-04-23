<!--
meta:
  title: Returns & Exchanges / Exchanges / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [returns-exchanges, exchanges, business-rules]
-->
> Hub: [[10-modules/returns-exchanges/features/exchanges/overview]]

# Exchanges - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Exchanges** feature inside the **Returns & Exchanges** module.

## Core rules
- exchange is created from one return
- difference_direction is collect, refund, or none
- exchange number unique within tenant

## Why these rules matter
Exchange is not just a return plus sale UI shortcut; it has its own value reconciliation and audit trail.

## Related feature files
- [[10-modules/returns-exchanges/features/exchanges/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]
- [[10-modules/payments/features/refunds/overview|Refunds]]

## Recommended reading order
Read after [[10-modules/returns-exchanges/features/exchanges/overview]], then before [[application]], [[api]], and [[validations]].
