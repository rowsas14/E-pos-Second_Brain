<!--
meta:
  title: Sales POS / POS Checkout / Frontend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, pos-checkout, frontend]
-->
> Hub: [[10-modules/sales-pos/features/pos-checkout/overview]]

# POS Checkout - Frontend

## Purpose
This file captures **frontend** behavior, screens, and UI integration points for **POS Checkout**.

## Frontend behavior notes
- cashier billing screen with always-visible basket, total, and payment action
- scan bar, cart panel, and payment modal are key UI elements

## Frontend dependency map
- [[10-modules/sales-pos/features/pos-checkout/overview]] for scope
- [[workflows]] for user flow
- [[permissions]] for access behavior
- [[api]] for contract usage
- [[edge-cases]] for failure state design

## Related features
- [[10-modules/catalog/features/variants/overview|Variants]]
- [[10-modules/pricing/features/price-lists/overview|Price Lists]]
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]
- [[10-modules/receipts/features/receipt-generation/overview|Receipt Generation]]

## Recommended reading order
Read after [[10-modules/sales-pos/features/pos-checkout/overview]], [[workflows]], [[permissions]], and [[api]].
