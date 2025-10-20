# Review and Integration Process

This document outlines the process for reviewing and integrating open issues and pull requests from the legacy google/pybadges repository.

## Current State

### Open Issues (5)
1. **#10** - [Legacy #26] Support a title element
2. **#9** - [Legacy #28] Custom Styles
3. **#4** - [Legacy #40] Add User-Agent option for Logo Lookup
4. **#2** - [Legacy #47] imghdr removal
5. **#1** - [Legacy #48] Example CLI command puts out dark color

### Open Pull Requests (4)
1. **#22** - Test PR
2. **#20** - [Legacy PR #24] Support for displaying a trend line and embedding a right image
3. **#19** - [Legacy PR #39] Added style support with default flat and flat-square
4. **#18** - [Legacy PR #38] Add support for Python 3.11

## Review Process

### For Pull Requests

Each PR should go through the following steps:

1. **Initial Review**
   - Check if the PR addresses a real need or issue
   - Review code quality and style
   - Check for breaking changes
   - Verify backward compatibility

2. **Testing**
   - Ensure all GitHub Actions CI checks pass:
     - Linting (yapf)
     - Unit tests
     - Type checking
     - Compatibility tests (Python 3.8-3.12)
   - Manually test the feature if needed
   - Review test coverage

3. **Code Review**
   - Check for:
     - Code style compliance
     - Type hints
     - Documentation/docstrings
     - Edge cases handled
     - No security issues

4. **Integration**
   - Request changes if needed
   - Approve when ready
   - Merge with a descriptive commit message
   - Update changelog if applicable

### For Issues

Each issue should be evaluated:

1. **Triage**
   - Determine if the issue is still relevant
   - Check if it's a duplicate
   - Assign appropriate labels
   - Assign to milestone if applicable

2. **Investigation**
   - Reproduce the issue (for bugs)
   - Evaluate feasibility (for features)
   - Estimate effort required

3. **Resolution**
   - Create or assign to a PR
   - Link the PR to close the issue
   - Verify fix before closing

## Priority Guidelines

### High Priority
- Security vulnerabilities
- Critical bugs affecting core functionality
- Python version compatibility issues
- Dependency updates for security

### Medium Priority
- Bug fixes for edge cases
- Documentation improvements
- Performance improvements
- New features with clear use cases

### Low Priority
- Nice-to-have features
- Cosmetic changes
- Refactoring without clear benefit

## Specific Legacy Items

### PR #18 - Python 3.11 Support
- **Status**: Python 3.12 support was already added in PR #21
- **Action**: Review and potentially close as completed or update for current version

### PR #19 - Style Support (flat and flat-square)
- **Status**: Needs review
- **Action**: Test implementation, verify backward compatibility
- **Priority**: Medium - useful feature but not critical

### PR #20 - Trend Line and Right Image Support
- **Status**: Needs review
- **Action**: Complex feature requiring thorough testing
- **Priority**: Medium - interesting feature for some use cases

### PR #22 - Test PR
- **Status**: Appears to be a test
- **Action**: Review purpose and close if not needed
- **Priority**: Low

### Issue #1 - CLI Dark Color
- **Action**: Reproduce the issue and fix
- **Priority**: High - affects user experience

### Issue #2 - imghdr Removal
- **Action**: imghdr is deprecated in Python 3.11, removed in 3.13
- **Priority**: High - compatibility issue
- **Note**: Need to replace with alternative (python-magic, filetype, or manual detection)

### Issue #4 - User-Agent Option for Logo Lookup
- **Action**: Evaluate need and implement
- **Priority**: Medium - useful for some users

### Issue #9 - Custom Styles
- **Action**: Related to PR #19, coordinate review
- **Priority**: Medium

### Issue #10 - Title Element Support
- **Action**: Check if already implemented (mentioned in README)
- **Priority**: Low - already has CLI flags like --whole-title

## GitHub Actions CI/CD

All contributions are automatically tested via GitHub Actions:

### CI Workflow (`ci.yml`)
- Runs on every push and pull request to main/master
- Jobs:
  - **Lint**: Code formatting check using yapf
  - **Unit Test**: Runs pytest test suite
  - **Type Check**: Static type checking with pytype
  - **Compatibility Test**: Tests across Python 3.8-3.12

### Release Workflow (`release.yml`)
- Triggers on version tags (e.g., `1.2.3`)
- Builds distribution packages
- Publishes to PyPI using trusted publishing

## Best Practices

1. **Always run tests locally before pushing**
   ```sh
   nox
   ```

2. **Keep PRs focused** - One feature or fix per PR

3. **Update documentation** - If the PR changes behavior, update docs

4. **Add tests** - New features and bug fixes should include tests

5. **Use descriptive commit messages** - Explain what and why, not just what

6. **Link issues and PRs** - Use `Closes #N` in PR descriptions

7. **Be responsive** - Address review comments promptly

## Maintainer Responsibilities

- Review PRs within 1 week
- Provide constructive feedback
- Test changes when appropriate
- Keep issues organized with labels
- Update this document as the process evolves
- Maintain the changelog
- Coordinate releases

## Getting Help

- Check the [CONTRIBUTING.md](../CONTRIBUTING.md) guide
- Review existing PRs and issues for examples
- Ask questions in issue comments
- Reference the original [google/pybadges](https://github.com/google/pybadges) repository
