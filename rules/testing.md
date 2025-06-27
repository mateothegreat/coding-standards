---
description: 
matchers:
- extensions:
  - go
- languages:
  - go
tags:
- all
---
# Testing Standards

## [∞](#coverage-requirements) Coverage Requirements

1. **Generate test coverage for ALL new functionality** - no exceptions
2. Tests must cover:

- Happy path scenarios
- Edge cases
- Error conditions
- Boundary values
- Concurrent access (where applicable)

## [∞](#quality-standards) Quality Standards

1. **Idempotency**: All tests MUST be idempotent - running them multiple times should produce the same result
2. **Isolation**: Tests should not depend on external state or other tests
3. **Clarity**: Test names should clearly describe what is being tested
4. **Performance**: Include benchmarks for performance-critical code

## [∞](#review-process) Review Process

- Re-evaluate existing test coverage when modifying code
- Re-implement tests if they:
  - Don't guarantee idempotency
  - Are potentially problematic or flaky
  - Could be improved with better approaches
  - Don't cover new edge cases introduced by changes

## [∞](#best-practices) Best Practices

- Use table-driven tests for complex scenarios
- Use mocks for external dependencies
- Use test doubles for complex objects
- Use test fixtures for setup and teardown
- Use test isolation for concurrent tests
- Use test coverage to guide testing efforts
- Use test performance to guide testing efforts
