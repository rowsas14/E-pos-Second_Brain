<!--
meta:
  title: Customers / Customer Profiles / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [customers, customer-profiles, application]
-->
> Hub: [[10-modules/customers/features/customer-profiles/overview]]

# Customer Profiles - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Customer Profiles**.

## Main orchestration paths
- create customer from POS or admin
- capture customer during online registration or checkout
- update customer contact information

## Application-layer notes
- customer merge strategy, if ever needed, must remain tenant-scoped

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/customers/features/customer-auth/overview|Customer Auth]]
- [[10-modules/customers/features/customer-addresses/overview|Customer Addresses]]
- [[10-modules/memberships/features/customer-memberships/overview|Customer Memberships]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
