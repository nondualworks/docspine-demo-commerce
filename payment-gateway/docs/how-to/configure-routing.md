# Configure Payment Routing

Set up geographic and amount-based payment routing rules to optimize transaction success rates.

## Geographic Routing

Route transactions to the nearest provider for lower latency and higher approval rates:

```yaml
routing:
  rules:
    - match: { region: EU }
      provider: adyen
    - match: { region: APAC }
      provider: adyen
    - match: { region: "*" }
      provider: stripe
```

## Amount-Based Routing

Route high-value transactions to providers with better fraud detection:

```yaml
routing:
  rules:
    - match: { amount_gte: 10000 }
      provider: stripe  # Better fraud tools for high-value
```
