# Provider Reference

## Supported Providers

| Provider | Regions | Card Types | Recurring |
|----------|---------|------------|-----------|
| Stripe | Global | Visa, MC, Amex | Yes |
| Adyen | EU, APAC | Visa, MC, JCB | Yes |
| PayPal | Global | N/A (wallet) | Limited |

## Configuration

Each provider requires credentials stored in AWS Secrets Manager:

```yaml
providers:
  stripe:
    secret_arn: arn:aws:secretsmanager:us-east-1:123456:secret:stripe-prod
  adyen:
    secret_arn: arn:aws:secretsmanager:eu-west-1:123456:secret:adyen-prod
```
