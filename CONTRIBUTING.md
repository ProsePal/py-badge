# How to Contribute

We'd love to accept your patches and contributions to this project. There are
just a few small guidelines you need to follow.

## About This Fork

This is a community-maintained fork of [google/pybadges](https://github.com/google/pybadges).
We welcome contributions including bug fixes, new features, and improvements from
the original repository.

## Getting Started

1. Fork the repository
2. Clone your fork: `git clone https://github.com/YOUR_USERNAME/py-badge.git`
3. Create a new branch: `git checkout -b your-feature-name`
4. Make your changes
5. Test your changes (see Testing section below)
6. Commit and push your changes
7. Open a pull request

## Development Setup

```sh
# Clone the repository
git clone https://github.com/ProsePal/py-badge.git
cd py-badge

# Create a virtual environment
python -m virtualenv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install in development mode with all dependencies
pip install -e .[dev]
```

## Testing

Before submitting your code for review, please run all tests:

```sh
# Install nox if you haven't already
pip install nox

# Run all tests
nox

# Or run specific test sessions:
nox -s lint          # Code formatting check
nox -s unit          # Unit tests
nox -s type_check    # Type checking (Python 3.12+)
nox -s compatibility # Compatibility tests
```

### GitHub Actions CI

All pull requests automatically run the following checks via GitHub Actions:
- Linting (yapf formatting)
- Unit tests
- Type checking
- Compatibility tests across Python 3.8, 3.9, 3.10, 3.11, and 3.12

You can view the CI results in the "Actions" tab or directly on your pull request.

## Code Style

- Follow [PEP 8](https://peps.python.org/pep-0008/) style guidelines
- Use `yapf` for code formatting (checked in CI)
- Add type hints where applicable
- Write docstrings for public functions and classes

## Pull Request Process

1. Fill out the pull request template with all relevant information
2. Link any related issues using `Closes #issue_number`
3. Ensure all CI checks pass
4. Wait for review from maintainers
5. Address any requested changes
6. Once approved, a maintainer will merge your PR

## Reporting Issues

- Use the bug report template for bugs
- Use the feature request template for new features
- Search existing issues before creating a new one
- Provide as much detail as possible, including:
  - Python version
  - pybadges version
  - Operating system
  - Minimal code to reproduce the issue

## Community Guidelines

- Be respectful and inclusive
- Provide constructive feedback
- Follow the [Code of Conduct](https://opensource.google.com/conduct/)
- Help others when you can

## License

By contributing to this project, you agree that your contributions will be
licensed under the Apache License 2.0.
