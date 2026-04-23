<!--
meta:
  title: Memberships / Membership Tiers / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [memberships, membership-tiers, application]
-->
> Hub: [[10-modules/memberships/features/membership-tiers/overview]]

# Membership Tiers - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Membership Tiers**.

## Main orchestration paths
- create tier
- change points multiplier or status

## Application-layer notes
- keep tier logic simple until advanced loyalty rules are introduced

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/memberships/features/customer-memberships/overview|Customer Memberships]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
