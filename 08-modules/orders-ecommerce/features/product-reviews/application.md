<!--
meta:
  title: Orders E-Commerce / Product Reviews / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [orders-ecommerce, product-reviews, application]
-->
> Hub: [[10-modules/orders-ecommerce/features/product-reviews/overview]]

# Product Reviews - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Product Reviews**.

## Main orchestration paths
- customer submits review
- moderator approves or rejects review

## Application-layer notes
- review moderation can remain simple until richer anti-abuse rules are needed

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/catalog/features/products/overview|Products]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
