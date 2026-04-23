<!--
meta:
  title: Customers / Customer Addresses / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [customers, customer-addresses, application]
-->
> Hub: [[10-modules/customers/features/customer-addresses/overview]]

# Customer Addresses - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Customer Addresses**.

## Main orchestration paths
- add address
- edit address
- choose address during checkout and snapshot into order

## Application-layer notes
- order placement must copy address snapshot rather than reference mutable address record

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
