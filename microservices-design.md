# Microservices Design

## Overview

This document outlines design patterns for building scalable microservices architectures.

## Service Boundaries

Define services around business capabilities:
- User Service
- Order Service
- Inventory Service
- Payment Service
- Notification Service

## Inter-Service Communication

### Synchronous (HTTP/gRPC)
Use for:
- Real-time requirements
- Simple request-response patterns
- When latency is critical (<100ms)

### Asynchronous (Message Queue)
Use for:
- Long-running operations
- Event-driven architectures
- Decoupling services
- Batch processing

## Data Management

### Database-per-Service
- Each service owns its data
- No shared databases
- Services access other data via APIs

### Event Sourcing
- Store state changes as events
- Rebuild state by replaying events
- Audit trail built-in

## Service Discovery

- Use Consul, etcd, or service mesh (Istio/Linkerd)
- Health checks every 10 seconds
- Circuit breaker pattern for resilience

## API Gateway

Responsibilities:
- Authentication/authorization
- Rate limiting
- Request routing
- Protocol translation (REST ↔ gRPC)
- Response caching

## Deployment Patterns

| Pattern | Use Case |
|---------|----------|
| Blue-Green | Zero-downtime deployments |
| Canary | Risk mitigation for new versions |
| Feature Flags | Gradual feature rollout |
| Sidecar | Cross-cutting concerns (logging, monitoring) |

## Monitoring

- Distributed tracing (OpenTelemetry)
- Centralized logging (ELK stack)
- Metrics (Prometheus + Grafana)
- Health check endpoints
