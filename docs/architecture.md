# Dev-Ashy OS Architecture

## Overview

Dev-Ashy OS is built on Ubuntu 24.04 LTS with custom branding, themes, and pre-installed tools.

## Base System

| Component | Version | Source |
|-----------|---------|--------|
| Ubuntu | 24.04 LTS | Canonical |
| Kernel | 6.8 | Ubuntu |
| GNOME | 46 | Ubuntu |
| systemd | 255 | Ubuntu |

## Desktop Environment

- **GNOME 46** — Primary desktop environment
- **GTK 4** — Application toolkit
- **Wayland** — Display server (default)
- **Xorg** — Legacy display server (fallback)

## File System

- **ext4** — Default file system
- **Btrfs** — Optional, with snapshots
- **ZFS** — Optional, advanced features

## Boot Process

1. **UEFI/BIOS** — Firmware initialization
2. **GRUB 2** — Boot loader
3. **Linux Kernel** — System initialization
4. **systemd** — Service manager
5. **GDM** — Display manager
6. **GNOME** — Desktop environment

## ISO Structure

```
Dev-Ashy-OS-0.1.0-amd64.iso
├── boot/
│   ├── grub/           # GRUB configuration
│   ├── vmlinuz         # Linux kernel
│   └── initrd.img      # Initial RAM disk
├── casper/
│   ├── filesystem.squashfs  # Compressed root filesystem
│   ├── filesystem.manifest  # Package manifest
│   └── filesystem.size      # Size info
├── isolinux/           # BIOS boot files
├── preseed/            # Automated installation
└── .disk/              # Disk information
```

## Build System

The ISO is built using:

1. **Ubuntu Base ISO** — Starting point
2. **xorriso** — ISO extraction and creation
3. **mksquashfs** — Filesystem compression
4. **grub-mkrescue** — Boot loader creation
5. **Custom scripts** — Branding and configuration

## Package Management

- **APT** — Primary package manager
- **Snap** — Universal packages
- **Flatpak** — Sandboxed applications
- **AppImage** — Portable applications

## Security

- **AppArmor** — Application sandboxing
- **UFW** — Uncomplicated firewall
- **Secure Boot** — UEFI Secure Boot support
- **Full Disk Encryption** — LUKS encryption

## Customization

Dev-Ashy OS can be customized by:

1. Editing files in `config/`
2. Modifying branding in `branding/`
3. Adding packages to `packages/package-list.txt`
4. Creating custom scripts in `scripts/`

See [Building](building.md) for more information.
