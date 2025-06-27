---
description: 
globs: 
alwaysApply: true
---

# Code Quality Standards

## General Best Practices

1. **DRY (Don't Repeat Yourself)** - Extract common patterns into reusable functions.
2. **SOLID Principles** - Follow where applicable.
3. **Clean Code** - Meaningful names, small functions, single responsibility.
4. **Error Handling** - Always handle errors explicitly and meaningfully.
5. **Performance** - Consider performance implications, add comments for O(n) complexity.

### Security Considerations

1. Never hardcode sensitive information.
2. Validate all inputs.
3. Sanitize outputs when dealing with user data.
4. Identify potential risks that violate any best practices.

### Version Control

1. Write clear, imperative commit messages.
2. Keep commits atomic and focused.
3. Reference issue numbers where applicable.
4. Never commit commented-out code without explanation.
5. Use convential commit messages (feat: foo, bug: bar, etc).

## Code Review Checklist

When reviewing or writing code, ensure:

- All new functions have proper documentation
- Test coverage is comprehensive
- Error handling is explicit and helpful
- Performance implications are considered
- Security concerns are addressed
- Code follows language-specific idioms
- Debug statements use proper formatting
- Documentation includes examples where helpful
- Existing functionality is preserved or improved

## Continuous Improvement

- Regularly update dependencies
- Refactor when patterns emerge
- Document architectural decisions
- Maintain a CHANGELOG.md
- Keep README.md up-to-date
- Add migration guides for breaking changes
