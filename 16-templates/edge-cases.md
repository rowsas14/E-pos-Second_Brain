<!--
meta:
  title: Feature Template - Edge Cases
  owner: Engineering / Documentation
  status: active
  last_reviewed: 2026-04-22
  tags: [template, feature-docs, edge-cases, failure-scenarios]
-->

# Feature Edge Cases Template

## Purpose of this file

Use this file to document **unusual, failure-prone, or conflict-sensitive scenarios** for the feature.

This is where the team records what can go wrong beyond the normal success path.

## What belongs here

Include cases such as:

- missing or conflicting state
- permission or capability mismatch
- tenant or outlet mismatch
- stale or conflicting data
- retry problems
- concurrent action conflicts
- invalid configuration combinations
- POS interruption scenarios
- stock, payment, or document linkage anomalies
- partial success or rollback-sensitive cases

## What should not dominate this file

Do not use this file for:

- ordinary business rules -> [business-rules.md](./business-rules.md)
- normal success workflow -> [workflows.md](./workflows.md)
- generic platform error policy -> [../../../../05-api/error-contract.md](../../../../05-api/error-contract.md)

## Before filling this file, read

- [workflows.md](./workflows.md)
- [validations.md](./validations.md)
- [permissions.md](./permissions.md)
- [../../../../05-api/concurrency-rules.md](../../../../05-api/concurrency-rules.md)
- [../../../../07-backend/exception-handling-rules.md](../../../../07-backend/exception-handling-rules.md)

## Project-specific guidance

In this project, edge cases often appear around:

- tenant consistency
- outlet scope
- cashier interruption or session state
- inventory-sensitive operations
- payment or refund retries
- return/exchange document linkage
- capability assigned but tenant configuration missing
- tenant configuration changed while the feature is in use

Use only the relevant ones.

## Recommended structure

## Edge-case summary

Describe the highest-risk unusual cases.

## Edge-case catalog

| Case ID | Scenario | Risk | Expected handling | Related file |
|---|---|---|---|---|
| `EC-001` | `[scenario]` | `[risk]` | `[handling]` | `[link]` |

## Conflict-sensitive cases

Use when concurrency or double-processing matters.

## Configuration-sensitive cases

Use when settings, scopes, or feature flags change behavior.

## Operational interruption cases

Use when POS, approval, or workflow interruption matters.

## Recovery expectations

Describe what the system or operator should do after failure.

## Related files

- [validations.md](./validations.md)
- [api.md](./api.md)
- [backend.md](./backend.md)
- [bugs.md](./bugs.md)
- [../../../../13-testing-quality/workflow-test-cases.md](../../../../13-testing-quality/workflow-test-cases.md)

## Final check before saving

Confirm that this file:

- focuses on real unusual scenarios
- helps QA and engineering test or defend the feature
- links to rule, validation, and backend handling documents
- covers conflict or tenant/configuration issues when relevant
