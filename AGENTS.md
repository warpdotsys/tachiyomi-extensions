# Warpdotsys Tachiyomi Extensions Repository

## Overview
This repository contains Tachiyomi extensions and related repositories for manga/anime sources. The main project is a Gradle-based multi-module build with Kotlin code.

## Key Commands

### Build and Test Commands
```bash
# Build all extensions
./gradlew assembleRelease

# Build specific extension
./gradlew :src:all:hitomi:assembleRelease

# Run code formatting
./gradlew spotlessApply

# Run tests
./gradlew test
```

## Repository Structure
- `src/` - Main source extensions (manga/anime sources)
- `lib/` - Shared libraries
- `lib-multisrc/` - Multi-source templates
- `common/` - Shared build configuration
- `.github/workflows/` - CI workflows

## Key Files and Directories
- `settings.gradle.kts` - Project module configuration
- `build.gradle.kts` - Root build configuration
- `src/*/build.gradle` - Extension build files
- `src/*/*/src/` - Extension source code
- `.github/scripts/` - CI helper scripts

## Development Workflow
1. Run `./gradlew spotlessApply` to format code
2. Run `./gradlew assembleRelease` to build
3. Check CI logs if build fails

## CI/CD Information
- GitHub Actions in `.github/workflows/`
- Builds triggered on push to master
- Builds extensions and publishes to repo

## Repository Specifics
- Extensions use `src/[lang]/[name]` structure
- Each extension has its own `build.gradle` file
- Extensions are built as separate APKs
- Publishing requires `BOT_PAT` secret for repo deployment

## Common Issues
- Kotlin code formatting must pass `spotlessCheck`
- Extension version codes must be within allowed range (1.3-1.5 for current tachiyomi)
- Network-dependent extensions may need updated URLs/APIs