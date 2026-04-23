<!--
meta:
  title: Sales POS / Hold & Recall Sales / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, hold-recall-sales, application]
-->
> Hub: [[10-modules/sales-pos/features/hold-recall-sales/overview]]

# Hold & Recall Sales - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Hold & Recall Sales**.

## Main orchestration paths
- hold current sale
- search held sale
- recall and continue checkout

## Application-layer notes
- keep status handling explicit: open, suspended, completed, voided

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
