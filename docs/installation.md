# Dev-Ashy OS Installation Guide

## System Requirements

| Component | Minimum | Recommended |
|-----------|---------|-------------|
| CPU | 64-bit dual-core | 64-bit quad-core |
| RAM | 4 GB | 8 GB |
| Disk | 25 GB | 50 GB |
| USB | 4 GB | 8 GB |

## Creating Bootable USB

### Linux

```bash
sudo dd if=Dev-Ashy-OS-0.1.0-amd64.iso of=/dev/sdX bs=4M status=progress oflag=sync
```

Replace `/dev/sdX` with your USB device (e.g., `/dev/sdb`).

### macOS

```bash
sudo dd if=Dev-Ashy-OS-0.1.0-amd64.iso of=/dev/diskX bs=4m
```

Replace `/dev/diskX` with your USB device (e.g., `/dev/disk2`).

### Windows

1. Download [Rufus](https://rufus.ie/)
2. Select your USB drive
3. Select the Dev-Ashy OS ISO
4. Click "Start"

## Installation Steps

1. **Boot from USB** — Insert USB and boot from it (may need to change boot order in BIOS/UEFI)
2. **Select "Install Dev-Ashy OS"** — Choose the installer option
3. **Choose language** — Select your preferred language
4. **Configure keyboard** — Select your keyboard layout
5. **Partition disk** — Choose automatic or manual partitioning
6. **Create user** — Enter your name, username, and password
7. **Wait for installation** — This may take 15-30 minutes
8. **Reboot** — Remove USB and reboot

## First Boot

After installation, you'll see the Dev-Ashy login screen. Log in with your credentials.

### Run Setup

Open a terminal and run:

```bash
dev-ashy-setup
```

This will:
- Update the system
- Install additional tools
- Configure Git
- Set up AI tools
- Install security tools

## Troubleshooting

### Boot failure
- Check BIOS/UEFI settings (disable Secure Boot if needed)
- Try recreating the USB with a different tool

### Installation fails
- Check disk space
- Verify ISO checksum
- Try a different USB drive

### No internet connection
- Check network cable or WiFi
- Try a different network

## Next Steps

After installation, see:
- [Building](building.md) — Build from source
- [Testing](testing.md) — Test the ISO
- [AI Tools](ai-tools.md) — Set up AI tools
- [Security](security.md) — Security tools guide
