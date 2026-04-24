# Event-Driven Architecture Design

## Overview

This document outlines patterns for building event-driven systems.

## Event Types

| Type | Description | Example |
|------|-------------|---------|
| Domain Events | Business significant occurrences | `OrderPlaced`, `PaymentReceived` |
| Integration Events | Cross-service communication | `UserCreated`, `InventoryUpdated` |
| Temporal Events | Time-triggered | `SubscriptionRenewalDue` |

## Event Structure

```json
{
  "id": "evt-abc123",
  "type": "order.placed",
  "version": "1.0",
  "timestamp": "2024-01-15T10:30:00Z",
  "correlationId": "req-def456",
  "source": "order-service",
  "payload": {
    "orderId": "ord-789",
    "customerId": "cust-123",
    "amount": 99.99,
    "currency": "USD"
  }
}
```

## Messaging Patterns

### Publish-Subscribe
- Multiple consumers receive each event
- Loose coupling between producers and consumers
- Event bus or message broker (RabbitMQ, SNS)

### Point-to-Point
- Single consumer processes each message
- Queue-based delivery
- Load balancing across consumers

## Event Sourcing

### Concept
- Store events as source of truth
- Current state derived by replaying events

### Benefits
- Complete audit trail
- Temporal queries (state at any point)
- Easy debugging and replay

### Considerations
- Event schema evolution
- Snapshotting for performance
- Projections for read models

## CQRS (Command Query Responsibility Segregation)

Separate read and write models:
- **Commands**: Update state, emit events
- **Queries**: Read optimized views
- **Event Handlers**: Update read models

## Message Broker Options

| Broker | Delivery Guarantee | Ordering | Use Case |
|--------|-------------------|----------|----------|
| RabbitMQ | At-least-once | Per-queue | Complex routing |
| Kafka | At-least-once | Per-partition | High throughput |
| NATS | At-most-once | Per-subject | Low latency |
| AWS SNS/SQS | Configurable | Best-effort | Cloud-native |

## Idempotency

Consumers must handle duplicate events:
- Idempotency keys on events
- Deduplication based on event ID
- Conditional updates with versioning
