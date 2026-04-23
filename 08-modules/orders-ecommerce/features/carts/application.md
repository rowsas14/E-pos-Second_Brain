<!--
meta:
  title: Orders E-Commerce / Carts / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [orders-ecommerce, carts, application]
-->
> Hub: [[10-modules/orders-ecommerce/features/carts/overview]]

# Carts - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Carts**.

## Main orchestration paths
- create cart
- add/update/remove items
- convert cart into order

## Application-layer notes
- cart service should reprice safely and keep cart_item uniqueness by variant

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/pricing/features/price-lists/overview|Price Lists]]
- [[10-modules/catalog/features/variants/overview|Variants]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
