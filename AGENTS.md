# Global Engineering Guidelines

## Principles
- Follow SOLID principles
- Prefer explicit over implicit behavior
- Design for failure (fail fast + recover)

## Architecture
- Prefer event-driven communication when decoupling is needed
- Ensure eventual consistency is explicit and traceable
- Avoid tight coupling between services

## Resilience
- Always consider:
  - Retry (with backoff)
  - Circuit Breaker
  - Timeout
- Do NOT overload dependencies

## Observability
- Every critical flow must include:
  - Logs
  - Metrics
  - Tracing

## Idempotency
- All consumers must be idempotent
- Use eventId or equivalent unique key

## Anti-patterns
- Blocking Kafka partitions unnecessarily
- Infinite retries without control
- Hidden side effects