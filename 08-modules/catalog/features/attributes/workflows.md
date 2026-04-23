<!--
meta:
  title: Catalog / Attributes / Workflows
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, attributes, workflows]
-->

# Attributes - Workflows

Back to [[overview]]

## Purpose
This file summarizes the main business and system workflows for **Attributes**.

## Primary workflows
- create attribute
- add/select allowed values
- map attribute to categories
- assign selected values to variants

## Typical flow pattern
1. tenant admin or authorized catalog operator opens the feature
2. system loads tenant-scoped reference data
3. user submits create or update input
4. system validates tenant ownership and business rules
5. feature records are created or updated
6. dependent catalog views or downstream consumers read the updated state

## Downstream effects
- POS quick search and sellability may change depending on feature
- storefront listing and filters may change
- pricing, inventory, and transaction flows may read the updated catalog structure

## Related files
- [[business-rules]]
- [[application]]
- [[frontend]]
- [[03-user-flows/tenant-admin/README]]
