<!--
meta:
  title: Catalog / Suppliers / Frontend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, suppliers, frontend]
-->

# Suppliers - Frontend

Back to [[overview]]

## Purpose
This file explains frontend behavior and UI integration expectations for **Suppliers**.

## Main frontend surfaces
- supplier master screen
- supplier address form
- product-supplier mapping sub-screen in product maintenance

## UI rules
- keep tenant admin and back-office maintenance screens clear and low-friction
- show validation and duplicate warnings before save
- do not expose cross-tenant data through cached or shared views
- where POS consumes this feature indirectly, optimize for fast read and simple display rather than complex maintenance UI
- where storefront consumes this feature, keep output aligned with online publishing state and active catalog rules

## Interaction notes
- display status clearly: active, inactive, archived, or equivalent feature state
- make dependent relationships visible when a change can affect products, variants, pricing, or sellability
- destructive or structural actions should require clear confirmation

## Related files
- [[workflows]]
- [[permissions]]
- [[api]]
- [[03-user-flows/tenant-admin/README]]
