# Cursor Rules for Professional Software Engineering

## 1. Context

I am a software engineering mentor who publishes and maintains both open source libraries and closed-source, for-profit services and tools.

## 2. Core Principles

### 2.1. Code Preservation

- **ALWAYS** preserve all pre-existing debugging code and statements
- Never remove console.log, debug prints, or diagnostic code without explicit permission
- Maintain and improve existing documentation - never reduce its quality or detail

### 2.2. Framework-Specific Requirements

#### 2.2.1. Svelte

- For `*.svelte.ts` files, always consider Svelte 5.0.0 or higher compatibility
- Use runes (`$state`, `$effect`, etc.) when appropriate
- Follow Svelte 5's best practices for reactivity and component composition

#### 2.2.2. TypeScript/JavaScript

- Use TypeScript strict mode principles even in JavaScript files
- Prefer type safety and explicit typing over implicit any types
- Follow ESLint and Prettier conventions when present

#### 2.2.3. Go

- Follow idiomatic Go patterns and conventions
- Use proper error handling with explicit error returns
- Prefer composition over inheritance

## 3. Documentation Standards

### 3.1. General Documentation Rules

1. **All documentation MUST include proper punctuation** - no exceptions
2. Use a technical and confident tone that remains inviting and welcoming
3. For test-related code documentation, be even more inviting and encouraging
4. Always document edge cases and potential pitfalls
5. Include usage examples where beneficial

### 3.2. Language-Specific Documentation Formats

#### 3.2.1. Go Documentation

```go
// FunctionName performs a detailed description of what this function does.
// Include any important behavioral notes or performance characteristics.
//
// Arguments:
// - paramName: Detailed description of the parameter including valid ranges/values.
// - anotherParam: Description with any constraints or expectations.
//
// Returns:
// - returnType: Detailed description of what is returned and under what conditions.
// - error: Description of possible error conditions and what they mean.
//
// Example:
//   result, err := FunctionName("example", 42)
//   if err != nil {
//       log.Fatal(err)
//   }
//   fmt.Println(result)
//
// Note: Any special considerations, performance implications, or gotchas.
```

#### 3.2.2. TypeScript/JavaScript Documentation

```typescript
/**
 * Performs a detailed description of what this function does.
 * Include any important behavioral notes or performance characteristics.
 * 
 * @param paramName - Detailed description of the parameter
 * @param {string} anotherParam - Description with type if not obvious from TypeScript
 * @returns Description of return value (omit if trivially inferred from signature)
 * @throws {ErrorType} Description of when this error is thrown
 * 
 * @example
 * ```typescript
 * const result = functionName("example", { option: true });
 * console.log(result);
 * ```
 * 
 * @remarks
 * Any additional implementation notes or considerations
 */
```

### 3.3. Python Documentation (if needed)

```python
"""
Brief description of what this function does.

Detailed explanation including any important behavioral notes
or performance characteristics.

Args:
    param_name: Detailed description of the parameter including types
    another_param: Description with any constraints or expectations

Returns:
    Description of what is returned and under what conditions

Raises:
    ErrorType: Description of when this error is raised

Example:
    >>> result = function_name("example", 42)
    >>> print(result)
    'expected output'

Note:
    Any special considerations or implementation details
"""
```

## 4. Testing Standards

### 4.1. Test Coverage Requirements

1. **Generate test coverage for ALL new functionality** - no exceptions
2. Tests must cover:
   - Happy path scenarios
   - Edge cases
   - Error conditions
   - Boundary values
   - Concurrent access (where applicable)

### 4.2. Test Quality Standards

1. **Idempotency**: All tests MUST be idempotent - running them multiple times should produce the same result
2. **Isolation**: Tests should not depend on external state or other tests
3. **Clarity**: Test names should clearly describe what is being tested
4. **Performance**: Include benchmarks for performance-critical code

### 4.3. Test Review Process

- Re-evaluate existing test coverage when modifying code
- Re-implement tests if they:
  - Don't guarantee idempotency
  - Are potentially problematic or flaky
  - Could be improved with better approaches
  - Don't cover new edge cases introduced by changes

### 4.4. Test Documentation

```go
// TestFunctionName_ScenarioDescription tests specific behavior.
// This test ensures that [specific guarantee or behavior].
```

## 5. Debugging Standards

### 5.1. Debug Logging

For Node.js/JavaScript environments with complex objects:

```javascript
console.log(inspect(complexObject, { 
    colors: true, 
    compact: false,
    depth: null, // Show full depth
    breakLength: 80 
}));
```

For simple debugging:

```javascript
console.log('[ComponentName]', 'Action:', { relevantData });
```

## 6. Code Quality Standards

### 6.1. General Best Practices

1. **DRY (Don't Repeat Yourself)** - Extract common patterns into reusable functions
2. **SOLID Principles** - Follow where applicable
3. **Clean Code** - Meaningful names, small functions, single responsibility
4. **Error Handling** - Always handle errors explicitly and meaningfully
5. **Performance** - Consider performance implications, add comments for O(n) complexity

### 6.2. Security Considerations

1. Never hardcode sensitive information
2. Validate all inputs
3. Sanitize outputs when dealing with user data
4. Use proper authentication and authorization checks
5. Follow OWASP guidelines for web applications

### 6.3. Version Control

1. Write clear, imperative commit messages
2. Keep commits atomic and focused
3. Reference issue numbers where applicable
4. Never commit commented-out code without explanation

## 7. Code Review Checklist

When reviewing or writing code, ensure:

- [ ] All new functions have proper documentation
- [ ] Test coverage is comprehensive
- [ ] Error handling is explicit and helpful
- [ ] Performance implications are considered
- [ ] Security concerns are addressed
- [ ] Code follows language-specific idioms
- [ ] Debug statements use proper formatting
- [ ] Documentation includes examples where helpful
- [ ] Existing functionality is preserved or improved

## 8. Continuous Improvement

- Regularly update dependencies
- Refactor when patterns emerge
- Document architectural decisions
- Maintain a CHANGELOG.md
- Keep README.md up-to-date
- Add migration guides for breaking changes
