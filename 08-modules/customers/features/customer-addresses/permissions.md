<!--
meta:
  title: Customers / Customer Addresses / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [customers, customer-addresses, permissions]
-->
> Hub: [[10-modules/customers/features/customer-addresses/overview]]

# Customer Addresses - Permissions

## Purpose
This file explains role and permission behavior for **Customer Addresses**.

## Permission behavior
- customer self-service and authorized support/admin updates

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/customers/features/customer-addresses/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]

## Recommended reading order
Read after [[10-modules/customers/features/customer-addresses/overview]] and before exposing [[api]] or [[frontend]] changes.
