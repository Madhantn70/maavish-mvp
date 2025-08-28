# Maavish — MVP Requirements

## Goal
Build an MVP for a food/subscription ordering service with per-product cutoff times, instant availability, subscriptions, and wallet.

## Core user features (must-have)
1. OTP login (phone-based).
2. Product catalog with attributes:
   - id, name, description, images, price, cutoff_time (HH:MM in local time), instant_available (boolean), inventory_by_date.
3. Cart & Checkout:
   - Validate cutoff per product at checkout.
   - If cutoff missed => allocate next valid slot and show scheduled date/time in order summary.
4. Subscriptions:
   - Frequency: daily / alternate / weekly.
   - Pause / resume.
   - Auto-debit wallet on scheduled day/time (5:00 AM).
   - Subscription allocation job runs nightly (22:00).
5. Wallet:
   - Balance ledger (credits, debits).
   - Recharge via Razorpay sandbox.
6. Admin:
   - Product CRUD, set cutoff_time, enter daily stock.
   - Subscription allocation, order assignment.
7. Notifications:
   - Push (Firebase) for order status, wallet events.

## Acceptance criteria
- Users can view products, add to cart, and create orders that respect per-product cutoff rules.
- Subscriptions reserve inventory and auto-debit wallet if enough balance; else mark failed and notify.
- Admin can add stock and see order board.

## Sample product (JSON)
{
  "id": "prod_dosa_01",
  "name": "Plain Dosa",
  "price": 50,
  "cutoff_time": "14:00",
  "instant_available": true,
  "images": ["..."]
}
