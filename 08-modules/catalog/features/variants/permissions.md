<!--
meta:
  title: Catalog / Variants / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, variants, permissions]
-->

# Variants - Permissions

Back to [[overview]]

## Purpose
This file defines role and permission expectations for **Variants**.

## Permission model
- tenant admin and catalog manager manage variants
- cashier and online customer flows consume active sellable variants only

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
