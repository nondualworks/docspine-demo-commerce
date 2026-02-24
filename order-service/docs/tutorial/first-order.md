# Your First Order

Create a test order end-to-end in the sandbox environment.

## Prerequisites

- Sandbox API key (get one from the developer portal)
- `curl` or any HTTP client

## Step 1: Create a Cart

```bash
curl -X POST https://sandbox.api.example.com/v1/carts \
  -d '{"items": [{"sku": "TEST-001", "quantity": 1}]}'
```

## Step 2: Create Checkout Session

Use the `cart_id` from Step 1:

```bash
curl -X POST https://sandbox.api.example.com/v1/checkout \
  -d '{"cart_id": "cart_xxx", "payment_method": "card"}'
```

## Step 3: Confirm Payment

```bash
curl -X POST https://sandbox.api.example.com/v1/checkout/chk_xxx/confirm \
  -d '{"card_token": "tok_test_visa"}'
```

## Step 4: Check Your Order

```bash
curl https://sandbox.api.example.com/v1/orders?checkout_id=chk_xxx
```

You should see an order in `confirmed` state. Congratulations!
