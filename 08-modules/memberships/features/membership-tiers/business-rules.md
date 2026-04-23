<!--
meta:
  title: Memberships / Membership Tiers / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [memberships, membership-tiers, business-rules]
-->
> Hub: [[10-modules/memberships/features/membership-tiers/overview]]

# Membership Tiers - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Membership Tiers** feature inside the **Memberships** module.

## Core rules
- tier code is unique per tenant
- points multiplier drives loyalty calculations where enabled
- inactive tiers should not be assigned to new memberships

## Why these rules matter
The platform needs a tenant-specific membership foundation without assuming one global loyalty identity.

## Related feature files
- [[10-modules/memberships/features/membership-tiers/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/memberships/features/customer-memberships/overview|Customer Memberships]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]

## Recommended reading order
Read after [[10-modules/memberships/features/membership-tiers/overview]], then before [[application]], [[api]], and [[validations]].
