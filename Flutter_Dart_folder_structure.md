# [Gathered by cupent](https://www.cupent.com)
### Create Date: 28-03-2025
### Last Update Date: 28-03-2025

# 📦 Flutter Project Folder Structure Guide

This guide provides a detailed, scalable, and maintainable folder structure for a large-scale, API-driven Flutter application following Clean Architecture principles.

---

## 🔰 Root Structure

```
lib/
├── core/
├── features/
├── common/
├── config/
├── main.dart
```

- `core/`: App-wide utilities and services.
- `features/`: Modular structure based on app features.
- `common/`: Shared UI components and utilities.
- `config/`: Configuration files (routing, DI, environment, localization).
- `main.dart`: App entry point.

---

## 🧱 `core/` – Global Foundations

```
core/
├── constants/
│   ├── colors.dart
│   ├── strings.dart
│   ├── sizes.dart
│   └── api_endpoints.dart
├── services/
│   ├── network_service.dart
│   ├── connectivity_service.dart
│   └── logger_service.dart
├── error/
│   ├── failure.dart
│   └── exceptions.dart
├── utils/
│   ├── validators.dart
│   ├── date_formatter.dart
│   └── helpers.dart
├── theme/
│   ├── app_theme.dart
│   └── theme_data.dart
```

---

## 📦 `features/` – Modular Business Logic

Each feature contains:
- `data/`: Data source implementations and models.
- `domain/`: Business logic (entities, use cases, repositories).
- `presentation/`: UI components, pages, state management.

```
features/
├── auth/
│   ├── data/
│   │   ├── models/
│   │   ├── datasources/
│   │   └── repositories/
│   ├── domain/
│   │   ├── entities/
│   │   ├── repositories/
│   │   └── usecases/
│   ├── presentation/
│   │   ├── pages/
│   │   ├── widgets/
│   │   └── bloc/ or provider/
│   └── auth_module.dart
├── home/
│   └── ...
```

---

## 🧰 `common/` – Reusable UI and Extensions

```
common/
├── widgets/
│   ├── custom_button.dart
│   ├── loading_indicator.dart
│   └── custom_dialog.dart
├── extensions/
│   ├── string_extensions.dart
│   ├── context_extensions.dart
│   └── date_extensions.dart
├── enums/
├── mixins/
├── types/
└── animations/
```

---

## ⚙️ `config/` – App Configurations

```
config/
├── di/
│   └── service_locator.dart
├── env/
│   ├── dev.dart
│   ├── prod.dart
│   └── staging.dart
├── routes/
│   ├── app_routes.dart
│   └── route_generator.dart
├── localization/
│   ├── en.json
│   ├── ar.json
│   └── localization_service.dart
```

---

## 🧪 `test/` – Unit and Widget Testing

```
test/
├── features/
│   ├── auth/
│   │   ├── data/
│   │   ├── domain/
│   │   └── presentation/
├── core/
├── common/
└── mock/
```

---

## 🧠 State Management

- Support for `bloc`, `provider`, `riverpod`, or others.
- State management is implemented within `presentation/` of each feature.

```
presentation/
├── bloc/
│   ├── event.dart
│   ├── state.dart
│   └── bloc.dart
```

---

## 🔌 Networking (API Layer)

- API calls should reside in `data/datasources/`.
- Use models for serialization and repositories to abstract API logic.

---

## 🧩 Dependency Injection

Using `get_it` or `riverpod`, register services inside:
```
config/di/service_locator.dart
```

```dart
final sl = GetIt.instance;

void init() {
  sl.registerLazySingleton(() => NetworkService());
  sl.registerFactory(() => AuthBloc(sl()));
}
```

---

## 🚀 Entry Point – `main.dart`

```dart
void main() async {
  WidgetsFlutterBinding.ensureInitialized();
  await init(); // Initialize DI
  runApp(MyApp());
}
```

---

## 💡 Best Practices

- Use **clean architecture** (Data > Domain > Presentation).
- Group code by **features** not type (feature-first approach).
- Keep widgets **reusable and testable**.
- Avoid **business logic** inside widgets.
- Separate **UI, logic, and data access**.

---

## 📘 Resources

- [Flutter Clean Architecture](https://resocoder.com/clean-architecture)
- [GetIt](https://pub.dev/packages/get_it)
- [Bloc](https://bloclibrary.dev/)

---

Happy Coding! 🚀
