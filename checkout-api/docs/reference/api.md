# API Reference

## Endpoints

### `POST /api/v1/checkout`

Creates a new checkout session.

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `cart_id` | string | yes | Cart identifier |
| `customer_id` | string | yes | Customer identifier |
| `payment_method` | string | yes | One of: `card`, `bank_transfer`, `wallet` |

**Response:** `201 Created`

```json
{
  "checkout_id": "chk_abc123",
  "status": "pending",
  "created_at": "2026-02-24T10:00:00Z"
}
```

### `GET /api/v1/checkout/{id}`

Returns the current state of a checkout session.

### `POST /api/v1/checkout/{id}/confirm`

Confirms payment and triggers order creation.
