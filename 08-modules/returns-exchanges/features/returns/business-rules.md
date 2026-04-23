<!--
meta:
  title: Returns & Exchanges / Returns / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [returns-exchanges, returns, business-rules]
-->
> Hub: [[10-modules/returns-exchanges/features/returns/overview]]

# Returns - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Returns** feature inside the **Returns & Exchanges** module.

## Core rules
- return must reference exactly one source: sale or order
- return number unique within tenant
- restock action is explicit per line

## Why these rules matter
The project explicitly models reverse flow as controlled documents instead of negative sale rows.

## Related feature files
- [[10-modules/returns-exchanges/features/returns/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/payments/features/refunds/overview|Refunds]]
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]

## Recommended reading order
Read after [[10-modules/returns-exchanges/features/returns/overview]], then before [[application]], [[api]], and [[validations]].
