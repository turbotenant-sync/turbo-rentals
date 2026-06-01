# Contributing to Turbo Rentals

Thank you for your interest in contributing to Turbo Rentals.

## Getting Started

1. Fork the repository.
2. Create a feature branch from `main`.

```bash
git checkout -b feature/your-feature-name
```

3. Install dependencies.

```bash
npm install
```

4. Run tests before submitting changes.

```bash
npm test
```

## Development Guidelines

* Follow existing code style and project conventions.
* Write clear, maintainable, and well-documented code.
* Add or update tests when introducing new functionality.
* Keep pull requests focused on a single change whenever possible.

## Security

Security is a priority for Turbo Rentals.

When developing features:

* Enforce server-side authorization checks.
* Never trust client-supplied identifiers for access control.
* Validate and sanitize all user input.
* Protect sensitive information and credentials.
* Follow the principle of least privilege.

If you discover a security vulnerability, please do not create a public issue. Report it privately to the maintainers.

## Pull Requests

Before submitting a pull request:

* Ensure all tests pass.
* Update documentation if necessary.
* Resolve linting issues.
* Verify GitHub Actions workflows complete successfully.

### Pull Request Checklist

* [ ] Tests added or updated
* [ ] Documentation updated
* [ ] Security considerations reviewed
* [ ] CI checks passing

## Commit Messages

Use clear and descriptive commit messages.

Examples:

* Add tenant SMS notification service
* Fix authorization validation for property access
* Add GitHub Actions permissions for CodeQL

## Code of Conduct

By participating in this project, you agree to interact respectfully and professionally with other contributors.

Thank you for helping improve Turbo Rentals.
