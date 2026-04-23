<!--
meta:
  title: Orders E-Commerce / Product Reviews / Backend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [orders-ecommerce, product-reviews, backend]
-->
> Hub: [[10-modules/orders-ecommerce/features/product-reviews/overview]]

# Product Reviews - Backend

## Purpose
This file captures **backend** implementation details for the .NET **Clean Architecture** solution.

## Backend implementation notes
- review moderation can remain simple until richer anti-abuse rules are needed

## Expected code areas
- **Domain** model or domain service where core rule belongs
- **Application** service/use case orchestration
- **Infrastructure** persistence and external **integration**
- **Repository**, **validation**, and transaction boundaries aligned to the feature

## Related feature files
- [[10-modules/orders-ecommerce/features/product-reviews/overview]]
- [[application]]
- [[data-model]]
- [[validations]]
- [[edge-cases]]

## Related features
- [[10-modules/catalog/features/products/overview|Products]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]

## Recommended reading order
Read after [[application]], [[data-model]], and [[validations]].
