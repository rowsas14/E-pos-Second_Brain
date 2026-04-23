<!--
meta:
  title: Platform Administration / Tenant Lifecycle / Bugs
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [platform-administration, tenant-lifecycle, bugs]
-->
> Hub: [[10-modules/platform-administration/features/tenant-lifecycle/overview]]

# Tenant Lifecycle - Bugs

## Purpose
This file tracks known issues, recurring defects, and defect patterns for **Tenant Lifecycle**.

## Current watch list
- watch for background jobs continuing under suspended tenant context
- watch for cache entries still serving tenant catalog after suspension

## Usage rule
- Record confirmed recurring defects here.
- Link bug fixes to [[changelog]] after release.
- Use this file during regression testing and production issue analysis.

## Related feature files
- [[10-modules/platform-administration/features/tenant-lifecycle/overview]]
- [[edge-cases]]
- [[backend]]
- [[frontend]]
- [[changelog]]

## Recommended reading order
Read when fixing defects or verifying regression risk after changes.
