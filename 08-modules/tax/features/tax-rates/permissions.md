<!--
meta:
  title: Tax / Tax Rates / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tax, tax-rates, permissions]
-->
> Hub: [[10-modules/tax/features/tax-rates/overview]]

# Tax Rates - Permissions

## Purpose
This file explains role and permission behavior for **Tax Rates**.

## Permission behavior
- tenant admin manages tax rates

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/tax/features/tax-rates/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/tax/features/tax-classes/overview|Tax Classes]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/tax/features/tax-rates/overview]] and before exposing [[api]] or [[frontend]] changes.
