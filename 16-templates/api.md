<!--
meta:
  title: Feature Template - API
  owner: Engineering / Documentation
  status: active
  last_reviewed: 2026-04-22
  tags: [template, feature-docs, api, contracts]
-->

# Feature API Template

## Purpose of this file

Use this file to document **feature-specific API behavior** only.

This file should explain the feature’s API surface and how the feature behaves through the API. Shared API standards do **not** belong here; they belong in the project-level API folder.

## What belongs here

Include feature-specific details such as:

- endpoints owned by the feature
- route purpose
- request and response intent
- feature-specific validation or permission impact
- important feature-specific error cases
- versioned path examples such as `/api/v1/...`
- event or side-effect notes when relevant

## What does not belong here

Do not repeat shared standards from:

- [../../../../05-api/request-response-standard.md](../../../../05-api/request-response-standard.md)
- [../../../../05-api/error-contract.md](../../../../05-api/error-contract.md)
- [../../../../05-api/auth-and-authorization.md](../../../../05-api/auth-and-authorization.md)
- [../../../../05-api/idempotency-rules.md](../../../../05-api/idempotency-rules.md)
- [../../../../05-api/concurrency-rules.md](../../../../05-api/concurrency-rules.md)

Reference those files and only document what is unique to the feature.

## Before filling this file, read

- [overview.md](./overview.md)
- [business-rules.md](./business-rules.md)
- [validations.md](./validations.md)
- [permissions.md](./permissions.md)
- [../../../../05-api/README.md](../../../../05-api/README.md)

## Feature API writing guidance

Use only the sections that truly apply.

Typical feature-level API concerns in this project include:

- tenant-aware resource access
- outlet or user scope
- capability or permission-gated actions
- operational actions used by POS or admin UI
- transaction-sensitive actions for payments, refunds, returns, or stock-affecting behavior
- customer-facing versus staff-facing route separation

## Recommended structure

## API summary

Describe what this feature exposes through the API.

## Endpoints

| Method | Path | Purpose | Actor type | Notes |
|---|---|---|---|---|
| `GET` | `/api/v1/[resource]` | `[purpose]` | `[actor]` | `[notes]` |

## Request notes

Document only feature-specific request requirements.

## Response notes

Document only feature-specific response detail or special shapes.

## Auth / permission impact

Summarize which checks matter for this feature.

## Feature-specific error cases

List only errors that are specific to this feature beyond the shared API contract.

## Idempotency / concurrency notes

Use only when the feature is retry-sensitive or conflict-sensitive.

## Related files

- [validations.md](./validations.md)
- [permissions.md](./permissions.md)
- [application.md](./application.md)
- [../../../../05-api/endpoint-design-rules.md](../../../../05-api/endpoint-design-rules.md)
- [../../../../05-api/versioning-strategy.md](../../../../05-api/versioning-strategy.md)

## Final check before saving

Confirm that this file:

- documents feature-specific API behavior only
- links to shared API rules instead of duplicating them
- uses realistic versioned route examples when needed
- reflects tenant, permission, and transaction concerns when relevant
