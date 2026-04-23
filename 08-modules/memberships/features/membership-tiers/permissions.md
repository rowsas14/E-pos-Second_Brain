<!--
meta:
  title: Memberships / Membership Tiers / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [memberships, membership-tiers, permissions]
-->
> Hub: [[10-modules/memberships/features/membership-tiers/overview]]

# Membership Tiers - Permissions

## Purpose
This file explains role and permission behavior for **Membership Tiers**.

## Permission behavior
- tenant admin manages membership tiers

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/memberships/features/membership-tiers/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/memberships/features/customer-memberships/overview|Customer Memberships]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]

## Recommended reading order
Read after [[10-modules/memberships/features/membership-tiers/overview]] and before exposing [[api]] or [[frontend]] changes.
