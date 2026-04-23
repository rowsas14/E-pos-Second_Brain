<!--
meta:
  title: Returns & Exchanges / Exchanges / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [returns-exchanges, exchanges, validations]
-->
> Hub: [[10-modules/returns-exchanges/features/exchanges/overview]]

# Exchanges - Validations

## Purpose
This file records input, business, and **workflow** validations for **Exchanges**.

## Validation rules
- ensure source return exists and is eligible
- validate difference total against old/new value totals

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]
- [[10-modules/payments/features/refunds/overview|Refunds]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
