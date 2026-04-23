---
name: kafka-consumer-review
description: Validate Kafka consumer robustness and correctness
---

## Instructions
- Ensure idempotent processing (eventId or equivalent)
- Validate retry strategy (limited + backoff)
- Check circuit breaker usage
- Avoid blocking partition for long operations
- Validate error handling strategy (DLQ or retry flow)
- Ensure safe commit strategy

## Red Flags
- Infinite retry loops
- No idempotency
- External calls without resilience