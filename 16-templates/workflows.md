<!--
meta:
  title: Feature Template - Workflows
  owner: Engineering / Documentation
  status: active
  last_reviewed: 2026-04-22
  tags: [template, feature-docs, workflows, process-flows]
-->

# Feature Workflows Template

## Purpose of this file

Use this file to document **how the feature operates step by step**.

This file should explain flows such as:

- primary success path
- alternative path
- approval path
- exception or recovery path
- actor-to-actor handoff
- state transition flow

For features used in POS, admin, inventory, manager, or e-commerce contexts, this file should make the real operating flow clear.

## What belongs here

Include:

- actor-driven steps
- system actions triggered at each step
- important branching points
- approval or review points
- failure or recovery flows
- POS-specific speed or sequence constraints when relevant
- where the flow affects stock, payment, customer, permissions, or audit behavior

## What should not be the focus here

Do not turn this file into:

- a rule catalog -> use [business-rules.md](./business-rules.md)
- a database design note -> use [data-model.md](./data-model.md)
- an endpoint contract document -> use [api.md](./api.md)
- a UI component inventory -> use [frontend.md](./frontend.md)

## Before filling this file, read

- [overview.md](./overview.md)
- [business-rules.md](./business-rules.md)
- [permissions.md](./permissions.md)

Read when relevant:

- POS-focused feature -> [../../../../06-frontend/pos-ui-principles.md](../../../../06-frontend/pos-ui-principles.md), [../../../../06-frontend/cashier-speed-rules.md](../../../../06-frontend/cashier-speed-rules.md)
- transaction-sensitive feature -> [../../../../07-backend/transaction-handling-rules.md](../../../../07-backend/transaction-handling-rules.md)
- API-integrated feature -> [api.md](./api.md)

## Workflow writing guidance

This project includes different operating contexts. Use only the actors and steps that genuinely apply to the feature.

Possible actors include:

- platform admin
- tenant admin
- store manager
- cashier
- inventory staff
- e-commerce operations staff
- customer
- system / scheduler / integration

If the feature has more than one meaningful workflow, split them clearly instead of mixing them together.

## Recommended structure

## Workflow list

| Workflow ID | Name | Primary actor | Trigger |
|---|---|---|---|
| `WF-001` | `[Workflow name]` | `[Actor]` | `[Trigger]` |

## Main success flow

1. `[Actor/System step]`
2. `[Next step]`
3. `[System response or state update]`

## Alternative flows

### Alternative flow A
Describe the variation.

### Alternative flow B
Describe the variation.

## Exception and recovery flows

Use for:

- validation stop
- authorization stop
- approval rejection
- stock or payment conflict
- configuration mismatch
- retry or resume behavior

## State transitions in flow

Use when the workflow changes document or entity state.

## POS / operational timing notes

Use only when relevant. This is especially important for cashier-speed features.

## Related files

- [business-rules.md](./business-rules.md)
- [validations.md](./validations.md)
- [permissions.md](./permissions.md)
- [edge-cases.md](./edge-cases.md)
- [frontend.md](./frontend.md)
- [application.md](./application.md)

## Final check before saving

Confirm that this file:

- explains real sequence behavior
- covers the main path and important deviations
- stays readable for developers, QA, and AI assistants
- does not replace the deeper rule, API, or backend files
