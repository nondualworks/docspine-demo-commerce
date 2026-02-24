# Order API Reference

## Endpoints

### `POST /api/v1/orders`
Create a new order from a confirmed checkout session.

### `GET /api/v1/orders/{id}`
Retrieve order details including current state and line items.

### `POST /api/v1/orders/{id}/cancel`
Cancel an order. Only valid in `created` or `confirmed` states.

### `POST /api/v1/orders/{id}/refund`
Initiate a full or partial refund.

### `GET /api/v1/orders/{id}/events`
Stream of order lifecycle events for tracking and audit.
