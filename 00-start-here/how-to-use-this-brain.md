<!--
meta:
  title: How To Use This Brain
  owner: Engineering / Documentation
  status: active
  last_reviewed: 2026-04-22
  tags: [usage-guide, reading-order, implementation-support, workflow]
-->

# How To Use This Brain

## Purpose

Use this guide to read the **right files in the right order** before changing product intent, architecture, schema, API behavior, frontend behavior, backend logic, permissions, or tests.

For this project, one change often touches several areas at once: tenant boundaries, role and capability rules, schema constraints, API behavior, frontend behavior, backend orchestration, and testing.

## Core rule

Do not start from one feature file and assume that is enough.

Read the smallest safe set of product, architecture, data, module, and implementation documents needed for the task.

## Default reading path for a new reader

1. [README.md](./README.md)
2. [documentation-rules.md](./documentation-rules.md)
3. [folder-structure-guide.md](./folder-structure-guide.md)
4. [../01-product/README.md](../01-product/README.md)
5. [../01-product/business-objectives.md](../01-product/business-objectives.md)
6. [../01-product/project-scope.md](../01-product/project-scope.md)
7. [../02-architecture/system-overview.md](../02-architecture/system-overview.md)
8. [../02-architecture/multi-tenancy-model.md](../02-architecture/multi-tenancy-model.md)
9. [../02-architecture/role-permission-capability-model.md](../02-architecture/role-permission-capability-model.md)
10. [../03-decisions/ADR-index.md](../03-decisions/ADR-index.md)

## Default working flow

Use this flow for day-to-day work:

```text
requirement
  -> product intent
  -> architecture boundaries
  -> ADRs
  -> data rules
  -> module docs
  -> implementation standards
  -> code change
  -> testing and validation
  -> bug/issue history update when needed
```

That path reduces the chance of changing one layer while missing another.

## Read these files first by task

### Feature implementation

Read first:

- relevant product files in [../01-product/](../01-product/)
- relevant architecture or ADR files in [../02-architecture/](../02-architecture/) and [../03-decisions/](../03-decisions/)
- the feature folder under [../08-modules/](../08-modules/)
- relevant standards from [../05-api/](../05-api/), [../06-frontend/](../06-frontend/), or [../07-backend/](../07-backend/)
- test guidance in [../13-testing-quality/](../13-testing-quality/)

Minimum feature file set:

- `overview.md`
- `business-rules.md`
- `data-model.md`
- `workflows.md`
- `permissions.md` if access matters
- `api.md`, `frontend.md`, or `backend.md` depending on the change

### Module creation

Read first:

- [folder-structure-guide.md](./folder-structure-guide.md)
- [../01-product/README.md](../01-product/README.md)
- [../02-architecture/README.md](../02-architecture/README.md)
- [../03-decisions/ADR-index.md](../03-decisions/ADR-index.md)
- [../08-modules/README.md](../08-modules/README.md)
- [../16-templates/module-overview-template.md](../16-templates/module-overview-template.md)
- [../16-templates/feature-template.md](../16-templates/feature-template.md)

Before creating a new module, verify that the subject is not already covered by an existing module and that it represents a real business boundary rather than a temporary implementation split.

### Business rule change

Read first:

- [../01-product/project-scope.md](../01-product/project-scope.md)
- relevant ADRs in [../03-decisions/](../03-decisions/)
- the feature `business-rules.md`
- the feature `workflows.md`
- the feature `permissions.md` if the rule affects access or approvals
- related `api.md`, `frontend.md`, or `backend.md` if the rule changes behavior across layers

If the rule changes platform boundaries or core operating assumptions, add or update an ADR.

### Database update

Read first:

- [../04-data/database-overview.md](../04-data/database-overview.md)
- [../04-data/schema-principles.md](../04-data/schema-principles.md)
- [../04-data/tenant-consistency-rules.md](../04-data/tenant-consistency-rules.md)
- the feature `data-model.md`
- related ADRs in [../03-decisions/](../03-decisions/)
- [../07-backend/transaction-handling-rules.md](../07-backend/transaction-handling-rules.md) when the change affects business transactions

For broad changes, also read:

- [../19-project-history/major-migrations.md](../19-project-history/major-migrations.md)
- [../19-project-history/breaking-changes.md](../19-project-history/breaking-changes.md)

### API change

Read first:

- the feature `api.md`
- [../05-api/api-overview.md](../05-api/api-overview.md)
- [../05-api/request-response-standard.md](../05-api/request-response-standard.md)
- [../05-api/error-contract.md](../05-api/error-contract.md)
- [../05-api/idempotency-rules.md](../05-api/idempotency-rules.md) when retries or money flows are involved
- related permissions and workflow files

### Permission update

Read first:

- [../02-architecture/role-permission-capability-model.md](../02-architecture/role-permission-capability-model.md)
- [../12-security-and-compliance/authorization-model.md](../12-security-and-compliance/authorization-model.md)
- feature `permissions.md`
- [../11-config-and-customization/permission-configuration.md](../11-config-and-customization/permission-configuration.md)
- relevant identity-access or settings-configuration module docs in [../08-modules/](../08-modules/)

### Frontend or POS behavior change

Read first:

- relevant product files in [../01-product/](../01-product/)
- [../06-frontend/pos-ui-principles.md](../06-frontend/pos-ui-principles.md)
- [../06-frontend/pos-screen-layout-rules.md](../06-frontend/pos-screen-layout-rules.md)
- [../06-frontend/cashier-speed-rules.md](../06-frontend/cashier-speed-rules.md)
- feature `frontend.md`, `workflows.md`, and `permissions.md`
- [../13-testing-quality/pos-ux-test-cases.md](../13-testing-quality/pos-ux-test-cases.md)

### Bug fix

Read first:

- feature `overview.md`
- feature `workflows.md`
- feature `edge-cases.md`
- feature `bugs.md`
- related frontend, backend, or API rules
- [../13-testing-quality/bug-handling-rules.md](../13-testing-quality/bug-handling-rules.md)
- [../15-ai-ide-rules/bug-fix-rules.md](../15-ai-ide-rules/bug-fix-rules.md) when AI assistance is used

Update after the fix when appropriate:

- feature `bugs.md`
- feature `changelog.md`
- [../19-project-history/overall-bugs.md](../19-project-history/overall-bugs.md) when the issue is broader than one feature

## Following linked files correctly

Use links as a reading path, not as decoration.

When a file links to another document:

- follow it if the linked file owns the rule
- follow it if your change crosses module or layer boundaries
- do not copy the linked content into the current file unless the local file truly needs a short summary

## Documentation must stay aligned with implementation

After implementation, bug fixing, or design change:

1. update the file that owns the changed topic
2. update related links if navigation changed
3. update `last_reviewed`
4. update feature `changelog.md` when the change materially affects feature behavior or documentation
5. update project-wide history files when the change matters beyond one feature
6. add or update an ADR if a major system rule or boundary changed

## Common mistakes to avoid

- reading only one feature file and ignoring architecture or tenancy context
- writing generic notes that do not match this platform
- duplicating the same rule across product, architecture, and module files
- changing a module document without checking API, data, permission, or testing impact
- creating new files before confirming the correct owning folder

## Related documents

- [README.md](./README.md)
- [documentation-rules.md](./documentation-rules.md)
- [folder-structure-guide.md](./folder-structure-guide.md)
- [../15-ai-ide-rules/README.md](../15-ai-ide-rules/README.md)
- [../16-templates/README.md](../16-templates/README.md)
