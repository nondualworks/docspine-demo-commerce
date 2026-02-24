# Error Codes

## Payment Error Codes

| Code | Meaning | Action |
|------|---------|--------|
| `PG-001` | Card declined | Prompt customer to retry with different card |
| `PG-002` | Insufficient funds | Prompt customer to retry with different card |
| `PG-003` | Provider timeout | Automatic retry with exponential backoff |
| `PG-004` | Invalid currency | Check supported currencies for the region |
| `PG-005` | Duplicate transaction | Idempotency key already used |
