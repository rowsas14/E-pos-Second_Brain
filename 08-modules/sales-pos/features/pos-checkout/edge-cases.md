<!--
meta:
  title: Sales POS / POS Checkout / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, pos-checkout, edge-cases]
-->
> Hub: [[10-modules/sales-pos/features/pos-checkout/overview]]

# POS Checkout - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **POS Checkout**.

## Edge cases
- barcode not found
- split payment partially succeeds
- customer attached after cart already built

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/sales-pos/features/pos-checkout/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/catalog/features/variants/overview|Variants]]
- [[10-modules/pricing/features/price-lists/overview|Price Lists]]
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]
- [[10-modules/receipts/features/receipt-generation/overview|Receipt Generation]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
