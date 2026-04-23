<!--
meta:
  title: Catalog / Categories / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, categories, permissions]
-->

# Categories - Permissions

Back to [[overview]]

## Purpose
This file defines role and permission expectations for **Categories**.

## Permission model
- tenant admin or catalog manager can maintain categories
- cashiers and customers only consume category output

## General rules
- platform admin should only intervene through platform-side support or tenant onboarding contexts, not daily catalog maintenance
- tenant admin owns final tenant catalog responsibility
- permissions must remain tenant-scoped and, where relevant, outlet-aware through higher-level access model
- customer-facing and cashier-facing consumption does not imply write access

## Sensitive actions
- activation, deactivation, archival, and structural remapping should be auditable
- bulk changes should follow the same tenant and role rules as manual changes

## Related files
- [[business-rules]]
- [[workflows]]
- [[07-api/auth-and-authorization]]
- [[02-domain/tenancy-model]]
