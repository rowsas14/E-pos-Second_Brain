<!--
meta:
  title: Validation Rules
  owner: Backend Engineering
  status: active
  last_reviewed: 2026-04-23
  tags: [validation, tenant-consistency, business-rules, backend]
-->

# Validation Rules

## Purpose

This file defines validation responsibilities across backend layers.

Validation in this project is more than field presence. It must protect:

- tenant boundaries
- outlet scope
- business rule preconditions
- workflow-specific state assumptions
- effective access state for sensitive operations

## Validation categories

| Validation type | Typical owner |
|---|---|
| request shape validation | API model binding and Application validators |
| use-case input validation | Application validators |
| business workflow validation | Application orchestration and Domain rules |
| tenant consistency validation | Application services plus persistence-aware checks |
| effective access validation | Application services plus permission/capability checks |
| state transition validation | Domain and Application workflow checks |

## Request validation

Use request validation for:

- required fields
- malformed values
- unsupported enums or codes at input boundary
- impossible input combinations that are obvious at request level

## Business validation

Business validation is needed for rules such as:

- actions allowed only in current status
- difference collection or refund logic in exchange scenarios
- allowed return or exchange flows
- valid use-case combinations

## Tenant consistency validation

This project requires strict same-tenant safety.

Validation must confirm, where applicable, that:

- user belongs to the tenant
- role belongs to the same tenant
- outlet belongs to the same tenant
- customer belongs to the tenant
- configuration scope is valid for the tenant context

See [../04-data/tenant-consistency-rules.md](../04-data/tenant-consistency-rules.md).

## Effective access validation

A default role mapping is not enough to approve a sensitive action.

Validation must confirm the **current effective access state** where applicable:

- the feature is currently assigned into the tenant-facing access model
- the user still has the required role scope or permission
- a later platform-admin override has not changed the mapping
- tenant-side configuration does not restrict the action
- outlet-specific restrictions are satisfied

### Important rule

Do not approve access only because a feature was seeded to a default role during onboarding or initial setup.

## Validator usage

Validators are appropriate in Application for:

- DTO validation
- command preconditions
- action-specific field rules

Examples:
- `CreateProductValidator`
- `UpdateProductValidator`
- `CreatePaymentValidator`

## Related documents

- [application-layer-rules.md](./application-layer-rules.md)
- [domain-layer-rules.md](./domain-layer-rules.md)
- [exception-handling-rules.md](./exception-handling-rules.md)
- [../04-data/tenant-consistency-rules.md](../04-data/tenant-consistency-rules.md)
- [../05-api/error-contract.md](../05-api/error-contract.md)
- [../05-api/auth-and-authorization.md](../05-api/auth-and-authorization.md)
- [../02-architecture/role-permission-capability-model.md](../02-architecture/role-permission-capability-model.md)
