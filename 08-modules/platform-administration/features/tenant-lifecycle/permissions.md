<!--
meta:
  title: Platform Administration / Tenant Lifecycle / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [platform-administration, tenant-lifecycle, permissions]
-->
> Hub: [[10-modules/platform-administration/features/tenant-lifecycle/overview]]

# Tenant Lifecycle - Permissions

## Purpose
This file explains role and permission behavior for **Tenant Lifecycle**.

## Permission behavior
- platform admin controls tenant lifecycle
- tenant admin can view status but should not self-reactivate if the platform locked the tenant

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/platform-administration/features/tenant-lifecycle/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/platform-administration/features/tenant-onboarding/overview|Tenant Onboarding]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/platform-administration/features/tenant-lifecycle/overview]] and before exposing [[api]] or [[frontend]] changes.
