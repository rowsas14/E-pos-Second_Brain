<!--
meta:
  title: Reporting / Daily Sales Reporting / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [reporting, daily-sales-reporting, business-rules]
-->
> Hub: [[10-modules/reporting/features/daily-sales-reporting/overview]]

# Daily Sales Reporting - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Daily Sales Reporting** feature inside the **Reporting** module.

## Core rules
- reports should resolve from authoritative transactional data
- tenant and outlet filters are mandatory for isolation and relevance

## Why these rules matter
The MVP explicitly requires daily sales and channel/outlet reporting for business operations.

## Related feature files
- [[10-modules/reporting/features/daily-sales-reporting/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/payments/features/payments/overview|Payments]]

## Recommended reading order
Read after [[10-modules/reporting/features/daily-sales-reporting/overview]], then before [[application]], [[api]], and [[validations]].
