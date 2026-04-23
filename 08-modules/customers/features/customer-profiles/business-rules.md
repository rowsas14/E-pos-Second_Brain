<!--
meta:
  title: Customers / Customer Profiles / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [customers, customer-profiles, business-rules]
-->
> Hub: [[10-modules/customers/features/customer-profiles/overview]]

# Customer Profiles - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Customer Profiles** feature inside the **Customers** module.

## Core rules
- customer belongs to one tenant
- normalized email and phone are unique within tenant when present
- same email may exist in another tenant as a separate customer

## Why these rules matter
Customer identity is business-owned per tenant, not globally merged across all tenants in the platform.

## Related feature files
- [[10-modules/customers/features/customer-profiles/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/customers/features/customer-auth/overview|Customer Auth]]
- [[10-modules/customers/features/customer-addresses/overview|Customer Addresses]]
- [[10-modules/memberships/features/customer-memberships/overview|Customer Memberships]]

## Recommended reading order
Read after [[10-modules/customers/features/customer-profiles/overview]], then before [[application]], [[api]], and [[validations]].
