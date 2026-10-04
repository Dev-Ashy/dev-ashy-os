# Building Dev-Ashy OS

## Prerequisites

### Required Tools

```bash
sudo apt-get install -y \
    cubic \
    genisoimage \
    xorriso \
    squashfs-tools \
    curl \
    git
```

### Disk Space

- **Minimum:** 20 GB free space
- **Recommended:** 50 GB free space

### Time

- **Download:** 10-30 minutes (depending on internet speed)
- **Build:** 30-60 minutes
- **Total:** 1-2 hours

## Quick Build

```bash
# Clone the repository
git clone https://github.com/Dev-Ashy/dev-ashy-os.git
cd dev-ashy-os

# Build the ISO
./build-iso
```

## Build Process

### 1. Download Ubuntu ISO

The build script automatically downloads the Ubuntu 24.04 Desktop ISO if not present.

### 2. Extract ISO

The ISO is extracted using `xorriso`:

```bash
xorriso -osirrox on -indev ubuntu-24.04-desktop-amd64.iso -extract / work/
```

### 3. Apply Branding

Dev-Ashy branding is applied:

- Wallpapers
- Themes
- Icons
- Terminal configuration

### 4. Customize Packages

Package lists are applied from `packages/package-list.txt`.

### 5. Add Scripts

Installation scripts are added to the filesystem.

### 6. Build SquashFS

The filesystem is compressed:

```bash
mksquashfs work/ filesystem.squashfs -comp xz -b 1M -noappend
```

### 7. Build ISO

The final ISO is created:

```bash
grub-mkrescue -o Dev-Ashy-OS-0.1.0-amd64.iso work/
```

### 8. Generate Checksums

SHA256 checksums are generated:

```bash
sha256sum Dev-Ashy-OS-0.1.0-amd64.iso > SHA256SUMS
```

## Build Options

### Clean Build

```bash
# Clean previous build artifacts
./clean-iso-build

# Build from scratch
./build-iso
```

### Custom Version

```bash
# Edit build-iso and change VERSION
VERSION="0.2.0"
```

### Skip Download

If you already have the Ubuntu ISO:

```bash
# Place ISO in build/
cp ubuntu-24.04-desktop-amd64.iso build/

# Build (will use existing ISO)
./build-iso
```

## Troubleshooting

### Build fails

1. Check disk space: `df -h`
2. Check dependencies: `which xorriso mksquashfs grub-mkrescue`
3. Check logs: `cat build/logs/*.log`

### ISO too large

- Remove unnecessary packages from `packages/package-list.txt`
- Use higher compression: `-comp xz -Xbcj x86`

### Boot failure

- Verify ISO checksum: `sha256sum -c SHA256SUMS`
- Try different USB creation tool
- Check BIOS/UEFI settings

## Advanced: Using Cubic

For a graphical ISO customization experience:

```bash
# Install Cubic
sudo apt-get install cubic

# Launch Cubic
cubic
```

Cubic provides a chroot environment for manual customization.

## Next Steps

- [Testing](testing.md) — Test the ISO
- [Release](release.md) — Create a release
- [Installation](installation.md) — Install the ISO
