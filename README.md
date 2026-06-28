# GitHub Actions

Reusable GitHub Actions workflows.

## Workflows

### 1. Reusable OpenCode (`opencode.yml`)

A general-purpose workflow for running OpenCode on your repository.

**Use Cases:**
- General code questions
- Bug investigation
- Feature implementation assistance
- Code exploration

### 2. Reusable OpenCode Review (`opencode-review.yml`)

A specialized workflow for comprehensive pull request code reviews.

**Use Cases:**
- Pull request code reviews
- Architecture and design reviews
- Security and performance analysis

## Setup

### Prerequisites

1. **GitHub Repository** with Actions enabled
3. **Target Repository** where you want to run OpenCode

## Usage

### Calling from Other Workflows

These workflows are designed to be called from other workflows in your repositories:

```yaml
jobs:
  review:
    uses: bruno303/github-actions/.github/workflows/opencode-review.yml@main
    secrets:
      token: ${{ secrets.GITHUB_TOKEN }}
    with:
      repository: owner/repo-name
```

## Configuration

### Permissions

Both workflows require:
- `id-token: write` - For OpenCode authentication
- `contents: write` - To checkout code
- `pull-requests: write` - To post reviews
- `issues: write` - To interact with issues

## Features

### Code Review Capabilities

The review workflow focuses on:
- **Inconsistent behavior** - Logic that behaves differently across similar flows
- **Edge cases and correctness** - Null pointer risks, missing guards, boundary conditions
- **Clean Architecture** - Separation of concerns, dependency direction
- **Code complexity** - Overly complex functions, duplication, hidden side effects
- **Regression risk** - Changes that might break existing functionality
- **Security** - Data exposure risks, vulnerabilities
- **Performance** - Unnecessary queries, loops, allocations
- **Test coverage** - Missing or weak tests for important paths

### Global Skills

Both workflows install global skills from `bruno303/ai-tools` repository to enhance OpenCode's capabilities.

## License

MIT License - see [LICENSE](LICENSE) for details.

## Support

- [OpenCode Documentation](https://github.com/anomalyco/opencode)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Report Issues](https://github.com/bruno303/github-actions/issues)
