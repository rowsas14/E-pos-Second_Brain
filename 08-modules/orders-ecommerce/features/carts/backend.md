<!--
meta:
  title: Orders E-Commerce / Carts / Backend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [orders-ecommerce, carts, backend]
-->
> Hub: [[10-modules/orders-ecommerce/features/carts/overview]]

# Carts - Backend

## Purpose
This file captures **backend** implementation details for the .NET **Clean Architecture** solution.

## Backend implementation notes
- cart service should reprice safely and keep cart_item uniqueness by variant

## Expected code areas
- **Domain** model or domain service where core rule belongs
- **Application** service/use case orchestration
- **Infrastructure** persistence and external **integration**
- **Repository**, **validation**, and transaction boundaries aligned to the feature

## Related feature files
- [[10-modules/orders-ecommerce/features/carts/overview]]
- [[application]]
- [[data-model]]
- [[validations]]
- [[edge-cases]]

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/pricing/features/price-lists/overview|Price Lists]]
- [[10-modules/catalog/features/variants/overview|Variants]]

## Recommended reading order
Read after [[application]], [[data-model]], and [[validations]].
