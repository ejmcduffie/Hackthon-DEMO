# Coding Standards and Best Practices

## Core Principles

- **Simplicity First**: Always prefer simple, straightforward solutions over complex ones.
- **DRY (Don't Repeat Yourself)**: Avoid code duplication by reusing existing functionality.
- **Environment Awareness**: Write code that works correctly in development, test, and production environments.

## Code Organization

- **File Size**: Keep files under 400-500 lines. Refactor when approaching this limit.
- **Avoid Scripts in Source**: Don't include one-off scripts in source files. Use the `scripts/` directory for utility scripts.
- **Clean Code**: Maintain a clean, well-organized codebase with consistent patterns.

## Development Practices

### Code Changes
- **Minimal Scope**: Only make changes that are requested or clearly related to the task.
- **Progressive Enhancement**: When fixing issues, exhaust existing patterns before introducing new ones.
- **Remove Legacy Code**: When introducing new patterns, remove the old implementation to prevent duplication.

### Testing
- **Mocks for Tests Only**: Use mocking only in test environments, never in dev or prod.
- **No Fake Data**: Avoid stubbing or fake data patterns in dev/prod code.

### Environment Management
- **Environment Files**: Never overwrite `.env` files without explicit confirmation.
- **Configuration**: Ensure code respects environment variables and configuration settings.

## Code Quality

- **Readability**: Write code that is easy to read and understand.
- **Maintainability**: Structure code to be easily maintainable by other developers.
- **Documentation**: Document complex logic and non-obvious decisions.

## Review Process

- **Peer Review**: All code changes should be reviewed by at least one other developer.
- **Automated Checks**: Use linters and formatters to maintain code quality.
- **Testing**: Ensure adequate test coverage for new features and bug fixes.

## Best Practices

- **Error Handling**: Implement proper error handling and logging.
- **Performance**: Be mindful of performance implications, especially in frequently called code paths.
- **Security**: Follow security best practices, especially for user input and authentication.

---

*Last Updated: June 18, 2025*
