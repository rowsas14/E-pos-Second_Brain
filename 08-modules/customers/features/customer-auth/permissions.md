<!--
meta:
  title: Customers / Customer Auth / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [customers, customer-auth, permissions]
-->
> Hub: [[10-modules/customers/features/customer-auth/overview]]

# Customer Auth - Permissions

## Purpose
This file explains role and permission behavior for **Customer Auth**.

## Permission behavior
- customer self-service feature; tenant staff may assist through support flows only

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/customers/features/customer-auth/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]
- [[10-modules/customers/features/customer-addresses/overview|Customer Addresses]]
- [[10-modules/memberships/features/customer-memberships/overview|Customer Memberships]]

## Recommended reading order
Read after [[10-modules/customers/features/customer-auth/overview]] and before exposing [[api]] or [[frontend]] changes.
