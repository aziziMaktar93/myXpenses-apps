# MyXpenses

MyXpenses is a personal expense-tracking app built with Flutter. It runs on Android, iOS, and web, and stores all data locally on the device using SQLite (via `sqflite`).

## Features

- **Dashboard** — quick overview of your balance and recent transactions, with a shortcut to add a new one.
- **Add / Edit / Delete Transactions** — record income or expenses with a title, amount, category, date, payment method, wallet, and an optional note. Deleting a transaction shows an Undo action.
- **Receipt Photos** — attach a photo of a receipt to a transaction using the camera or photo library.
- **History** — full list of transactions with search-by-title, tap-to-edit, and swipe-to-delete.
- **Budget** — set a monthly spending limit per category and track how much has been spent against it. A local notification is triggered when a category goes over budget.
- **Report** — visual breakdown of spending by category and income vs. expense over a selected period, powered by `fl_chart`.
- **Custom Categories** — add your own categories in addition to the built-in ones (Food, Transport, Shopping, Bills, Family, Health, Salary, Allowance, Freelance, Bonus, Others).
- **CSV Export** — export all transactions to a CSV file saved to the device's Downloads folder.
- **App Lock (PIN)** — optionally protect the app with a PIN code, set and managed from the Dashboard.

## Tech Stack

- [Flutter](https://flutter.dev/) / Dart
- `sqflite` + `sqflite_common_ffi_web` — local SQLite storage on mobile and web
- `fl_chart` — charts for the Report screen
- `image_picker` — receipt photo capture
- `flutter_local_notifications` — budget-exceeded alerts
- `shared_preferences` + `crypto` — PIN storage/verification
- `file_saver` — CSV export

## Project Structure

```
lib/
├── main.dart                    # App entry point, navigation, app lock
├── db/app_database.dart         # SQLite schema and queries
├── models/transaction_item.dart # Transaction model
├── screens/
│   ├── dashboard_screen.dart
│   ├── transaction_screen.dart  # Add/edit transaction form
│   ├── history_screen.dart
│   ├── budget_screen.dart
│   ├── report_screen.dart
│   └── pin_lock_screen.dart
└── utils/
    ├── app_lock.dart
    ├── budget_notifications.dart
    └── csv_export.dart
```

## Getting Started

1. Install [Flutter](https://docs.flutter.dev/get-started/install) (SDK `^3.12.0-76.0.dev` or compatible).
2. Install dependencies:
   ```
   flutter pub get
   ```
3. Run the app:
   ```
   flutter run
   ```

## Building

```
flutter build apk      # Android
flutter build ios      # iOS
flutter build web       # Web
```
