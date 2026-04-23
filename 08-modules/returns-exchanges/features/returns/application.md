<!--
meta:
  title: Returns & Exchanges / Returns / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [returns-exchanges, returns, application]
-->
> Hub: [[10-modules/returns-exchanges/features/returns/overview]]

# Returns - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Returns**.

## Main orchestration paths
- initiate return
- receive and inspect items
- approve and refund return

## Application-layer notes
- return orchestration should coordinate inventory action and refund creation, but keep them explicit

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/payments/features/refunds/overview|Refunds]]
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
