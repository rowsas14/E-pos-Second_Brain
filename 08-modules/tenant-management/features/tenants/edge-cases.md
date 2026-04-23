<!--
meta:
  title: Tenant Management / Tenants / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tenant-management, tenants, edge-cases]
-->
> Hub: [[10-modules/tenant-management/features/tenants/overview]]

# Tenants - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Tenants**.

## Edge cases
- tenant changes timezone after outlets already exist
- tenant switches from single-channel to hybrid mode

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/tenant-management/features/tenants/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/settings-configuration/features/tenant-settings/overview|Tenant Settings]]
- [[10-modules/settings-configuration/features/ui-themes/overview|UI Themes]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
