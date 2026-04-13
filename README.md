# CITE IMS — College of Information Technology Education Inventory Management System

## Table of Contents
- [Introduction](#introduction)
- [Technologies](#technologies)
- [Features](#features)
- [Project structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Build & Run](#build--run)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Introduction

CITE IMS (College of Information Technology Education Inventory Management System) is an Android application for managing inventory in an educational context. It provides core inventory functionality (items, stock levels, basic reporting and user/admin workflows) implemented as an Android app using Java and Gradle.

## Technologies

- Android (native)
- Java (Android app code)
- Gradle (build system)
- Project uses Gradle Kotlin DSL (.kts) for top-level and module-level build scripts

## Features

- Item listing and inventory tracking
- Local storage via a SQLite helper
- Simple user login / registration flow
- Admin and user activities/screens
- Basic encryption utilities for local data handling
- Adapter for displaying inventory items in lists

## Project structure (high-level)

- build.gradle.kts, settings.gradle.kts, gradle.properties — top-level Gradle configuration
- app/ — Android application module
  - app/src/main/AndroidManifest.xml
  - app/src/main/java/activities/ — UI activities
    - AdminActivity.java
    - LoginActivity.java
    - MainActivity.java
    - RegisterActivity.java
    - SettingsActivity.java
    - SplashActivity.java
    - UserActivity.java
  - app/src/main/java/com/example/cite_ims/
    - DBHelper.java
    - EncryptionUtils.java
    - InventoryAdapter.java
    - InventoryItem.java
  - app/proguard-rules.pro
  - app/ic_launcher-playstore.png

This README reflects the app-first, Android-native nature of the repository.

## Prerequisites

- Java JDK 11 or newer
- Android Studio (recommended) with Android SDK installed
- Android device or emulator
- Git

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/ProfessorArthur/CITE_IMS.git
   cd CITE_IMS
   ```

2. Open the project in Android Studio:
   - Start Android Studio and choose "Open", then select the cloned project directory.
   - Let Android Studio sync and download required Gradle dependencies.

Alternatively, from the command line you can build the app with Gradle (Linux/macOS/WSL):
```bash
./gradlew assembleDebug
```

## Build & Run

- To install on a connected device/emulator using Gradle:
  1. Build the debug APK:
     ```bash
     ./gradlew :app:assembleDebug
     ```
  2. Install the debug APK (replace path with the actual output if different):
     ```bash
     adb install -r app/build/outputs/apk/debug/app-debug.apk
     ```
- Or run the app directly from Android Studio (recommended). Select a device/emulator and click Run.

## Usage

- Launch the app on your device/emulator.
- The app includes login and registration flows (see LoginActivity and RegisterActivity).
- After login, user or admin flows are available:
  - AdminActivity: administrative features for inventory management.
  - UserActivity / MainActivity: browse and interact with inventory items.
- Inventory items are represented by InventoryItem and shown via InventoryAdapter. Data is managed locally via DBHelper. Encryption utilities are in EncryptionUtils.

## Contributing

Contributions are welcome. Please:
- Fork the repository
- Create a feature branch
- Open a pull request describing your changes

If you plan significant changes (new features, architecture changes), open an issue first so the design can be discussed.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
