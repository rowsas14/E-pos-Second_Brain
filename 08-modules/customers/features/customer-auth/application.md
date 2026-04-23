<!--
meta:
  title: Customers / Customer Auth / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [customers, customer-auth, application]
-->
> Hub: [[10-modules/customers/features/customer-auth/overview]]

# Customer Auth - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Customer Auth**.

## Main orchestration paths
- register customer auth account
- log in with local or provider identity
- link or manage identity methods

## Application-layer notes
- keep customer auth separate from staff auth policy and session claims

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]
- [[10-modules/customers/features/customer-addresses/overview|Customer Addresses]]
- [[10-modules/memberships/features/customer-memberships/overview|Customer Memberships]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
