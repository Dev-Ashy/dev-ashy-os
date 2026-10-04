# Dev-Ashy OS

**Your developer workstation, rebuilt.**

Dev-Ashy OS is a modern, developer-focused Linux distribution built around Ubuntu. It comes pre-installed with everything you need for software development, AI development, cybersecurity, mobile development, and creative work.

## Features

- **Developer-First** — Pre-installed with Node.js, Python, Go, Rust, Java, and more
- **AI-Ready** — Compatible with Ollama, OpenCode, Gemini CLI, and Hermes Agent
- **Security Tools** — Nmap, Metasploit, Wireshark, and more
- **Mobile Development** — React Native, Expo, Android SDK
- **Creative Tools** — FFmpeg, OBS Studio, GIMP, Blender
- **Dev-Ashy Branding** — Custom themes, wallpapers, and terminal configuration

## Quick Start

### Download

Download the latest ISO from [GitHub Releases](https://github.com/Dev-Ashy/dev-ashy-os/releases).

### Create Bootable USB

```bash
# Linux
sudo dd if=Dev-Ashy-OS-0.1.0-amd64.iso of=/dev/sdX bs=4M status=progress

# macOS
sudo dd if=Dev-Ashy-OS-0.1.0-amd64.iso of=/dev/diskX bs=4m

# Windows
# Use Rufus: https://rufus.ie/
```

### Install

1. Boot from USB
2. Select "Install Dev-Ashy OS"
3. Follow the installer
4. Reboot and enjoy

## First Boot

After installation, run the setup script:

```bash
dev-ashy-setup
```

This will:
- Update the system
- Install additional tools
- Configure Git
- Set up AI tools
- Install security tools

## Optional Installers

```bash
# Install development tools
install-dev-tools

# Install AI tools
install-ai-tools

# Install security tools
install-security-tools

# Install mobile development tools
install-mobile-tools

# Install creative tools
install-creative-tools
```

## Building from Source

### Prerequisites

```bash
sudo apt-get install cubic genisoimage xorriso squashfs-tools
```

### Build

```bash
# Clone the repository
git clone https://github.com/Dev-Ashy/dev-ashy-os.git
cd dev-ashy-os

# Build the ISO
./build-iso

# Test the ISO
./test-iso

# Verify the ISO
./verify-iso

# Release
./release-iso 0.1.0
```

## Documentation

- [Installation Guide](docs/installation.md)
- [System Requirements](docs/requirements.md)
- [Architecture](docs/architecture.md)
- [Package List](docs/packages.md)
- [Building](docs/building.md)
- [Testing](docs/testing.md)
- [Troubleshooting](docs/troubleshooting.md)
- [Release Process](docs/release.md)
- [AI Tools](docs/ai-tools.md)
- [Security](docs/security.md)
- [Contributing](docs/contributing.md)

## System Requirements

| Component | Minimum | Recommended |
|-----------|---------|-------------|
| CPU | 64-bit dual-core | 64-bit quad-core |
| RAM | 4 GB | 8 GB |
| Disk | 25 GB | 50 GB |
| USB | 4 GB | 8 GB |

## License

Dev-Ashy OS is built on Ubuntu and uses the same licenses. See [LICENSE](LICENSE) for details.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## Support

- GitHub Issues: https://github.com/Dev-Ashy/dev-ashy-os/issues
- Documentation: https://dev-ashy.com/docs
- Community: https://discord.gg/dev-ashy

---

**Dev-Ashy OS** — Build beyond the screen.
