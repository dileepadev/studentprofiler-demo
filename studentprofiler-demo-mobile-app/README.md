# Student Profiler Demo - Mobile App

This is a demo mobile application for the Student Profiler system, built using Flutter. It provides a cross-platform interface for users (teachers, administrators) to interact with the student profiling system, manage data, and view results on the go.

## Features

- **Cross-Platform Support**: Runs on Android, iOS, and Web.
- **User Authentication**: Secure login and management using Firebase Auth.
- **Data Synchronization**: Real-time data updates with Cloud Firestore.
- **Media Handling**: functionality to capture and upload images using Image Picker and Firebase Storage.
- **Student/Teacher Profiling**: Interfaces to view and manage profiles.

## Tech Stack

- **Framework**: Flutter
- **Language**: Dart
- **Backend**: Firebase (Auth, Firestore, Storage)

### Dependencies & Version Comparison

The following table outlines the dependencies used in the project, comparing the original legacy versions with the current updated versions.

| Dependency | Original (Legacy) Version | Updated Version |
| :--- | :--- | :--- |
| flutter_native_splash | ^2.3.1 | ^2.3.1 |
| rename | ^2.1.1 | ^3.1.0 |
| firebase_core | ^2.15.1 | ^4.3.0 |
| firebase_auth | ^4.7.3 | ^6.1.3 |
| cloud_firestore | ^4.8.5 | ^6.1.1 |
| firebase_storage | ^11.2.6 | ^13.0.5 |
| intl | ^0.18.1 | ^0.20.2 |
| image_picker | ^1.0.2 | ^1.0.2 |
| flutter_lints | ^2.0.0 | ^6.0.0 |
| flutter_launcher_icons | ^0.13.1 | ^0.14.4 |

## Project Structure

```markdown
studentprofiler-demo-mobile-app/
├── lib/
│   ├── main.dart           # Application entry point
│   ├── models/             # Data models for Firestore objects
│   ├── pages/              # UI Screens and Widgets
│   ├── services/           # Firebase and logic services
│   └── theme/              # App theming and styling
├── android/                # Android native project files
├── ios/                    # iOS native project files
├── assets/                 # Static assets (images, icons)
├── pubspec.yaml            # Dart/Flutter dependency configuration
└── analysis_options.yaml   # Linter rules
```

## Setup Instructions

### Prerequisites

Before you get started, ensure your environment matches the requirements below.

#### Environment Versions

| Component | Original (Legacy) Version | Updated Version |
| :--- | :--- | :--- |
| Flutter SDK | 3.13.0 | 3.38.5 |
| Dart SDK | 3.1.0 | 3.10.4 |
| Android Gradle Plugin | 7.3.0 | 8.6.0 |
| Gradle | 7.5 | 8.7 |
| Kotlin | 1.6.10 | 2.0.21 |
| Java JDK | 11 | 25 |

### Installation

1. **Navigate to the directory:**

    ```bash
    cd studentprofiler-demo/studentprofiler-demo-mobile-app
    ```

2. **Install dependencies:**

    ```bash
    flutter pub get
    ```

3. **Firebase Configuration:**

    - Ensure you have `google-services.json` (Android) and `GoogleService-Info.plist` (iOS) placed in their respective directories if connecting to your own Firebase instance.

## Usage

### Running the Application

To run the app on a connected device or emulator:

```bash
flutter run
```

To build a release APK for Android:

```bash
flutter build apk --release
```

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License

[MIT](../LICENSE)

## Developers

- **Dileepa Bandara** - *Initial work* - [dileepadev](https://github.com/dileepadev)

## Contact

For any inquiries, please contact:

- **Email**: [contact@dileepa.dev](mailto:contact@dileepa.dev)
- **GitHub**: [@dileepadev](https://github.com/dileepadev)

## Acknowledgements

- [Flutter](https://flutter.dev) team for the amazing framework.
- Firebase for the robust backend infrastructure.
