<!--
meta:
  title: Feature Template - Frontend
  owner: Engineering / Documentation
  status: active
  last_reviewed: 2026-04-22
  tags: [template, feature-docs, frontend, ui]
-->

# Feature Frontend Template

## Purpose of this file

Use this file to document the feature’s **frontend behavior and UI structure**.

For this project, frontend documentation may need to cover:

- POS screen behavior
- admin/back-office UI behavior
- e-commerce UI behavior
- permission-based visibility or action access
- UI states, interactions, and transitions
- frontend module, screen, and component interaction

## What belongs here

Include:

- screens, views, or panels touched by the feature
- component or interaction responsibilities
- important states and UI transitions
- permission-based UI behavior
- loading, empty, locked, disabled, or error states
- POS-specific ergonomics when relevant
- tenant theme or configuration impact when relevant

## What should not dominate this file

Do not use this file for:

- deep business rule ownership -> [business-rules.md](./business-rules.md)
- API contract detail -> [api.md](./api.md)
- backend orchestration detail -> [application.md](./application.md) and [backend.md](./backend.md)
- generic frontend standards -> [../../../../06-frontend/README.md](../../../../06-frontend/README.md)

## Before filling this file, read

- [overview.md](./overview.md)
- [workflows.md](./workflows.md)
- [permissions.md](./permissions.md)
- [api.md](./api.md)
- [../../../../06-frontend/frontend-overview.md](../../../../06-frontend/frontend-overview.md)
- [../../../../06-frontend/state-management-rules.md](../../../../06-frontend/state-management-rules.md)

Read these when relevant:

- POS-heavy feature -> [../../../../06-frontend/pos-ui-principles.md](../../../../06-frontend/pos-ui-principles.md), [../../../../06-frontend/pos-screen-layout-rules.md](../../../../06-frontend/pos-screen-layout-rules.md)
- theme-aware feature -> [../../../../06-frontend/tenant-theme-application.md](../../../../06-frontend/tenant-theme-application.md)
- permission-sensitive feature -> [../../../../06-frontend/permissions-in-ui.md](../../../../06-frontend/permissions-in-ui.md)

## Project-specific guidance

This platform is not a generic website. When relevant, document how the feature behaves in:

- touchscreen POS flows
- admin or manager operational screens
- e-commerce customer-facing screens
- permission or configuration-based states
- fast operational workflows with low typing
- tenant-specific branding or theme behavior

Use only the contexts that truly apply to the feature.

## Recommended structure

## Frontend summary

Describe how the feature appears and behaves in the UI.

## Screens / views / components

| UI area | Responsibility | Actor type | Notes |
|---|---|---|---|
| `[screen/component]` | `[responsibility]` | `[actor]` | `[notes]` |

## States and transitions

Document loading, success, disabled, empty, conflict, and error states only when relevant.

## Permission-based behavior

Describe how UI access or actions vary by permission or capability.

## POS / usability notes

Use when the feature affects cashier speed, touch behavior, or low-typing workflows.

## Theme / configuration notes

Use when tenant settings or theme tokens change what the feature shows.

## Related files

- [workflows.md](./workflows.md)
- [permissions.md](./permissions.md)
- [api.md](./api.md)
- [edge-cases.md](./edge-cases.md)
- [../../../../06-frontend/error-state-rules.md](../../../../06-frontend/error-state-rules.md)

## Final check before saving

Confirm that this file:

- captures real UI behavior for the feature
- makes important states and restrictions visible
- reflects POS or admin/e-commerce context when relevant
- stays aligned with the shared frontend rules
