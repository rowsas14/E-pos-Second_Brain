<!--
meta:
  title: Platform Administration / Platform Users / Overview
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [platform-administration, platform-users, overview]
-->
# Platform Users

## Purpose
Separate platform-side administrator identities used for tenant creation, activation, suspension, and emergency support. These identities are not tenant staff users.

## Why this feature exists
The project explicitly separates platform administration from tenant staff so platform operations do not leak into tenant authorization and reporting.

## Scope
- create platform admin identity
- sign in to internal control area
- suspend or reactivate internal operator access

## Navigation hub
- [[business-rules]]
- [[data-model]]
- [[application]]
- [[api]]
- [[workflows]]
- [[permissions]]
- [[validations]]
- [[edge-cases]]
- [[bugs]]
- [[changelog]]
- [[backend]]
- [[frontend]]

## Related features
- [[10-modules/platform-administration/features/tenant-onboarding/overview|Tenant Onboarding]]
- [[10-modules/platform-administration/features/tenant-lifecycle/overview|Tenant Lifecycle]]
- [[10-modules/audit-compliance/features/audit-logs/overview|Audit Logs]]

## Work this feature supports
- Product-specific implementation and change planning
- Business-rule clarification before coding
- API, database, backend, and frontend alignment for the same feature
- Bug analysis and controlled change history at feature level

## Recommended reading order
1. [[10-modules/platform-administration/features/platform-users/overview]]
2. [[business-rules]]
3. [[data-model]]
4. [[application]]
5. [[api]]
6. [[permissions]]
7. [[validations]]
8. [[workflows]]
9. [[edge-cases]]
10. [[backend]]
11. [[frontend]]
12. [[bugs]]
13. [[changelog]]
