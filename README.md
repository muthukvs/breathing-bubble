# 🫁 Breathing Bubble

A minimalist Flutter app for mindful breathing. Open the app, watch the bubble, breathe along.

**Features:**
- ✨ Simple, calming interface
- ⏱️ 4-second inhale + 4-second exhale cycle
- 📱 iOS & Android support
- 🚀 Zero setup required

## Quick Start

### Prerequisites
- Flutter 3.16.0+
- Dart 3.0.0+

### Local Development

```bash
# Clone
git clone https://github.com/muthukvs/breathing-bubble.git
cd breathing-bubble

# Get dependencies
flutter pub get

# Run
flutter run
```

## Deployment

### Google Play (Android)

1. **Create keystore** (one-time):
   ```bash
   keytool -genkey -v -keystore ~/breathing_bubble.keystore \
     -keyalg RSA -keysize 2048 -validity 10000 \
     -alias breathing_bubble
   ```

2. **Create `android/key.properties`**:
   ```properties
   storePassword=YOUR_PASSWORD
   keyPassword=YOUR_PASSWORD
   keyAlias=breathing_bubble
   storeFile=/path/to/breathing_bubble.keystore
   ```

3. **Build signed APK**:
   ```bash
   flutter build apk --release
   ```
   APK: `build/app/outputs/flutter-apk/app-release.apk`

4. **Upload to Play Store**:
   - Go to [play.google.com/console](https://play.google.com/console)
   - Create app → Upload APK → Internal testing → Release
   - **Timeline:** 30 min - few hours

### Apple App Store (iOS)

1. **Setup Code Signing** (in Xcode):
   ```bash
   open ios/Runner.xcworkspace
   ```
   - Select Runner → Signing & Capabilities
   - Set Team ID

2. **Build for iOS**:
   ```bash
   flutter build ios --release
   ```

3. **Archive in Xcode**:
   - Product → Archive → Distribute → TestFlight/App Store
   - **Timeline:** 1-3 days review

## GitHub Actions CI/CD

Everytime you push to `main`, GitHub Actions automatically:
- ✅ Builds APK for Android
- ✅ Builds IPA for iOS
- ✅ Uploads artifacts for download

Check progress: **Actions tab** → Latest workflow

## Architecture

- **Animation**: `AnimationController` + `ScaleTransition`
- **UI**: Single screen with gradient + glow effects
- **State**: Stateful widget with lifecycle management
- **Performance**: 60fps native animations

## Project Structure

```
breathing-bubble/
├── lib/main.dart              # Main app
├── pubspec.yaml              # Dependencies
├── .github/workflows/build.yml # CI/CD
├── android/                  # Android config
├── ios/                      # iOS config
└── README.md
```

## Next Steps

1. Clone locally: `git clone https://github.com/muthukvs/breathing-bubble.git`
2. Run: `flutter run`
3. Build: `flutter build apk --release` or `flutter build ios --release`
4. Upload to stores (see Deployment section)

---

**Made with ❤️ for mindful breathing**
