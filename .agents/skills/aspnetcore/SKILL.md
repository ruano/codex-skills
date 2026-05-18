---
name: aspnetcore
description: Use this skill when building, reviewing, refactoring, or extending ASP.NET Core and .NET backend applications, including Web APIs, minimal APIs, controllers, DI, middleware, and production-ready backend structure. Do not use for frontend-only tasks or non-.NET stacks.
---

# ASP.NET Core

## Goal

Provide guidance for modern ASP.NET Core backend development with maintainability, performance, security, and production readiness.

## Use this skill for

- ASP.NET Core Web API
- Minimal APIs
- Controllers
- Middleware
- Dependency Injection
- API design
- Health checks
- Background services

## Core rules

- Keep controllers and endpoints thin.
- Put business rules in application/domain layers.
- Prefer explicit request/response contracts.
- Use async for I/O.
- Use cancellation tokens where appropriate.
- Centralize exception handling.
- Use proper HTTP status codes.
- Do not expose EF entities directly through API contracts.
- Add pagination for list endpoints when needed.
- Use global exception handler with ProblemDetails for API errors when possible.
- Use Serilog for structured logging and avoid sensitive data.
- Use OpenTelemetry defaults for distributed tracing and monitoring.
- Use Options Pattern with data annotations and validate it on start using ValidateOnStart() method
- Prefer Span/ReadOnlySpan over Substring for allocation-sensitive string parsing.
- Use Scalar tool to document APIs using OpenAPI standards and generate client code when appropriate.
- Add API versioning when evolving APIs to maintain backward compatibility.
- Use Refit to create type-safe REST API clients when consuming other services to reduce boilerplate and improve maintainability.
- Prefer using Microsoft.Extensions.Resilience for implementing retry policies and circuit breakers in a consistent way across the application, leveraging Polly under the hood for advanced resilience strategies.
- Consider using Hangfire for background job processing when you need reliable, persistent background tasks with retry capabilities and a dashboard for monitoring.
- Use System.Text.Json for JSON serialization and deserialization for better performance and lower memory usage compared to Newtonsoft.Json, unless you require specific features that are only available in Newtonsoft.Json.
- Use connection pooling with IHttpClientFactory to optimize outbound HTTP calls and avoid socket exhaustion.

## Project structure preference

Prefer this separation when the project is not already opinionated:

- Api
- Application
- Domain
- Infrastructure

For smaller services, keep the same separation of concerns even if the folders are simpler.

## DI guidance

- Register services with extension methods when possible:
  - AddApplication()
  - AddInfrastructure()
  - AddApi()
- Avoid service locator patterns.
- Avoid oversized classes with too many dependencies.
- Use KeyedService (AddKeyedScoped, AddKeyedSingleton, AddKeyedTransient) when an interface has multiples implementations
- Use Scrutor for assembly scanning and decoration when appropriate to reduce boilerplate in DI registration.
- Use IOptions pattern for configuration and avoid injecting IConfiguration directly into services.

## API design

- Use minimal APIs for smaller, focused services.
- Use controllers for larger APIs or when conventions and grouping are helpful.
- Validate input at the edge.
- Use FluentValidation to validate endpoint request models to prevent XSS and other injection attacks.
- Keep transport validation separate from business validation.
- Follow the RESTful principles for API design using the appropriate HTTP methods and status codes.
- When real time communication is needed, consider using SignalR for WebSocket-based interactions or Server Sent Events (SSE) for simpler one-way streaming scenarios.

## Persistence

- Prefer EF Core for standard CRUD and relational workflows.
- When CQRS is needed, consider using Dapper for the read side to optimize performance and EF to manage the write side for its change tracking and migrations.
- Use EF core migrations for schema changes and version control.
- Use projections for reads.
- Use AsNoTracking for read-only queries where appropriate.
- Watch for N+1 queries.
- Avoid unbounded queries.

## Security

- Prefer secure defaults.
- Use authentication and authorization consistently and OAuth2/OpenID Connect.
- Apply rate limiting and throttling to protect APIs from abuse.
- Follow the OWASP Top Ten for API security to mitigate common vulnerabilities.
- Never hardcode secrets.
- Never log sensitive values.
- Use HTTPS and secure headers.

## Deployment

- Use environment variables for configuration in production.
- Create an initial CI/CD pipeline with build, test, and deploy stages fr GitHub Actions or Azure DevOps when setting up a new project.
- Create an initial docker-compose file for local development and testing when setting up a new project.
- Create an initial Dockerfile for containerization when setting up a new project.

## Output style

When implementing or reviewing, provide:
- concise rationale
- main trade-offs
- minimal necessary code changes
- notes about security/performance when relevant
