# Dev-Ashy OS Release Process

## Pre-Release Checklist

- [ ] All tests pass
- [ ] ISO builds successfully
- [ ] Checksums generated
- [ ] Documentation updated
- [ ] CHANGELOG updated
- [ ] Version number bumped

## Version Numbering

Dev-Ashy OS follows [Semantic Versioning](https://semver.org/):

- **Major** (x.0.0) — Breaking changes
- **Minor** (0.x.0) — New features
- **Patch** (0.0.x) — Bug fixes

## Release Steps

### 1. Update Version

Edit `build-iso` and update:

```bash
VERSION="0.1.0"
```

### 2. Update CHANGELOG

Add new entry to `CHANGELOG.md`:

```markdown
## [0.1.0] - 2026-10-04

### Added
- Initial release
```

### 3. Build ISO

```bash
./build-iso
```

### 4. Test ISO

```bash
./test-iso
./verify-iso
```

### 5. Create Release

```bash
./release-iso 0.1.0
```

### 6. Create GitHub Release

```bash
# Create tag
git tag -a v0.1.0 -m "Dev-Ashy OS v0.1.0"
git push origin v0.1.0

# Create GitHub release
gh release create v0.1.0 \
    releases/iso/Dev-Ashy-OS-0.1.0-amd64.iso \
    releases/iso/SHA256SUMS \
    releases/iso/ISO-SOFTWARE-MANIFEST.txt \
    --title "Dev-Ashy OS v0.1.0" \
    --notes-file releases/iso/RELEASE-NOTES.md
```

## Release Artifacts

Each release should include:

| File | Description |
|------|-------------|
| `Dev-Ashy-OS-0.1.0-amd64.iso` | Bootable ISO |
| `SHA256SUMS` | Checksums |
| `ISO-SOFTWARE-MANIFEST.txt` | Package list |
| `RELEASE-NOTES.md` | Release notes |

## Post-Release

1. Update website with download link
2. Announce on social media
3. Monitor for issues
4. Plan next release

## Emergency Releases

For critical security fixes:

1. Bump patch version (e.g., 0.1.0 → 0.1.1)
2. Fix the issue
3. Test thoroughly
4. Release immediately
5. Notify users

## Release Schedule

- **Alpha:** As needed for testing
- **Beta:** Monthly
- **Stable:** Quarterly

## Next Steps

- [Building](building.md) — Build from source
- [Testing](testing.md) — Test the ISO
- [Installation](installation.md) — Install the ISO
