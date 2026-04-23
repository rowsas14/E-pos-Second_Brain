<!--
meta:
  title: Receipts / Receipt Generation / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [receipts, receipt-generation, application]
-->
> Hub: [[10-modules/receipts/features/receipt-generation/overview]]

# Receipt Generation - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Receipt Generation**.

## Main orchestration paths
- generate receipt on document completion
- reprint or retrieve stored receipt

## Application-layer notes
- generate from stable transaction snapshot, not live mutable reads

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
