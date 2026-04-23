---
name: dotnet-messaging
description: Use this skill for .NET asynchronous integrations using messaging or event-driven architecture, including Kafka, RabbitMQ, background consumers, event contracts, retries, dead-letter flows, ordering concerns, idempotency, and eventual consistency. Do not use for synchronous HTTP-only tasks.
---

# .NET Messaging

## Goal

Guide implementation and review of event-driven and message-driven solutions in .NET.

## Use this skill for

- Kafka consumers and producers
- RabbitMQ integrations
- Background workers
- Event contracts
- Async integration flows
- Dead-letter strategies
- Retry strategies
- Event versioning
- Eventual consistency

## Core rules

- Treat message consumption as at-least-once unless the platform clearly guarantees otherwise.
- Design handlers to be idempotent.
- Distinguish transient failures from permanent failures.
- Define clear retry behavior.
- Define poison message or dead-letter behavior.
- Preserve correlation and trace identifiers across events.
- Avoid mixing transport concerns with business logic.

## Consumer design

- Keep the transport adapter small.
- Move business processing to dedicated services/use cases.
- Validate payload shape early.
- Record processing outcomes clearly.
- Make retries bounded and intentional.

## Event contracts

- Prefer stable, versioned contracts.
- Do not break consumers accidentally.
- Favor additive evolution when possible.

## Operational concerns

- Watch partition or queue backlogs.
- Log retries, failures, and terminal states.
- Expose metrics for throughput, failures, and lag when applicable.