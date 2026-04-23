<!--
meta:
  title: Feature Template - Permissions
  owner: Engineering / Documentation
  status: active
  last_reviewed: 2026-04-23
  tags: [template, feature-docs, permissions, capabilities, access-control]
-->

# Feature Permissions Template

## Purpose of this file

Use this file to document the **effective access model** for one feature.

This file should explain:

- who can access the feature
- what permissions or capability checks apply
- what scope rules apply
- whether the feature has a default role mapping
- whether platform admin can override that mapping
- how tenant-side configuration changes feature availability or behavior

This file is not only for a role list. It is the feature-level access contract.

## What belongs here

Document feature-specific access topics such as:

- primary actors
- tenant-scope vs outlet-scope access
- required permission codes or capability names
- default role mapping if one exists
- platform-admin override rules
- tenant-side configuration impact
- approval-sensitive actions
- action-level access differences inside the same feature
- customer-facing access differences if applicable

## What should not dominate this file

Do not let this file become:

- a business-rule file -> use [business-rules.md](./business-rules.md)
- a UI visibility specification only -> use [frontend.md](./frontend.md)
- an API auth contract only -> use [api.md](./api.md)
- a backend validation implementation note only -> use [application.md](./application.md) or [backend.md](./backend.md)

Short references are fine. Ownership is not.

## Before filling this file, read

At minimum:

- [overview.md](./overview.md)
- [business-rules.md](./business-rules.md)
- [../../02-architecture/role-permission-capability-model.md](../../02-architecture/role-permission-capability-model.md)
- [../../02-architecture/multi-tenancy-model.md](../../02-architecture/multi-tenancy-model.md)

Read these when relevant:

- API-sensitive feature -> [../../05-api/auth-and-authorization.md](../../05-api/auth-and-authorization.md)
- backend-sensitive feature -> [../../07-backend/validation-rules.md](../../07-backend/validation-rules.md)
- tenant configuration feature -> [../../11-config-and-customization/permission-configuration.md](../../11-config-and-customization/permission-configuration.md)

## Project-specific guidance

This project does **not** treat a feature as permanently owned by one hard-coded role.

A feature may have:

- a **default role mapping** as an initial or seeded assignment
- a **platform-admin override** that changes the mapping
- a **tenant-side configuration layer** that changes behavior after assignment

### Required rule for writers

If the feature has a default role mapping, document it clearly as a **starting assignment only**.

Do not document the default role as if it were the final runtime access rule unless the source material explicitly says it is fixed and non-overridable.

### Effective access rule

Final runtime access should be documented as:

- platform-admin capability assignment
- current role/permission mapping
- current scope rules
- tenant-side configuration that affects the feature
- tenant and outlet boundary checks

## Recommended structure

## Access summary

Write 3-6 sentences explaining the feature access model in plain language.

## Primary actors

| Actor | Access type | Notes |
|---|---|---|
| `[Actor]` | `[read/use/approve/admin]` | `[short note]` |

## Default role mapping

Use this section only when a default role mapping exists.

Document:

- the default mapped role
- why that default exists
- whether it is seeded at onboarding or initial configuration
- whether it is only a starter mapping

If no default role mapping exists, omit this section.

## Platform capability assignment

Document:

- whether platform admin must assign or enable the feature
- whether the tenant can use the feature without that assignment
- whether the capability can be mapped to more than one role

## Effective runtime access

Document the actual access decision path.

Good examples:

- “Runtime access is determined by current capability assignment, current tenant role mapping, and tenant-side configuration.”
- “The default role is not sufficient by itself if the platform-admin mapping has been changed.”

## Scope rules

Document tenant scope, outlet scope, channel scope, or customer scope when applicable.

## Action-level access differences

Document when the feature has different actions with different access requirements.

Example pattern:

| Action | Who can perform it | Extra rule |
|---|---|---|
| `[Action]` | `[Actor/Role]` | `[Approval or scope note]` |

## Tenant-side configuration impact

Document whether configuration can:

- hide or show actions
- limit actions to certain outlets
- enable approval thresholds
- enable channel-specific behavior
- disable only part of the feature while leaving the capability assigned

## Sensitive actions

Document whether some actions need stronger control, approval, or audit treatment.

## Related files

- [business-rules.md](./business-rules.md)
- [validations.md](./validations.md)
- [api.md](./api.md)
- [frontend.md](./frontend.md)
- [../../02-architecture/role-permission-capability-model.md](../../02-architecture/role-permission-capability-model.md)
- [../../05-api/auth-and-authorization.md](../../05-api/auth-and-authorization.md)

## Final check before saving

Confirm that this file:

- separates default role mapping from effective runtime access
- does not assume the feature is permanently owned by one role
- records platform-admin override behavior when it exists
- records tenant configuration impact when it exists
- stays aligned with the current feature and project access model
