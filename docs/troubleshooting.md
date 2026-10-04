# Dev-Ashy OS Troubleshooting

## Build Issues

### Missing Dependencies

**Error:** `command not found: xorriso`

**Fix:**
```bash
sudo apt-get install xorriso
```

### Disk Space

**Error:** `No space left on device`

**Fix:**
```bash
# Clean build artifacts
./clean-iso-build

# Check disk space
df -h

# Free up space
sudo apt-get clean
sudo apt-get autoremove
```

### Download Fails

**Error:** `curl: (22) The requested URL returned error: 404`

**Fix:**
```bash
# Check Ubuntu download URL
curl -I https://releases.ubuntu.com/24.04/

# Try alternative mirror
# Edit build-iso and change download URL
```

## Boot Issues

### ISO Won't Boot

**Symptoms:** Black screen or error when booting from USB

**Fixes:**
1. Verify ISO checksum: `sha256sum -c SHA256SUMS`
2. Recreate USB with different tool
3. Try different USB port
4. Check BIOS/UEFI settings (disable Secure Boot)

### GRUB Errors

**Error:** `grub rescue>`

**Fix:**
```bash
# Boot from live USB
# Open terminal and run:
sudo fdisk -l
sudo mount /dev/sdX1 /mnt
sudo grub-install --boot-directory=/mnt/boot /dev/sdX
```

## Installation Issues

### Disk Not Detected

**Symptoms:** Installer doesn't show any disks

**Fixes:**
1. Check BIOS/UEFI settings (AHCI mode)
2. Try different SATA port
3. Check disk connections

### Installation Fails

**Error:** `Installation failed`

**Fixes:**
1. Check disk space (minimum 25 GB)
2. Verify ISO checksum
3. Try manual partitioning
4. Check logs: `/var/log/installer/`

## Desktop Issues

### No Desktop

**Symptoms:** Black screen or terminal only after login

**Fixes:**
```bash
# Reinstall GNOME
sudo apt-get install --reinstall ubuntu-desktop

# Reset GNOME settings
dconf reset -f /org/gnome/
```

### Theme Not Applied

**Symptoms:** Default Ubuntu theme instead of Dev-Ashy

**Fixes:**
```bash
# Reapply theme
cp -r /usr/share/themes/Dev-Ashy ~/.themes/
gnome-tweaks  # Select Dev-Ashy theme
```

## Network Issues

### No Internet

**Symptoms:** No network connection

**Fixes:**
```bash
# Check network status
nmcli device status

# Restart network
sudo systemctl restart NetworkManager

# Check WiFi
nmcli device wifi list
nmcli device wifi connect "SSID" password "password"
```

## Tool Issues

### Ollama Won't Start

**Error:** `ollama: command not found`

**Fix:**
```bash
# Reinstall Ollama
curl -fsSL https://ollama.com/install.sh | sh

# Start Ollama
ollama serve
```

### GitHub CLI Not Authenticated

**Error:** `gh auth status` shows not authenticated

**Fix:**
```bash
gh auth login
```

## Getting Help

If you can't find a solution:

1. Check [GitHub Issues](https://github.com/Dev-Ashy/dev-ashy-os/issues)
2. Open a new issue with details
3. Join our [Discord community](https://discord.gg/dev-ashy)

## Next Steps

- [Installation](installation.md) — Install Dev-Ashy OS
- [Building](building.md) — Build from source
- [Testing](testing.md) — Test the ISO
- [Release](release.md) — Create a release
