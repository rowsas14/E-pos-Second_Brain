<!--
meta:
  title: Customers / Customer Addresses / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [customers, customer-addresses, business-rules]
-->
> Hub: [[10-modules/customers/features/customer-addresses/overview]]

# Customer Addresses - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Customer Addresses** feature inside the **Customers** module.

## Core rules
- address belongs to customer and tenant
- address_type is billing, shipping, or other
- default handling should remain clear at customer level

## Why these rules matter
E-Commerce checkout and order snapshots need durable source addresses while letting customers maintain reusable address book entries.

## Related feature files
- [[10-modules/customers/features/customer-addresses/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]

## Recommended reading order
Read after [[10-modules/customers/features/customer-addresses/overview]], then before [[application]], [[api]], and [[validations]].
