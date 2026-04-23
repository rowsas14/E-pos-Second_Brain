<!--
meta:
  title: Sales POS / POS Checkout / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, pos-checkout, application]
-->
> Hub: [[10-modules/sales-pos/features/pos-checkout/overview]]

# POS Checkout - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **POS Checkout**.

## Main orchestration paths
- scan or search variant
- edit cart line quantity/discount
- collect payment and complete sale

## Application-layer notes
- checkout orchestrates pricing snapshot, stock movement, payment allocation, and receipt generation
- idempotency is critical on complete action

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/catalog/features/variants/overview|Variants]]
- [[10-modules/pricing/features/price-lists/overview|Price Lists]]
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]
- [[10-modules/receipts/features/receipt-generation/overview|Receipt Generation]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
