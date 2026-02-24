# Process a Refund

Initiate and track full or partial refunds for completed orders.

## Full Refund

```bash
curl -X POST /api/v1/orders/{order_id}/refund \
  -H 'Content-Type: application/json' \
  -d '{"reason": "customer_request"}'
```

## Partial Refund

```bash
curl -X POST /api/v1/orders/{order_id}/refund \
  -H 'Content-Type: application/json' \
  -d '{"amount": 2500, "reason": "damaged_item", "line_items": ["li_abc"]}'
```

## Refund Status

Track refund progress via the order events endpoint:

```
GET /api/v1/orders/{order_id}/events?type=refund
```
