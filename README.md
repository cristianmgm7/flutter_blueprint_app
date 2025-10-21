# Flutter Blueprint App

A production-ready Flutter template with Clean Architecture, flavors, and dependency injection.

## Project Structure

```
lib/
├── core/                      # Shared infrastructure
│   ├── config/                # App configuration (flavors, env)
│   ├── di/                    # Dependency injection setup
│   ├── errors/                # Error handling
│   ├── network/               # API client, interceptors
│   ├── theme/                 # App theming
│   ├── constants/             # App constants
│   ├── utils/                 # Utilities
│   ├── widgets/               # Reusable widgets
│   └── routing/               # Navigation setup
│
├── features/                  # Feature modules (Clean Architecture)
│   └── [feature_name]/
│       ├── data/              # Data sources, models, repositories
│       ├── domain/            # Entities, repository interfaces, use cases
│       └── presentation/      # UI, state management
│
├── main.dart                  # Common app entry
├── main_dev.dart              # Dev flavor entry
├── main_staging.dart          # Staging flavor entry
└── main_prod.dart             # Prod flavor entry
```

## Getting Started

### Prerequisites
- Flutter SDK >=3.27.0
- Dart SDK >=3.6.0

### Installation
```bash
flutter pub get
flutter pub run build_runner build --delete-conflicting-outputs
```

### Running the App

**Development:**
```bash
flutter run --flavor dev -t lib/main_dev.dart
```

**Staging:**
```bash
flutter run --flavor staging -t lib/main_staging.dart
```

**Production:**
```bash
flutter run --flavor prod -t lib/main_prod.dart
```

## Code Generation

Run code generation when adding new:
- Injectable services
- Freezed models
- JSON serializable classes

```bash
# One-time build
flutter pub run build_runner build --delete-conflicting-outputs

# Watch mode (recommended during development)
flutter pub run build_runner watch --delete-conflicting-outputs
```

## Testing

```bash
# Run all tests
flutter test

# Run with coverage
flutter test --coverage
```

## Linting

```bash
flutter analyze
```

## Project Configuration

- **Flavors**: Configured in `flavorizr.yaml`
- **Environment Variables**: `.env.dev`, `.env.staging`, `.env.prod`
- **Linting**: `analysis_options.yaml` (using very_good_analysis)
- **Code Generation**: `build.yaml`
