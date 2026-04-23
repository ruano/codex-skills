# Architecture Context

## Style
- Event-driven architecture
- Microservices with clear boundaries

## Messaging
- Kafka-based communication
- At-least-once delivery

## Data
- PostgreSQL for integration state
- Oracle for legacy systems

## Patterns
- Unit of Work
- Retry + Circuit Breaker (Polly)
- Idempotent consumers

## Constraints
- Avoid Outbox unless strictly required
- Prefer simplicity over over-engineering