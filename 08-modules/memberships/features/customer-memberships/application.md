<!--
meta:
  title: Memberships / Customer Memberships / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [memberships, customer-memberships, application]
-->
> Hub: [[10-modules/memberships/features/customer-memberships/overview]]

# Customer Memberships - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Customer Memberships**.

## Main orchestration paths
- enroll customer
- change tier
- suspend or expire membership

## Application-layer notes
- membership state should be optional and not block core order/sale workflows if loyalty is not enabled

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/memberships/features/membership-tiers/overview|Membership Tiers]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]
- [[10-modules/reporting/features/daily-sales-reporting/overview|Daily Sales Reporting]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
