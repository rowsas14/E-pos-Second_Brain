<!--
meta:
  title: Customers / Customer Profiles / Overview
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [customers, customer-profiles, overview]
-->
# Customer Profiles

## Purpose
Tenant-scoped customer master shared across POS and E-Commerce, allowing the same email to exist separately in different tenants.

## Why this feature exists
Customer identity is business-owned per tenant, not globally merged across all tenants in the platform.

## Scope
- create customer from POS or admin
- capture customer during online registration or checkout
- update customer contact information

## Navigation hub
- [[business-rules]]
- [[data-model]]
- [[application]]
- [[api]]
- [[workflows]]
- [[permissions]]
- [[validations]]
- [[edge-cases]]
- [[bugs]]
- [[changelog]]
- [[backend]]
- [[frontend]]

## Related features
- [[10-modules/customers/features/customer-auth/overview|Customer Auth]]
- [[10-modules/customers/features/customer-addresses/overview|Customer Addresses]]
- [[10-modules/memberships/features/customer-memberships/overview|Customer Memberships]]

## Work this feature supports
- Product-specific implementation and change planning
- Business-rule clarification before coding
- API, database, backend, and frontend alignment for the same feature
- Bug analysis and controlled change history at feature level

## Recommended reading order
1. [[10-modules/customers/features/customer-profiles/overview]]
2. [[business-rules]]
3. [[data-model]]
4. [[application]]
5. [[api]]
6. [[permissions]]
7. [[validations]]
8. [[workflows]]
9. [[edge-cases]]
10. [[backend]]
11. [[frontend]]
12. [[bugs]]
13. [[changelog]]
