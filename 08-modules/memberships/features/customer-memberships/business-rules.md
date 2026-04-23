<!--
meta:
  title: Memberships / Customer Memberships / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [memberships, customer-memberships, business-rules]
-->
> Hub: [[10-modules/memberships/features/customer-memberships/overview]]

# Customer Memberships - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Customer Memberships** feature inside the **Memberships** module.

## Core rules
- unique membership per customer per tenant
- membership number unique within tenant
- customer, tier, and membership tenant must align

## Why these rules matter
Membership is explicitly tenant-specific in the operating model and must not be merged globally.

## Related feature files
- [[10-modules/memberships/features/customer-memberships/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/memberships/features/membership-tiers/overview|Membership Tiers]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]
- [[10-modules/reporting/features/daily-sales-reporting/overview|Daily Sales Reporting]]

## Recommended reading order
Read after [[10-modules/memberships/features/customer-memberships/overview]], then before [[application]], [[api]], and [[validations]].
