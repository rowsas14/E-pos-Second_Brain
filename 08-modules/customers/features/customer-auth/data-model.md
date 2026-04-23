<!--
meta:
  title: Customers / Customer Auth / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [customers, customer-auth, data-model]
-->
> Hub: [[10-modules/customers/features/customer-auth/overview]]

# Customer Auth - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Customer Auth**.

## Primary entities
- customer_auth_accounts
- customer_auth_identities

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/customers/features/customer-auth/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]
- [[10-modules/customers/features/customer-addresses/overview|Customer Addresses]]
- [[10-modules/memberships/features/customer-memberships/overview|Customer Memberships]]

## Recommended reading order
Read after [[10-modules/customers/features/customer-auth/overview]] and [[business-rules]], then before [[application]] and [[api]].
