<!--
meta:
  title: Platform Administration / Tenant Lifecycle / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [platform-administration, tenant-lifecycle, business-rules]
-->
> Hub: [[10-modules/platform-administration/features/tenant-lifecycle/overview]]

# Tenant Lifecycle - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Tenant Lifecycle** feature inside the **Platform Administration** module.

## Core rules
- tenant status is active, suspended, or inactive
- suspension must affect tenant-facing operational access without deleting business data
- status changes must be auditable and intentional

## Why these rules matter
The platform needs a controlled lifecycle for commercial operations, support, contract issues, and emergency isolation.

## Related feature files
- [[10-modules/platform-administration/features/tenant-lifecycle/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/platform-administration/features/tenant-onboarding/overview|Tenant Onboarding]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/platform-administration/features/tenant-lifecycle/overview]], then before [[application]], [[api]], and [[validations]].
