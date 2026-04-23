<!--
meta:
  title: Customers / Customer Auth / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [customers, customer-auth, edge-cases]
-->
> Hub: [[10-modules/customers/features/customer-auth/overview]]

# Customer Auth - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Customer Auth**.

## Edge cases
- same email signs into two different tenants
- provider identity exists but customer profile is blocked

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/customers/features/customer-auth/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]
- [[10-modules/customers/features/customer-addresses/overview|Customer Addresses]]
- [[10-modules/memberships/features/customer-memberships/overview|Customer Memberships]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
