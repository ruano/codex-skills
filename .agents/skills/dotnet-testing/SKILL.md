---
name: dotnet-testing
description: Use this skill when implementing or reviewing unit and integration tests in .NET projects using xUnit, Shouldly, Testcontainers, NSubstitute, and the AAA pattern. Use for test design, assertions, mocks, fakes, integration test infrastructure, database/container setup, and reliable automated test suites. Do not use for production-only implementation tasks unless tests are also requested.
---

# .NET Testing Skill

## Purpose

Guide the implementation and review of automated tests in .NET applications using:

- xUnit
- Shouldly
- Testcontainers
- NSubstitute
- AAA pattern: Arrange, Act, Assert

The goal is to produce tests that are readable, deterministic, maintainable, and focused on behavior.

---

## When to use

Use this skill when the task involves:

- unit tests
- integration tests
- test review or refactoring
- test naming
- assertions with Shouldly
- mocks/stubs with NSubstitute
- disposable infrastructure with Testcontainers
- API, database, repository, handler, service, worker, or consumer tests

---

## Core principles

Always prefer:

- behavior-focused tests
- clear test names
- deterministic tests
- minimal mocking
- AAA structure
- expressive assertions with Shouldly
- realistic integration tests
- isolated unit tests

Avoid:

- testing private methods directly
- testing implementation details
- excessive mocks
- fragile shared state
- random data that makes failures hard to reproduce
- tests without meaningful assertions
- multiple unrelated behaviors in one test

---

## Test naming

Prefer:

```csharp
MethodName_WhenCondition_ShouldExpectedResult()