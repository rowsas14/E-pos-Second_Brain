# 10-modules

This folder uses one strict feature-based structure across all modules.

## Structure rule
```
module-name/
  features/
    feature-name/
      overview.md
      business-rules.md
      data-model.md
      application.md
      api.md
      workflows.md
      permissions.md
      validations.md
      edge-cases.md
      bugs.md
      changelog.md
      backend.md
      frontend.md
```

## Module and feature map
- **platform-administration/**
  - `features/`
    - `platform-users/` - Platform Users
    - `tenant-onboarding/` - Tenant Onboarding
    - `tenant-lifecycle/` - Tenant Lifecycle
- **tenant-management/**
  - `features/`
    - `tenants/` - Tenants
    - `outlets/` - Outlets
- **identity-access/**
  - `features/`
    - `staff-users/` - Staff Users
    - `roles-permissions/` - Roles & Permissions
    - `outlet-assignments/` - Outlet Assignments
- **catalog/**
  - `features/`
    - `brands/` - Brands
    - `categories/` - Categories
    - `products/` - Products
    - `variants/` - Variants
    - `attributes/` - Attributes
    - `product-images/` - Product Images
    - `suppliers/` - Suppliers
- **pricing/**
  - `features/`
    - `price-lists/` - Price Lists
    - `outlet-price-overrides/` - Outlet Price Overrides
- **inventory/**
  - `features/`
    - `stock-ledger/` - Stock Ledger
    - `reservations/` - Reservations
    - `stock-transfers/` - Stock Transfers
    - `stocktakes/` - Stocktakes
- **customers/**
  - `features/`
    - `customer-profiles/` - Customer Profiles
    - `customer-auth/` - Customer Auth
    - `customer-addresses/` - Customer Addresses
- **memberships/**
  - `features/`
    - `membership-tiers/` - Membership Tiers
    - `customer-memberships/` - Customer Memberships
- **sales-pos/**
  - `features/`
    - `tills-sessions/` - Tills & Sessions
    - `pos-checkout/` - POS Checkout
    - `hold-recall-sales/` - Hold & Recall Sales
    - `cash-movements/` - Cash Movements
- **orders-ecommerce/**
  - `features/`
    - `carts/` - Carts
    - `orders/` - Orders
    - `product-reviews/` - Product Reviews
- **discounts-promotions/**
  - `features/`
    - `discount-requests/` - Discount Requests
    - `discount-applications/` - Discount Applications
    - `coupons/` - Coupons
- **payments/**
  - `features/`
    - `payments/` - Payments
    - `payment-allocations/` - Payment Allocations
    - `refunds/` - Refunds
    - `provider-transactions/` - Provider Transactions
- **returns-exchanges/**
  - `features/`
    - `returns/` - Returns
    - `exchanges/` - Exchanges
- **fulfillment-logistics/**
  - `features/`
    - `deliveries/` - Deliveries
    - `delivery-tracking/` - Delivery Tracking
    - `fulfillment-assignment/` - Fulfillment Assignment
- **reporting/**
  - `features/`
    - `daily-sales-reporting/` - Daily Sales Reporting
    - `payment-return-reporting/` - Payment & Return Reporting
- **tax/**
  - `features/`
    - `tax-classes/` - Tax Classes
    - `tax-rates/` - Tax Rates
- **receipts/**
  - `features/`
    - `receipt-generation/` - Receipt Generation
    - `receipt-delivery/` - Receipt Delivery
- **audit-compliance/**
  - `features/`
    - `audit-logs/` - Audit Logs
    - `sensitive-action-audit/` - Sensitive Action Audit
- **settings-configuration/**
  - `features/`
    - `tenant-settings/` - Tenant Settings
    - `feature-flags/` - Feature Flags
    - `ui-themes/` - UI Themes
