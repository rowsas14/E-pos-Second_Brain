<!--
meta:
  title: Feature Template - Validations
  owner: Engineering / Documentation
  status: active
  last_reviewed: 2026-04-22
  tags: [template, feature-docs, validations, guard-rules]
-->

# Feature Validations Template

## Purpose of this file

Use this file to document **what must be checked before the feature action is allowed to proceed**.

This file should gather the feature’s important guard conditions in one place.

It should cover:

- request validation
- business validation
- tenant consistency validation
- state validation
- permission-dependent checks when they affect processing
- data existence and relation checks
- conflict-sensitive checks when relevant

## What belongs here

Document validations such as:

- required fields
- valid ranges or formats
- allowed state for action
- same-tenant requirements
- same-outlet requirements where relevant
- existence checks
- ownership or document linkage checks
- duplicate prevention checks
- stock / payment / allocation / transition guard conditions
- feature-configuration-dependent checks

## What should not be written here

Do not turn this into:

- a full business rule document -> use [business-rules.md](./business-rules.md)
- a low-level API schema dump -> summarize only what matters and link to [api.md](./api.md)
- a backend class-by-class validator list -> use [application.md](./application.md) or [backend.md](./backend.md) when needed

## Before filling this file, read

- [business-rules.md](./business-rules.md)
- [data-model.md](./data-model.md)
- [permissions.md](./permissions.md)
- [../../../../04-data/tenant-consistency-rules.md](../../../../04-data/tenant-consistency-rules.md)
- [../../../../07-backend/validation-rules.md](../../../../07-backend/validation-rules.md)

## Validation categories for this project

Use only the categories that apply to the feature.

### Request validation
Shape and format checks before business processing.

### Business validation
Feature-specific operational rules.

### Tenant consistency validation
Same-tenant and scope checks.

### State validation
Allowed status or document-state checks.

### Permission-sensitive validation
Use when the action can only proceed if permission or capability checks pass.

### Conflict-sensitive validation
Use when allocation, stock, concurrency, or state-transition conflicts matter.

## Recommended structure

## Validation summary

Describe the most important validations in plain language.

## Validation catalog

| Validation ID | Category | Check | Failure result | Related file |
|---|---|---|---|---|
| `VAL-001` | `[request/business/tenant/state/conflict]` | `[check]` | `[result]` | `[link]` |

## Required input checks

Use when the feature has meaningful request requirements.

## Business guard conditions

Use for rule-heavy conditions.

## Tenant / outlet / scope checks

Use whenever tenant or scope rules matter.

## State and transition checks

Use when the feature depends on current status.

## Related files

- [business-rules.md](./business-rules.md)
- [data-model.md](./data-model.md)
- [permissions.md](./permissions.md)
- [edge-cases.md](./edge-cases.md)
- [../../../../05-api/error-contract.md](../../../../05-api/error-contract.md)

## Final check before saving

Confirm that this file:

- makes the major guards visible
- distinguishes request checks from business and tenant checks
- stays consistent with the API and backend rules
- does not hide important same-tenant checks
