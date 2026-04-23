<!--
meta:
  title: Catalog / Suppliers / Bugs
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, suppliers, bugs]
-->

# Suppliers - Bugs

Back to [[overview]]

## Purpose
This file records known defects and recurring risk patterns for **Suppliers**.

## Current status
No confirmed feature-specific production bug is recorded in this documentation set as of 2026-04-18.

## Watchlist
- duplicate master data caused by onboarding imports or inconsistent naming
- cross-tenant leakage if repository filters are missed
- stale storefront or POS lookups after master-data change
- primary-flag conflicts on image, supplier, or similar supporting records where relevant
- broken downstream assumptions when active/inactive status changes are not handled consistently

## Bug entry rule
- defect summary
- affected tenant/channel
- reproduction path
- business impact
- technical root cause
- related files updated
- release or fix reference

## Related files
- [[edge-cases]]
- [[changelog]]
- [[backend]]
- [[frontend]]
