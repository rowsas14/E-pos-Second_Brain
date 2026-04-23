<!--
meta:
  title: Catalog / Categories / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, categories, application]
-->

# Categories - Application

Back to [[overview]]

## Purpose
This file explains how the `Application` layer should orchestrate the **Categories** feature.

## Primary use cases
- create/update category
- move category in hierarchy
- map attributes to category
- activate/deactivate category

## Orchestration rules
- load tenant-safe master data first
- validate same-tenant references before mutation
- use domain entities or domain rules for stable business invariants
- coordinate repositories; do not push workflow sequencing into controllers or repositories
- write audit entries for sensitive catalog changes when required by cross-cutting rules

## Expected service composition
- application service in `Catalog`
- validator for request and business checks
- repository access limited to this feature and closely related catalog data
- optional integration hook for storage or onboarding enrichment where relevant

## Transaction notes
- keep one business mutation atomic when the change affects multiple rows in this feature
- do not commit half-completed catalog setup flows if referential integrity or primary-flag rules would break

## Related files
- [[business-rules]]
- [[data-model]]
- [[validations]]
- [[backend]]
- [[08-backend/application-layer-rules]]
- [[08-backend/service-composition-rules]]
