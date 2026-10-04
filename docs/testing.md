# Testing Dev-Ashy OS

## QEMU Testing

### Quick Test

```bash
# Test the ISO
./test-iso
```

### Custom Test

```bash
# Test with specific options
./test-iso /path/to/Dev-Ashy-OS-0.1.0-amd64.iso
```

### Manual QEMU

```bash
# Create disk image
qemu-img create -f qcow2 test-disk.qcow2 20G

# Boot ISO
qemu-system-x86_64 \
    -m 4096 \
    -smp 2 \
    -cdrom Dev-Ashy-OS-0.1.0-amd64.iso \
    -drive file=test-disk.qcow2,format=qcow2 \
    -boot d \
    -net nic -net user \
    -vga virtio \
    -display sdl
```

## Test Checklist

### Boot

- [ ] ISO boots in QEMU
- [ ] GRUB menu appears
- [ ] Live environment starts
- [ ] Installer starts

### Installation

- [ ] Disk detection works
- [ ] Partitioning works
- [ ] User creation works
- [ ] Bootloader installation works
- [ ] System reboots after installation

### Desktop

- [ ] GNOME loads
- [ ] Wallpaper is Dev-Ashy branded
- [ ] Theme is applied
- [ ] Terminal opens
- [ ] Network works

### Tools

- [ ] Git works
- [ ] GitHub CLI works
- [ ] Node.js works
- [ ] Python works
- [ ] Go works
- [ ] Rust works

### AI Tools

- [ ] Ollama installs
- [ ] OpenCode installs
- [ ] Gemini CLI installs
- [ ] Hermes Agent installs

### Security Tools

- [ ] Nmap works
- [ ] Wireshark works
- [ ] Metasploit works

### Mobile Tools

- [ ] React Native CLI works
- [ ] Expo CLI works
- [ ] Android SDK works

### Creative Tools

- [ ] FFmpeg works
- [ ] OBS Studio works
- [ ] GIMP works
- [ ] Blender works

## Automated Testing

### Create Test Script

```bash
#!/bin/bash
# test-all.sh

ISO="$1"

echo "Testing Dev-Ashy OS ISO..."

# Verify ISO
./verify-iso "$ISO"

# Boot test
timeout 60 ./test-iso "$ISO"

# Check results
if [ $? -eq 0 ]; then
    echo "All tests passed!"
else
    echo "Tests failed!"
    exit 1
fi
```

### Run Tests

```bash
chmod +x test-all.sh
./test-all.sh Dev-Ashy-OS-0.1.0-amd64.iso
```

## Performance Testing

### Boot Time

```bash
# Measure boot time
systemd-analyze
```

### Resource Usage

```bash
# Check memory usage
free -h

# Check disk usage
df -h

# Check CPU usage
htop
```

## Reporting Issues

When reporting test failures, include:

1. ISO version and checksum
2. Test environment (QEMU version, host OS)
3. Error messages or screenshots
4. Steps to reproduce

## Next Steps

- [Building](building.md) — Build from source
- [Release](release.md) — Create a release
- [Troubleshooting](troubleshooting.md) — Fix common issues
