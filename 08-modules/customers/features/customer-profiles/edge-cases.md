<!--
meta:
  title: Customers / Customer Profiles / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [customers, customer-profiles, edge-cases]
-->
> Hub: [[10-modules/customers/features/customer-profiles/overview]]

# Customer Profiles - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Customer Profiles**.

## Edge cases
- same phone reused by household members
- guest checkout later converted into a customer account

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/customers/features/customer-profiles/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/customers/features/customer-auth/overview|Customer Auth]]
- [[10-modules/customers/features/customer-addresses/overview|Customer Addresses]]
- [[10-modules/memberships/features/customer-memberships/overview|Customer Memberships]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
