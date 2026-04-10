# Apollo Automation Profile

A Google Chrome browser profile snapshot containing configuration, cache, and settings for Apollo platform testing and automation workflows. Includes pre-configured extensions, cached resources, and browser state optimized for Apollo automation.

## Overview

This repository contains a complete Chrome user profile directory that can be used to reproduce a specific browser environment for Apollo platform testing. It includes saved settings, extensions, cached data, and session storage configured for automation workflows.

## Features

- Pre-configured Chrome settings for Apollo platform integration
- Cached resources and code caches for faster test execution
- Saved session and authentication data
- Optimized extension configuration
- GPU-related optimization caches

## Contents

- **Default/** - Main Chrome profile directory with settings, bookmarks, and local storage
- **Cache/** - Browser HTTP cache and temporary data
- **Code Cache/** - Compiled JavaScript cache for performance
- **Session Storage/** - Persisted session and local storage data
- **Extensions/** - Chrome extension metadata and configuration
- **Shader & Graphics Caches/** - GPU optimization files (GrShaderCache, GraphiteDawnCache)
- **NativeMessagingHosts/** - Native application integration configuration

## Tech Stack

- **Chrome Browser** (v125+)
- **Apollo Platform** integrations
- Standard Chromium profile architecture with SQLite databases and LevelDB storage

## Setup Instructions

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/apollo-automation-profile.git
   cd apollo-automation-profile
   ```

2. **Environment Setup:**
   ```bash
   # No environment variables required (see .env.example)
   cp .env.example .env
   ```

3. **Locate Chrome profile directory:**
   - **macOS:** `~/Library/Application Support/Google/Chrome/`
   - **Windows:** `C:\Users\<USERNAME>\AppData\Local\Google\Chrome\User Data\`
   - **Linux:** `~/.config/google-chrome/`

4. **Import the profile:**
   ```bash
   # Backup your existing profile first (IMPORTANT)
   mv ~/Library/Application\ Support/Google/Chrome/Default ~/Library/Application\ Support/Google/Chrome/Default.backup
   
   # Copy this profile
   cp -r apollo-automation-profile ~/Library/Application\ Support/Google/Chrome/Default
   ```

5. **Restart Chrome** to load the imported profile.

## Usage Example

After importing this profile into Chrome, you'll have:
```bash
# Launch Chrome with the profile
google-chrome --profile-directory=Default

# Or with additional automation flags
google-chrome --profile-directory=Default --headless --no-sandbox --disable-dev-shm-usage
```

The profile includes:
- Pre-configured settings for Apollo platform automation
- Cached resources for faster testing cycles
- Saved session information and authentication data
- Optimized extensions for testing workflows

## Important Notes

- **Backup first:** Always backup your existing Chrome profile before importing
- **Single instance:** Do not use this profile with multiple Chrome instances simultaneously
- **Browser compatibility:** Designed for Chrome v125+; compatibility with other versions may vary
- **Cache staleness:** Some cached data may become obsolete; Chrome will refresh as needed
- **Authentication:** Session cookies expire; re-authentication may be required for services
- **File size:** This profile directory is large due to cache files; they can be cleaned without losing settings
- **Privacy:** Contains browser history and cached web content; use with appropriate privacy considerations

## File Structure Reference

- `.db` files: SQLite databases (bookmarks, history, preferences, web apps)
- `.log` files: LevelDB transaction logs (cache, session, local storage)
- `Cache_Data/` directories: HTTP cache and cached resources
- `Local Storage/` and `IndexedDB/`: Web application persistent storage
- `Extensions/`: Extension IDs and their data

## License

[Specify your license here, e.g., MIT, Apache 2.0]
