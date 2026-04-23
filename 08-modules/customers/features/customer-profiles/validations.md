<!--
meta:
  title: Customers / Customer Profiles / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [customers, customer-profiles, validations]
-->
> Hub: [[10-modules/customers/features/customer-profiles/overview]]

# Customer Profiles - Validations

## Purpose
This file records input, business, and **workflow** validations for **Customer Profiles**.

## Validation rules
- reject duplicate normalized email or phone within same tenant
- track source as pos, ecommerce, import, or api

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/customers/features/customer-auth/overview|Customer Auth]]
- [[10-modules/customers/features/customer-addresses/overview|Customer Addresses]]
- [[10-modules/memberships/features/customer-memberships/overview|Customer Memberships]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
