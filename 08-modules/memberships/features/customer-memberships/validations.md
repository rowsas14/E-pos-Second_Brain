<!--
meta:
  title: Memberships / Customer Memberships / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [memberships, customer-memberships, validations]
-->
> Hub: [[10-modules/memberships/features/customer-memberships/overview]]

# Customer Memberships - Validations

## Purpose
This file records input, business, and **workflow** validations for **Customer Memberships**.

## Validation rules
- reject second active membership for same customer in same tenant
- validate membership number uniqueness

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/memberships/features/membership-tiers/overview|Membership Tiers]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]
- [[10-modules/reporting/features/daily-sales-reporting/overview|Daily Sales Reporting]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
