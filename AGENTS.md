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
- Use ValueTask for high-throughput async methods that may complete synchronously to reduce allocations.
- Use coding conventions like .editorconfig
- Prefer using Span over Substring when string manipulations
- Add global StyleCop.json file and StyleCop analyzers

## Validation and quality

- Run tests related to the modified area.
- Prefer focused tests for business-critical paths.
- Avoid unnecessary abstractions.
- Keep code readable and intention-revealing.
- Validate inputs
- Fast fail
- Use immutability
- Handle null explicitly
- Log safely
- Expect failures
- Enforce invariants
- Use exceptions when necessary, prefer using Operation Result Pattern

## Clean Code

- Use meaningful and descriptive names for variables, functions, and classes.
- Avoid using magic numbers or hard-coded values in your code. Instead, use Constants or Enums.
- Keep your code concise and easy to read by using whitespace and indentation.
- File names should follow the PascalCase convention.
- Use try-catch blocks to handle exceptions gracefully.
- Use interfaces to define contracts between classes.
- Use the var keyword sparingly and only when the type is obvious.
- Use the using statement to ensure that disposable objects are properly disposed of.
- Use the null-coalescing operator.
- Use pattern matching when possible
- Use object initializers to create objects.
- For Dtos, chose immutable record insetead of classes.
- Keep functions small and classes focused on a single job.
- Keep things simple to reduce complexity and improve collaboration.
- Write meaningful, maintainable tests to validate core logic and prevent regressions.
- Keep dependencies clean and avoid unnecessary complexity.
- Keep the codebase clean and adaptable.
- Avoid Deep Nesting
- Prevent the cyclomatic complexity
- Remove Dead Code
- Keep funcion arguments less than 3
- Prefer Composition Over Inheritance
- Minimize Global State

## Coding principles

Follow these coding principles:

- DRY
- KISS
- YAGNI
- SOLID

## Security

- Never hardcode secrets.
- Never log tokens, passwords, connection strings, or personal data.
- Prefer policy-based authorization when authorization is required.

## Constraints

Do not use:

- MediatR
- FluentAssertions
- AutoMapper