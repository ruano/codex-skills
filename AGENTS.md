# AGENTS.md

## Repository expectations

- Use .NET 8 unless the repository already defines another target framework.
- Preserve existing architectural conventions unless they are clearly broken.
- Prefer small, explicit changes over broad refactors.
- Do not add production dependencies unless necessary.
- Keep endpoints/controllers thin.
- Business rules must stay in application/domain layers.
- Never expose persistence entities directly in API contracts.
- Use async for I/O operations.
- Propagate CancellationToken where appropriate.
- Use structured logging.
- Add or preserve health checks when touching service startup.
- Prefer resilient integrations for external dependencies.
- When changing persistence logic, consider transactions, idempotency, and query performance.
- When changing public APIs, preserve backward compatibility unless explicitly instructed otherwise.

## Validation and quality

- Run tests related to the modified area.
- Prefer focused tests for business-critical paths.
- Avoid unnecessary abstractions.
- Keep code readable and intention-revealing.

## Security

- Never hardcode secrets.
- Never log tokens, passwords, connection strings, or personal data.
- Prefer policy-based authorization when authorization is required.