<!--
meta:
  title: Payments / Refunds / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, refunds, validations]
-->
> Hub: [[10-modules/payments/features/refunds/overview]]

# Refunds - Validations

## Purpose
This file records input, business, and **workflow** validations for **Refunds**.

## Validation rules
- validate original payment reference and refundable balance
- ensure refund payment row uses outbound direction and refund purpose

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]
- [[10-modules/payments/features/payments/overview|Payments]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
