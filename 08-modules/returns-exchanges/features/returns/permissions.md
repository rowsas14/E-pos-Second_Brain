<!--
meta:
  title: Returns & Exchanges / Returns / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [returns-exchanges, returns, permissions]
-->
> Hub: [[10-modules/returns-exchanges/features/returns/overview]]

# Returns - Permissions

## Purpose
This file explains role and permission behavior for **Returns**.

## Permission behavior
- cashier or operations staff can initiate based on policy
- manager approval may be required for refunds or exceptions

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/returns-exchanges/features/returns/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/payments/features/refunds/overview|Refunds]]
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]

## Recommended reading order
Read after [[10-modules/returns-exchanges/features/returns/overview]] and before exposing [[api]] or [[frontend]] changes.
