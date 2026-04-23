<!--
meta:
  title: Memberships / Customer Memberships / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [memberships, customer-memberships, data-model]
-->
> Hub: [[10-modules/memberships/features/customer-memberships/overview]]

# Customer Memberships - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Customer Memberships**.

## Primary entities
- customer_memberships

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/memberships/features/customer-memberships/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/memberships/features/membership-tiers/overview|Membership Tiers]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]
- [[10-modules/reporting/features/daily-sales-reporting/overview|Daily Sales Reporting]]

## Recommended reading order
Read after [[10-modules/memberships/features/customer-memberships/overview]] and [[business-rules]], then before [[application]] and [[api]].
