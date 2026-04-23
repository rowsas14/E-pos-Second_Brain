<!--
meta:
  title: Receipts / Receipt Delivery / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [receipts, receipt-delivery, application]
-->
> Hub: [[10-modules/receipts/features/receipt-delivery/overview]]

# Receipt Delivery - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Receipt Delivery**.

## Main orchestration paths
- print thermal receipt
- email receipt
- download PDF/A4 render

## Application-layer notes
- device/integration adapters belong in infrastructure; receipt service only coordinates

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/receipts/features/receipt-generation/overview|Receipt Generation]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
