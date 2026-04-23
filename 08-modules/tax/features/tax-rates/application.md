<!--
meta:
  title: Tax / Tax Rates / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tax, tax-rates, application]
-->
> Hub: [[10-modules/tax/features/tax-rates/overview]]

# Tax Rates - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Tax Rates**.

## Main orchestration paths
- create tax rate
- expire and replace with new effective rate

## Application-layer notes
- transaction modules must snapshot applied rate id and value rather than re-querying later

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/tax/features/tax-classes/overview|Tax Classes]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
