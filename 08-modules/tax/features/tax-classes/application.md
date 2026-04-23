<!--
meta:
  title: Tax / Tax Classes / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tax, tax-classes, application]
-->
> Hub: [[10-modules/tax/features/tax-classes/overview]]

# Tax Classes - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Tax Classes**.

## Main orchestration paths
- create tax class
- assign tax class to products

## Application-layer notes
- tax class lookup should be lightweight but cached carefully

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/catalog/features/products/overview|Products]]
- [[10-modules/tax/features/tax-rates/overview|Tax Rates]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
