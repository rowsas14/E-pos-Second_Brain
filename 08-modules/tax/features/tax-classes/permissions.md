<!--
meta:
  title: Tax / Tax Classes / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tax, tax-classes, permissions]
-->
> Hub: [[10-modules/tax/features/tax-classes/overview]]

# Tax Classes - Permissions

## Purpose
This file explains role and permission behavior for **Tax Classes**.

## Permission behavior
- tenant admin manages tax classes

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/tax/features/tax-classes/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/catalog/features/products/overview|Products]]
- [[10-modules/tax/features/tax-rates/overview|Tax Rates]]

## Recommended reading order
Read after [[10-modules/tax/features/tax-classes/overview]] and before exposing [[api]] or [[frontend]] changes.
