<!--
meta:
  title: Sales POS / Tills & Sessions / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, tills-sessions, application]
-->
> Hub: [[10-modules/sales-pos/features/tills-sessions/overview]]

# Tills & Sessions - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Tills & Sessions**.

## Main orchestration paths
- open register
- work under active session
- close and reconcile register

## Application-layer notes
- session open/close should be explicit use cases with reconciliation checks

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/sales-pos/features/cash-movements/overview|Cash Movements]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
