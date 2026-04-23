<!--
meta:
  title: Feature Template - Data Model
  owner: Engineering / Documentation
  status: active
  last_reviewed: 2026-04-22
  tags: [template, feature-docs, data-model, schema]
-->

# Feature Data Model Template

## Purpose of this file

Use this file to describe the **feature-specific data impact**.

Document only the part of the data model that matters directly to the feature:

- entities and tables touched by the feature
- important fields relevant to the feature
- relationships
- tenant and outlet boundaries
- state or document effects
- read/write impacts
- audit/configuration impacts when relevant

## What belongs here

Include:

- feature-relevant tables or entities
- why each one matters to the feature
- key relationships used by the feature
- feature-specific field meaning
- how the feature reads or writes data
- important uniqueness, state, or consistency implications
- whether the feature depends on reference data, tenant configuration, or operational data

## What should not be repeated here

Do not restate all platform-wide schema rules here. Link to the shared data docs instead.

Examples of shared rules that should usually be linked instead of repeated:

- tenant-wide schema principles -> [../../../../04-data/schema-principles.md](../../../../04-data/schema-principles.md)
- reference data policy -> [../../../../04-data/enum-and-reference-data-policy.md](../../../../04-data/enum-and-reference-data-policy.md)
- naming rules -> [../../../../04-data/naming-conventions.md](../../../../04-data/naming-conventions.md)
- same-tenant consistency rules -> [../../../../04-data/tenant-consistency-rules.md](../../../../04-data/tenant-consistency-rules.md)

## Before filling this file, read

- [overview.md](./overview.md)
- [business-rules.md](./business-rules.md)
- [../../../../04-data/database-overview.md](../../../../04-data/database-overview.md)
- [../../../../04-data/schema-principles.md](../../../../04-data/schema-principles.md)

Read more when relevant:

- transaction-sensitive feature -> [../../../../07-backend/transaction-handling-rules.md](../../../../07-backend/transaction-handling-rules.md)
- API-heavy feature -> [api.md](./api.md)

## Project-specific guidance

This project is multi-tenant and rule-heavy. For each feature, check whether the data model must document:

- `tenant_id` scope
- outlet scope
- user scope
- customer scope
- channel scope
- variant-level sellable behavior
- payment allocation or refund linkage
- stock movement or projection impact
- separate return or exchange documents
- feature configuration or theme/setting impact

Include only the feature-relevant ones.

## Recommended structure

## Feature data summary

Describe the feature’s data footprint in plain language.

## Main entities / tables

| Entity or table | Role in feature | Read / write | Notes |
|---|---|---|---|
| `[name]` | `[why it matters]` | `[R/W]` | `[notes]` |

## Key relationships

| From | To | Relationship | Why it matters |
|---|---|---|---|
| `[A]` | `[B]` | `[1:1 / 1:M / M:M]` | `[reason]` |

## Important fields

List only fields that matter to understanding the feature.

## Tenant and scope boundaries

Explain how the feature respects tenant, outlet, user, or channel scope.

## State / document impact

Use when the feature creates or updates meaningful documents or statuses.

## Audit / reporting / configuration impact

Use only if relevant.

## Related files

- [validations.md](./validations.md)
- [application.md](./application.md)
- [backend.md](./backend.md)
- [../../../../04-data/tenant-consistency-rules.md](../../../../04-data/tenant-consistency-rules.md)

## Final check before saving

Confirm that this file:

- focuses on feature-relevant data only
- links to shared data rules instead of duplicating them
- makes tenant and scope boundaries visible where they matter
- is understandable by developers, QA, and AI assistants
