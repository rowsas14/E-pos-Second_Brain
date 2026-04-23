<!--
meta:
  title: Customers / Customer Profiles / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [customers, customer-profiles, data-model]
-->
> Hub: [[10-modules/customers/features/customer-profiles/overview]]

# Customer Profiles - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Customer Profiles**.

## Primary entities
- customers

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/customers/features/customer-profiles/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/customers/features/customer-auth/overview|Customer Auth]]
- [[10-modules/customers/features/customer-addresses/overview|Customer Addresses]]
- [[10-modules/memberships/features/customer-memberships/overview|Customer Memberships]]

## Recommended reading order
Read after [[10-modules/customers/features/customer-profiles/overview]] and [[business-rules]], then before [[application]] and [[api]].
