<!--
meta:
  title: Returns & Exchanges / Returns / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [returns-exchanges, returns, validations]
-->
> Hub: [[10-modules/returns-exchanges/features/returns/overview]]

# Returns - Validations

## Purpose
This file records input, business, and **workflow** validations for **Returns**.

## Validation rules
- ensure source line belongs to referenced sale/order
- validate quantity not exceeding returnable balance
- validate restock/quarantine/discard choice

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/payments/features/refunds/overview|Refunds]]
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
