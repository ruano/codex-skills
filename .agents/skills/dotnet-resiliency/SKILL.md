---
name: dotnet-resiliency
description: Use this skill when implementing or reviewing resilience patterns in .NET services, including retry, timeout, circuit breaker, fallback, idempotency, outbox-like guarantees, and failure handling for external dependencies. Do not use for tasks that do not involve failure management or distributed systems concerns.
---

# .NET Resiliency

## Goal

Apply resilience patterns carefully and pragmatically in distributed .NET systems.

## Use this skill for

- Retry
- Timeout
- Circuit breaker
- Fallback
- Idempotency
- External dependency failures
- Fault handling in distributed flows
- Transactional consistency trade-offs

## Core rules

- Retry only transient failures.
- Never retry validation or business rule failures.
- Always pair retries with bounded attempts and backoff.
- Use timeout to prevent resource exhaustion.
- Use circuit breaker to fail fast when a dependency is unhealthy.
- Explain trade-offs before adding fallback behavior.
- Design side-effecting operations to be idempotent when retried.

## Circuit breaker guidance

When the circuit is open:
- fail fast
- avoid hammering the dependency
- preserve observability
- decide explicitly what happens to the request or message

Possible strategies:
- return a controlled failure for synchronous calls
- reschedule or retry later for async flows
- send terminal failures to dead-letter or manual handling paths when appropriate

## Idempotency

Prefer:
- idempotency keys
- unique constraints where valid
- processing ledgers / integration registers
- safe re-entry in handlers

## Output style

When suggesting resilience changes, always include:
- failure mode being addressed
- why the pattern fits
- trade-offs
- operational side effects