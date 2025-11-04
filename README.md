# Snapchat Blocker

[![Download APK](https://img.shields.io/github/v/release/eliasfloreteng/block-snapchat-discover-and-spotlight?label=Download%20APK&style=for-the-badge&logo=android)](https://github.com/eliasfloreteng/block-snapchat-discover-and-spotlight/releases/latest/download/app-release.apk)

Android app that uses Accessibility Services to automatically block specific sections in apps by detecting UI text patterns and returning to the home screen.

## Features

- **Customizable App Blocking**: Block any Android app by package name
- **Text-Based Detection**: Define custom strings to detect and block specific pages
- **Automatic Exit**: Automatically presses back and goes home when blocked content is detected
- **Multiple Apps**: Configure blocking for multiple apps simultaneously
- **Real-time Updates**: Settings changes apply within 5 seconds without restarting

## How It Works

1. Uses Android Accessibility Services to monitor app UI elements
2. Scans for configured text strings in visible content
3. When detected, automatically exits the blocked section
4. Debouncing prevents multiple triggers (2-second cooldown)

## Setup

1. Install and open the app
2. Grant notification permission (Android 13+)
3. Tap "Open Accessibility Settings"
4. Enable "Snapchat Blocker"
5. Return to app and verify service status

## Configuration

Default configuration blocks Snapchat Discover:

- **App**: Snapchat (`com.snapchat.android`)
- **Blocked Strings**: "View Profile", "For you"

### Adding Apps

1. Open app → tap "Settings"
2. Tap the "+" button
3. Enter app name, package name, and blocked strings (one per line)
4. Tap "Add"

### Editing Apps

1. Tap "Edit" on any app card
2. Modify app name or blocked strings
3. Tap "Save"

## Requirements

- Android 12 (API 31) or higher
- Accessibility Service permission

## Technical Details

- **Language**: Kotlin
- **UI**: Jetpack Compose
- **Storage**: SharedPreferences + Gson
- **Min SDK**: 31
- **Target SDK**: 36

## Permissions

- `BIND_ACCESSIBILITY_SERVICE` - Monitor app UI
- `POST_NOTIFICATIONS` - Show toast notifications

## Notes

- Settings reload automatically every 5 seconds
- Service must be enabled in Accessibility Settings after each device restart
- Works on any app where text-based detection is reliable
