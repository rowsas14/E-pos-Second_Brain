<!--
meta:
  title: Customers / Customer Addresses / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [customers, customer-addresses, data-model]
-->
> Hub: [[10-modules/customers/features/customer-addresses/overview]]

# Customer Addresses - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Customer Addresses**.

## Primary entities
- customer_addresses
- order_addresses

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/customers/features/customer-addresses/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]

## Recommended reading order
Read after [[10-modules/customers/features/customer-addresses/overview]] and [[business-rules]], then before [[application]] and [[api]].
