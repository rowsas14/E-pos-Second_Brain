<!--
meta:
  title: Payments / Provider Transactions / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, provider-transactions, validations]
-->
> Hub: [[10-modules/payments/features/provider-transactions/overview]]

# Provider Transactions - Validations

## Purpose
This file records input, business, and **workflow** validations for **Provider Transactions**.

## Validation rules
- validate payment reference exists
- preserve provider_transaction_id when available

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/payments/features/payments/overview|Payments]]
- [[10-modules/payments/features/refunds/overview|Refunds]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
