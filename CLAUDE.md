# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **setup guide and distribution repository** for **SPT (Single Player Tarkov) v4.1.3** and **Fika v2.4.2**. The primary purpose is to provide clear installation instructions and distribute mod packages to users.

**Key deliverables:**
- `README.md` - Comprehensive setup guide with step-by-step instructions
- GitHub releases - Distribute installers, runtimes, and optional mod bundles

## Repository Structure

```
├── README.md                 # Main setup guide and mod documentation
├── mods/                     # Mod package files (zips, 7z archives) for v1.0.0-mods release
├── installers/               # Installer and runtime files for v1.0.0 release
├── assets/                   # Images and media for documentation
├── profiles/                 # SPT game profile backups
└── .claude/settings.local.json # Claude Code permissions config
```

## Release Management

### Release Tiers

**v1.0.0 - Base Setup Package**
- Contains runtimes (DotNet 10, ASP.NET 10)
- Contains installers (Battlestate Games Launcher, SPT, Fika)
- **Currently appears to be empty after recent cleanup**

**v1.0.0-mods - Quality-of-Life Mods Bundle**
- Contains SPT Mod Manager utility
- Contains **Required Mods**: DynamicMaps, UIFixes (tested for headless)
- Contains **Optional Mods**: 11 additional quality-of-life mods organized by category
  - Search & Filter Tools (4 mods)
  - Information & Display (2 mods)
  - Inventory & Trading (3 mods)
  - Gameplay Improvements (2 mods)

### Common Release Tasks

**Upload a new mod to v1.0.0-mods:**
```bash
gh release upload v1.0.0-mods path/to/ModName-Version.zip --clobber
```

**Remove an asset from a release:**
```bash
gh release delete-asset v1.0.0-mods "AssetName.zip" --yes
```

**View all assets in a release:**
```bash
gh release view v1.0.0-mods --json assets
```

**⚠️ Release Maintenance**
After creating or updating releases, always remove auto-generated source code files (GitHub creates `Source code (zip)` and `Source code (tar.gz)` automatically). These are unnecessary bloat for distribution releases. Keep releases clean with only the actual installer/mod files users need to download.

## Documentation (README.md) Patterns

### Table Formatting

All component/mod names in reference tables are **clickable links** to their official sources:
- **Mods**: Link to sp-mod.com page
- **Utilities**: Link to official tool page
- **Runtimes/Applications**: Link directly to download

Example pattern:
```markdown
| **[Component Name](https://url-to-official-source)** | Description | Version | File |
```

### Mod Organization Structure

**Required Mods Section:**
- Contains only mods critical for server operation
- Clearly indicates they've been tested for headless environments

**Optional Mods Section:**
- Includes disclaimer: NOT tested for headless, won't be enabled on server
- Users can test locally but results not guaranteed
- Organized into subcategories by function
- Can be promoted to Required section after testing

## GitHub CLI Requirements

This project uses `gh` (GitHub CLI) for release management. Common commands used:

```bash
# View release info
gh release view <release-tag> --json assets

# Upload files to release
gh release upload <release-tag> <file-path> --clobber

# Delete asset from release
gh release delete-asset <release-tag> <asset-name> --yes

# Create new release
gh release create <tag> <file-paths> -t "Title" -n "Notes"
```

## Workflow Notes

### Updating README

When modifying documentation:
1. Update README.md with changes
2. Commit with descriptive message
3. Push to main
4. Verify changes render correctly in GitHub

### Adding/Updating Mods

When adding a new mod or updating existing ones:
1. Place mod file in `mods/` folder
2. Update README.md mods table with:
   - Mod name as clickable link to sp-mod.com
   - Description
   - Version
   - File name
3. Add file to appropriate release (`v1.0.0-mods`)
4. Commit and push

### Testing Status for New Mods

New mods should start in the Optional section with:
- No checkmarks in "Required" or "Headless Tested"
- Listed under disclaimer that they haven't been tested
- Can be promoted to Required once verified for headless compatibility

## Known Issues / Notes

- Source code auto-generated assets (tar.gz, zip) have been removed from both releases to keep distributions clean
- Installer files in `installers/` folder are kept locally and uploaded to v1.0.0 release as needed
- Mod files in `mods/` folder are kept locally and uploaded to v1.0.0-mods release

## Permissions Configured

The `.claude/settings.local.json` has these permissions for this project:
- WebFetch to sp-mod.com and github.com
- GitHub CLI (gh) operations for releases
- Git operations for commits and adds
