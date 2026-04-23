---
name: aspnetcore
description: Use this skill when building, reviewing, refactoring, or extending ASP.NET Core and .NET backend applications, including Web APIs, minimal APIs, controllers, DI, middleware, EF Core, authentication, authorization, and production-ready backend structure. Do not use for frontend-only tasks or non-.NET stacks.
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
- EF Core
- Authentication and authorization
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
- Use ProblemDetails for API errors when possible.

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

## API design

- Use minimal APIs for smaller, focused services.
- Use controllers for larger APIs or when conventions and grouping are helpful.
- Validate input at the edge.
- Keep transport validation separate from business validation.

## Persistence

- Prefer EF Core for standard CRUD and relational workflows.
- Use projections for reads.
- Use AsNoTracking for read-only queries where appropriate.
- Watch for N+1 queries.
- Avoid unbounded queries.

## Security

- Prefer secure defaults.
- Use authentication and authorization consistently.
- Never hardcode secrets.
- Never log sensitive values.

## Output style

When implementing or reviewing, provide:
- concise rationale
- main trade-offs
- minimal necessary code changes
- notes about security/performance when relevant