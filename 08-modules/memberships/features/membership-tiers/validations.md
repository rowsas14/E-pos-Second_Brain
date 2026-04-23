<!--
meta:
  title: Memberships / Membership Tiers / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [memberships, membership-tiers, validations]
-->
> Hub: [[10-modules/memberships/features/membership-tiers/overview]]

# Membership Tiers - Validations

## Purpose
This file records input, business, and **workflow** validations for **Membership Tiers**.

## Validation rules
- reject duplicate tier code within tenant
- validate positive multiplier policy

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/memberships/features/customer-memberships/overview|Customer Memberships]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
