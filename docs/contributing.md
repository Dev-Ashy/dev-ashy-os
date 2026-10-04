# Contributing to Dev-Ashy OS

Thank you for your interest in contributing to Dev-Ashy OS!

## Ways to Contribute

- **Report bugs** — Open an issue with details
- **Suggest features** — Open a discussion
- **Submit code** — Open a pull request
- **Improve docs** — Fix typos, add examples
- **Test builds** — Test and report issues
- **Spread the word** — Share Dev-Ashy OS

## Development Setup

```bash
# Clone the repository
git clone https://github.com/Dev-Ashy/dev-ashy-os.git
cd dev-ashy-os

# Install dependencies
sudo apt-get install cubic genisoimage xorriso squashfs-tools

# Build the ISO
./build-iso
```

## Project Structure

```
dev-ashy-os/
├── build-iso              # ISO build script
├── clean-iso-build        # Clean build artifacts
├── test-iso               # Test ISO in QEMU
├── verify-iso             # Verify ISO integrity
├── release-iso            # Release ISO
├── config/                # Configuration files
├── branding/              # Branding assets
├── scripts/               # Installation scripts
├── docs/                  # Documentation
├── packages/              # Package manifests
└── iso/                   # ISO output
```

## Pull Request Process

1. **Fork** the repository
2. **Create a branch** — `git checkout -b feature/my-feature`
3. **Make changes** — Follow code style guidelines
4. **Test changes** — Build and test the ISO
5. **Commit** — Use clear commit messages
6. **Push** — `git push origin feature/my-feature`
7. **Open PR** — Fill out the pull request template

## Code Style

### Shell Scripts

- Use 2-space indentation
- Add shebang: `#!/bin/bash`
- Use `set -e` for error handling
- Add comments for complex logic
- Use descriptive variable names

### Documentation

- Use Markdown
- Include examples
- Keep it concise
- Update CHANGELOG for significant changes

## Commit Messages

Use [Conventional Commits](https://www.conventionalcommits.org/):

```
feat: add new feature
fix: fix bug
docs: update documentation
style: format code
refactor: refactor code
test: add tests
chore: update dependencies
```

## Testing

Before submitting a PR:

```bash
# Build the ISO
./build-iso

# Test the ISO
./test-iso

# Verify the ISO
./verify-iso
```

## Code of Conduct

- Be respectful and inclusive
- Welcome newcomers
- Focus on constructive feedback
- Follow the [Contributor Covenant](https://www.contributor-covenant.org/)

## Questions?

- Open a [GitHub Discussion](https://github.com/Dev-Ashy/dev-ashy-os/discussions)
- Join our [Discord community](https://discord.gg/dev-ashy)
- Email: contributors@dev-ashy.com

## License

By contributing, you agree that your contributions will be licensed under the MIT License.
