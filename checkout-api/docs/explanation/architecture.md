# Architecture Overview

## Hexagonal Architecture

The Checkout API follows a hexagonal (ports and adapters) architecture, separating business logic from infrastructure concerns.

**Core domain:** Cart validation, price calculation, checkout session management.

**Inbound ports:** REST API, async event consumers.

**Outbound ports:** Payment gateway adapter, order service adapter, notification adapter.

## Event-Driven Order Processing

Orders are processed asynchronously via an event bus rather than synchronous API calls. When a checkout is confirmed, a `CheckoutConfirmed` event is published. The Order Service consumes this event and creates the order independently.

This decouples the checkout flow from downstream services, improving resilience and allowing independent scaling.

## Idempotent Payments

All payment operations use idempotency keys to prevent duplicate charges. The checkout session ID serves as the natural idempotency key — retrying a confirmation with the same session ID is always safe.
