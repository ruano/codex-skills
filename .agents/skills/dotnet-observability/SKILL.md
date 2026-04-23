---
name: dotnet-observability
description: Use this skill when adding or reviewing observability in .NET services, including structured logging, tracing, metrics, OpenTelemetry, correlation IDs, health checks, and diagnostics for APIs, workers, and asynchronous integrations. Do not use for tasks unrelated to monitoring, telemetry, or diagnostics.
---

# .NET Observability

## Goal

Improve diagnosability, operational visibility, and production supportability in .NET systems.

## Use this skill for

- structured logging
- OpenTelemetry
- tracing
- metrics
- correlation IDs
- health checks
- diagnostics for APIs and background workers

## Core rules

- Prefer structured logs over string-concatenated logs.
- Preserve correlation IDs across boundaries.
- Instrument inbound and outbound calls when relevant.
- Add metrics for throughput, latency, failure rate, and retries when useful.
- Use health checks for readiness and liveness.
- Never log secrets or sensitive data.

## Logging

Prefer logs for:
- important business transitions
- external dependency failures
- retry attempts
- circuit breaker state changes
- terminal processing failures

Avoid:
- noisy logs in hot paths
- duplicate logs for the same failure at multiple layers

## Tracing

- Propagate trace context across HTTP and messaging when possible.
- Instrument API, database, and external dependency boundaries.

## Metrics

Useful examples:
- request duration
- dependency duration
- retry count
- failure count
- consumer lag
- queue depth