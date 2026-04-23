<!--
meta:
  title: Memberships / Customer Memberships / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [memberships, customer-memberships, permissions]
-->
> Hub: [[10-modules/memberships/features/customer-memberships/overview]]

# Customer Memberships - Permissions

## Purpose
This file explains role and permission behavior for **Customer Memberships**.

## Permission behavior
- tenant admin or authorized CRM/support staff manages enrollment

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/memberships/features/customer-memberships/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/memberships/features/membership-tiers/overview|Membership Tiers]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]
- [[10-modules/reporting/features/daily-sales-reporting/overview|Daily Sales Reporting]]

## Recommended reading order
Read after [[10-modules/memberships/features/customer-memberships/overview]] and before exposing [[api]] or [[frontend]] changes.
