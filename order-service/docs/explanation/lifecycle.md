# Order Lifecycle

## State Machine

Every order follows a deterministic state machine:

```
created → confirmed → processing → shipped → delivered
                  ↘ cancelled
         confirmed → refund_requested → refunded
```

## Compensating Transactions

When an order fails at any stage, compensating transactions unwind previous steps:

- **Payment captured but shipping fails:** Automatic refund initiated
- **Inventory reserved but payment fails:** Reservation released
- **Partial fulfillment:** Split into fulfilled and unfulfilled sub-orders
