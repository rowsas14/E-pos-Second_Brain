<!--
meta:
  title: Platform Administration / Tenant Lifecycle / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [platform-administration, tenant-lifecycle, application]
-->
> Hub: [[10-modules/platform-administration/features/tenant-lifecycle/overview]]

# Tenant Lifecycle - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Tenant Lifecycle**.

## Main orchestration paths
- activate tenant after onboarding
- temporarily suspend tenant operations
- reactivate tenant after issue resolution

## Application-layer notes
- tenant status should be enforced by tenant-resolution middleware and authorization checks
- keep lifecycle transitions in a dedicated service to centralize side effects

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/platform-administration/features/tenant-onboarding/overview|Tenant Onboarding]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
