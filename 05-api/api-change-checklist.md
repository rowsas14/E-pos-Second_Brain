<!--
meta:
  title: API Change Checklist
  owner: Engineering / API
  status: active
  last_reviewed: 2026-04-22
  tags: [api, checklist, change-management, review]
-->

# API Change Checklist

## Purpose

Use this checklist before shipping any API change in this project.

This checklist exists because even small API changes can affect:

- tenant isolation
- permissions and capabilities
- POS workflows
- e-commerce flows
- payments and refunds
- frontend parsing
- module documentation
- tests and release safety

## Change checklist

### Contract impact

- [ ] route path reviewed against [endpoint-design-rules.md](./endpoint-design-rules.md)
- [ ] request shape reviewed against [request-response-standard.md](./request-response-standard.md)
- [ ] response shape reviewed for frontend compatibility
- [ ] error behavior reviewed against [error-contract.md](./error-contract.md)
- [ ] list/query behavior reviewed against [pagination-filtering-sorting.md](./pagination-filtering-sorting.md) when relevant

### Tenant and auth impact

- [ ] tenant boundary impact reviewed
- [ ] platform admin vs tenant staff vs customer access reviewed
- [ ] role or permission impact reviewed
- [ ] outlet-scope impact reviewed where relevant
- [ ] feature capability or tenant configuration impact reviewed

### Transaction and workflow impact

- [ ] payment or refund sensitivity reviewed
- [ ] idempotency reviewed where duplicate-safe handling matters
- [ ] concurrency/conflict behavior reviewed
- [ ] workflow state transition impact reviewed
- [ ] inventory-sensitive consequences reviewed where relevant

### Documentation impact

- [ ] relevant feature `api.md` updated in [../08-modules/](../08-modules/)
- [ ] related `business-rules.md`, `workflows.md`, or `permissions.md` updated if affected
- [ ] shared `05-api/` file updated if the rule is cross-cutting
- [ ] `last_reviewed` updated in changed documents
- [ ] project history or breaking change record updated if needed

### Implementation impact

- [ ] backend rules reviewed against [../02-architecture/backend-architecture.md](../02-architecture/backend-architecture.md)
- [ ] backend layer boundaries reviewed
- [ ] data impact reviewed against [../04-data/](../04-data/)
- [ ] migration impact reviewed if contract change depends on schema change

### Frontend and test impact

- [ ] POS, admin, or storefront client impact reviewed
- [ ] TypeScript contract impact reviewed
- [ ] test cases updated
- [ ] regression risk reviewed

### Versioning impact

- [ ] breaking vs non-breaking assessed
- [ ] `/api/v1/...` compatibility checked
- [ ] versioning update handled per [versioning-strategy.md](./versioning-strategy.md) if required

## Use this checklist with

- [README.md](./README.md)
- [api-overview.md](./api-overview.md)
- [versioning-strategy.md](./versioning-strategy.md)
- [../13-testing-quality/release-readiness-checklist.md](../13-testing-quality/release-readiness-checklist.md)
- [../19-project-history/overall-changelog.md](../19-project-history/overall-changelog.md)
