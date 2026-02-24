# Configure Webhooks

Configure webhook endpoints to receive real-time notifications about checkout events.

## Supported Events

- `checkout.created` — New checkout session initiated
- `checkout.completed` — Payment confirmed and order created
- `checkout.failed` — Payment declined or expired

## Configuration

Add your endpoint URL in the service configuration:

```yaml
webhooks:
  endpoints:
    - url: https://your-service.example.com/webhooks/checkout
      events: [checkout.completed, checkout.failed]
      secret: ${WEBHOOK_SECRET}
```
