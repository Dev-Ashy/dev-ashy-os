# Contributing to Dev-Ashy OS

Thank you for your interest in contributing to Dev-Ashy OS!

## Getting Started

1. Fork the repository
2. Create a new branch: `git checkout -b feature/my-feature`
3. Make your changes
4. Test your changes
5. Submit a pull request

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
│   ├── wallpaper.svg      # Default wallpaper
│   └── theme/             # GTK theme
├── scripts/               # Installation scripts
│   ├── dev-ashy-setup     # First-boot setup
│   ├── install-dev-tools  # Development tools
│   ├── install-ai-tools   # AI tools
│   ├── install-security-tools  # Security tools
│   ├── install-mobile-tools    # Mobile tools
│   └── install-creative-tools  # Creative tools
├── docs/                  # Documentation
├── packages/              # Package manifests
└── iso/                   # ISO output
```

## Pull Request Guidelines

1. **One feature per PR** — Keep changes focused
2. **Write clear commit messages** — Use conventional commits
3. **Test your changes** — Build and test the ISO
4. **Update documentation** — Keep docs in sync
5. **Follow code style** — Use consistent formatting

## Code Style

- Use 2-space indentation for shell scripts
- Use 4-space indentation for other files
- Add comments for complex logic
- Keep functions small and focused

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

## Questions?

Open a discussion on GitHub or join our Discord community.
