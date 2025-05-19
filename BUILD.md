# Building iOS Apps with Expo

This guide explains how to build iOS apps for both Simulator and physical devices using Expo.

## Prerequisites

### For iOS Simulator Builds
- macOS (required for iOS development)
- Expo account
- EAS CLI installed and logged in
- iOS Simulator installed
- Development environment set up

### For iOS Device Builds
- macOS (required for iOS development)
- Expo account
- EAS CLI installed and logged in
- Paid Apple Developer account (required for device builds)
- Development environment set up

## Installation Steps

1. Install EAS CLI and login:
```bash
npm install -g eas-cli
eas login
```

2. Install expo-dev-client in your project:
```bash
npx expo install expo-dev-client
```

## Building for iOS Simulator

### Using EAS Build (Recommended)

1. Configure your `eas.json` to include a simulator profile:
```json
{
  "build": {
    "development-simulator": {
      "ios": {
        "simulator": true
      }
    }
  }
}
```

2. Run the build command:
```bash
eas build --platform ios --profile development-simulator
```

Note: iOS Simulator builds can only be installed on simulators, not on physical devices.

### Building Locally

To build locally without EAS:
```bash
npx expo run:ios
```

## Building for iOS Device

### Using EAS Build (Recommended)

1. Run the build command:
```bash
eas build --platform ios --profile development
```

Note: iOS device builds require a paid Apple Developer account and can only be installed on physical iPhone devices, not simulators.

### Building Locally

To build locally for a physical device:
```bash
npx expo run:ios --device
```

## Installing the Build

### For EAS Builds
- After the build completes, EAS CLI will prompt you to install the app
- You can also install previous builds from the expo.dev dashboard
- Use Expo Orbit to install builds from your local machine

### For Local Builds
- Local builds will be installed automatically once the build process completes

## Starting Development

After installing the build, start the development server:
```bash
npx expo start
```

This will start the JavaScript bundler and connect to your development build.

## Notes
- Development builds are essentially your own version of Expo Go
- You can use any native libraries and modify native configurations
- The development client persists between sessions - you only need to rebuild when making native code changes
- Keep your Apple Developer account credentials secure and up to date

## Troubleshooting

If you encounter any issues:
1. Ensure all prerequisites are met
2. Verify your Apple Developer account status
3. Check that your development environment is properly set up
4. Review the Expo documentation for specific error messages
5. Contact Expo support if issues persist
