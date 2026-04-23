<!--
meta:
  title: Platform Administration / Tenant Lifecycle / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [platform-administration, tenant-lifecycle, validations]
-->
> Hub: [[10-modules/platform-administration/features/tenant-lifecycle/overview]]

# Tenant Lifecycle - Validations

## Purpose
This file records input, business, and **workflow** validations for **Tenant Lifecycle**.

## Validation rules
- block lifecycle change if target tenant id is invalid
- prevent status transition that violates business contract rules
- ensure suspension logic is applied consistently across POS and E-Commerce APIs

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/platform-administration/features/tenant-onboarding/overview|Tenant Onboarding]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
