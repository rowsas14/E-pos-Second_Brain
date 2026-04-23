<!--
meta:
  title: Memberships / Membership Tiers / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [memberships, membership-tiers, data-model]
-->
> Hub: [[10-modules/memberships/features/membership-tiers/overview]]

# Membership Tiers - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Membership Tiers**.

## Primary entities
- membership_tiers

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/memberships/features/membership-tiers/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/memberships/features/customer-memberships/overview|Customer Memberships]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]

## Recommended reading order
Read after [[10-modules/memberships/features/membership-tiers/overview]] and [[business-rules]], then before [[application]] and [[api]].
