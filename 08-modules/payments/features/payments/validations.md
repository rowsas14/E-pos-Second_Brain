<!--
meta:
  title: Payments / Payments / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, payments, validations]
-->
> Hub: [[10-modules/payments/features/payments/overview]]

# Payments - Validations

## Purpose
This file records input, business, and **workflow** validations for **Payments**.

## Validation rules
- validate compatible direction and purpose
- validate method type and status transitions
- idempotency key must be unique when used

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]
- [[10-modules/payments/features/refunds/overview|Refunds]]
- [[10-modules/payments/features/provider-transactions/overview|Provider Transactions]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
