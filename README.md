Bloomwell Mobile – Smoke Tests (Flutter, Android & iOS)

This repository contains automated mobile smoke tests for the Bloomwell Flutter application (Android and iOS).

The purpose of this test suite is to validate that the most critical user flows work correctly after each deployment on staging and production-like environments.

Technology Stack

Flutter Integration Tests

Dart

Flutter Driver (integration_test)

Android Emulator / Physical Device

iOS Simulator / Physical Device

BrowserStack (optional, for cloud execution)

Test Scope (Smoke Level)
1. App Launch & Initialization

Application starts without crashes

Splash screen loads successfully

Initial API calls complete

2. Authentication / Registration Flow

User can open registration screen

Mandatory fields validation is triggered

User can register using valid test credentials

User can log in with existing account

Session is created successfully

3. Home & Navigation

Home screen loads correctly after login

Bottom navigation tabs are visible and clickable

Navigation between main sections works as expected

4. Product Listing & Search

Product list loads correctly

Search returns results

Wrapped and non-wrapped products are visible when applicable

5. Order Flow (Smoke)

Order creation can be started

Pharmacy selection is displayed

Delivery method selection is available

Pick-up / delivery options render correctly

Note: Deep order logic and payments are covered by separate test suites.

6. Order Details

Order details screen opens

Pharmacy information is displayed

“Rechnung” (invoice) link visibility is validated

Pick-up address is displayed for pick-up orders

7. Feature Flag & Platform Parity Checks

Feature availability is consistent across:

Android

iOS

Same account behaves consistently on both platforms

Platforms Covered

Android (minimum supported version)

Android 14 / 15 (latest)

iOS (latest stable version)

Tests are validated on:

Emulators / Simulators

Physical devices

BrowserStack devices (optional)

Project Structure
integration_test/
├── app_launch_test.dart
├── registration_test.dart
├── login_test.dart
├── navigation_test.dart
├── product_list_test.dart
├── order_smoke_test.dart

test/
├── helpers/
│   ├── selectors.dart
│   ├── test_data.dart
│   └── utils.dart

Prerequisites

Flutter SDK (stable channel)

Android Studio with SDK tools installed

Xcode (for iOS)

CocoaPods (for iOS)

At least one connected device or emulator

Running Tests Locally
Install dependencies
flutter pub get

Run all integration tests
flutter test integration_test

Run a single test
flutter test integration_test/registration_test.dart

Running on Android
flutter test integration_test --device-id android

Running on iOS
flutter test integration_test --device-id ios

BrowserStack Execution (Optional)

Build APK / IPA

Upload build to BrowserStack

Execute tests on selected real devices

BrowserStack is used to validate:

Multiple Android versions

Multiple iOS versions

Device-specific issues

Test Data & Accounts

Dedicated test accounts are used for automation

Test data is isolated from production users

Feature flags must be enabled for relevant test accounts

Reporting

Console output is used for local execution

CI pipelines can export logs and artifacts

BrowserStack dashboard provides device-level reports

Limitations

Payment flows are not fully automated

A-Orders may not be testable on DEV

Some scenarios require STAGE environment
