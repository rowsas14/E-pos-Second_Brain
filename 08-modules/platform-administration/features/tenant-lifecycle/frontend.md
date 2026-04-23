<!--
meta:
  title: Platform Administration / Tenant Lifecycle / Frontend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [platform-administration, tenant-lifecycle, frontend]
-->
> Hub: [[10-modules/platform-administration/features/tenant-lifecycle/overview]]

# Tenant Lifecycle - Frontend

## Purpose
This file captures **frontend** behavior, screens, and UI integration points for **Tenant Lifecycle**.

## Frontend behavior notes
- platform admin status dashboard with clear reason and timestamp
- tenant admin area should show locked/suspended banners rather than generic auth failure

## Frontend dependency map
- [[10-modules/platform-administration/features/tenant-lifecycle/overview]] for scope
- [[workflows]] for user flow
- [[permissions]] for access behavior
- [[api]] for contract usage
- [[edge-cases]] for failure state design

## Related features
- [[10-modules/platform-administration/features/tenant-onboarding/overview|Tenant Onboarding]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/platform-administration/features/tenant-lifecycle/overview]], [[workflows]], [[permissions]], and [[api]].
