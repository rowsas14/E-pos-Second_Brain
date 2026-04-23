<!--
meta:
  title: Memberships / Customer Memberships / Overview
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [memberships, customer-memberships, overview]
-->
# Customer Memberships

## Purpose
One membership record per customer per tenant, linked to a membership tier and points balance.

## Why this feature exists
Membership is explicitly tenant-specific in the operating model and must not be merged globally.

## Scope
- enroll customer
- change tier
- suspend or expire membership

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
- [[10-modules/memberships/features/membership-tiers/overview|Membership Tiers]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]
- [[10-modules/reporting/features/daily-sales-reporting/overview|Daily Sales Reporting]]

## Work this feature supports
- Product-specific implementation and change planning
- Business-rule clarification before coding
- API, database, backend, and frontend alignment for the same feature
- Bug analysis and controlled change history at feature level

## Recommended reading order
1. [[10-modules/memberships/features/customer-memberships/overview]]
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
