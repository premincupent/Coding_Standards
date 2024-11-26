# [Gathered by cupent](https://www.cupent.com)
### Create Date: 02-09-2024
### Last Update Date: 02-09-2024

# Flutter and Dart Coding Best Practices and Style Guide

## General Coding Practices

| Practice                                | Description                                      |
|-----------------------------------------|--------------------------------------------------|
| **Follow Effective Dart Guidelines**    | Adhere to the [Effective Dart](https://dart.dev/guides/language/effective-dart) guidelines for Dart coding standards. |
| **Use Stateless and Stateful Widgets Appropriately** | Use `StatelessWidget` for immutable widgets and `StatefulWidget` for widgets that maintain mutable state. |
| **Keep Widgets Small and Focused**      | Create small, focused widgets to improve readability and maintainability. |
| **Use Dart's Null Safety**              | Utilize Dart’s null safety features to avoid null reference errors. |
| **Use Dependency Injection**            | Utilize dependency injection for managing dependencies rather than directly instantiating them. |
| **Avoid Code Duplication**              | Reuse code through widgets, functions, and libraries to prevent duplication. |
| **Use Comments and Documentation**      | Document code using comments and DartDoc to explain complex logic and public APIs. |

## Splitting Functions and Reusability

| Practice                                | Description                                      |
|-----------------------------------------|--------------------------------------------------|
| **Refactor Large Functions**            | Break large functions into smaller, more manageable functions that each perform a single task. |
| **Create Reusable Widgets**             | Extract reusable UI components into separate widgets to avoid code duplication. |
| **Use Helper Functions**                | Create helper functions for common operations and utilities. |
| **Utilize Mixins and Extensions**       | Use mixins and extensions to add functionalities to classes in a reusable manner. |
| **Apply the DRY Principle**             | Follow the "Don't Repeat Yourself" principle to reduce redundancy in code. |

## Managing Large Widgets and Classes

| Practice                                | Description                                      |
|-----------------------------------------|--------------------------------------------------|
| **Split Large Widgets**                 | Break down large widgets into smaller, more focused widgets. |
| **Use Composition Over Inheritance**    | Prefer composition to inheritance for creating complex UI components. |
| **Encapsulate Widget Logic**            | Encapsulate widget logic into methods or separate classes to keep widgets clean. |
| **Follow SOLID Principles**             | Adhere to SOLID principles (Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation, Dependency Inversion) for better code structure. |
| **Use Providers and BLoC Pattern**      | Utilize state management solutions like Provider or BLoC for managing state effectively. |

## Naming Conventions

| Component                   | Convention                                    | Example                       |
|-----------------------------|------------------------------------------------|-------------------------------|
| **Widgets**                 | PascalCase                                     | `UserProfileWidget`, `OrderList` |
| **State Classes**           | PascalCase with `State` suffix                 | `UserProfileState`, `OrderListState` |
| **Dart Files**              | snake_case                                      | `user_profile_widget.dart`, `order_list.dart` |
| **Methods and Functions**   | camelCase                                       | `fetchUserData()`, `updateOrderStatus()` |
| **Variables**               | camelCase                                       | `userProfile`, `orderList`    |
| **Constants**               | UPPER_SNAKE_CASE                                | `API_URL`, `MAX_RETRIES`      |
| **Class Names**             | PascalCase                                      | `UserProfile`, `OrderManager` |
| **Enum Names**              | PascalCase                                      | `OrderStatus`, `UserRole`     |

## Code Structure

| Structure                     | Description                                      |
|-------------------------------|--------------------------------------------------|
| **Widgets**                   | Place widgets in `lib/widgets`. Use descriptive names and group by functionality. |
| **Models**                    | Place models in `lib/models`. Define data structures and business logic here. |
| **Services**                  | Place service classes in `lib/services`. Define methods for interacting with APIs or data sources. |
| **Providers**                 | Place state management providers in `lib/providers`. Define and manage app state. |
| **Screens**                   | Place screens in `lib/screens`. Each screen should be a separate file or directory. |
| **Utils**                     | Place utility functions and helpers in `lib/utils`. Include commonly used functions and constants. |

## Database and Networking

| Practice                                | Description                                      |
|-----------------------------------------|--------------------------------------------------|
| **Use Packages for HTTP Requests**      | Use packages like `http` or `dio` for making network requests. |
| **Handle Errors Gracefully**            | Handle network errors and data parsing errors effectively to provide user feedback. |
| **Use SQLite for Local Storage**        | Use packages like `sqflite` for local database storage. |
| **Avoid Hardcoding URLs**               | Store URLs and API endpoints in a configuration file or environment variables. |

## Error Handling and Validation

| Practice                                | Description                                      |
|-----------------------------------------|--------------------------------------------------|
| **Use Try-Catch for Error Handling**    | Use `try-catch` blocks to handle exceptions and provide error feedback to users. |
| **Validate User Input**                 | Validate user input before processing to ensure data integrity. |
| **Use Flutter's Built-In Validation**   | Utilize Flutter's built-in validation widgets and packages for form validation. |

## Testing

| Practice                                | Description                                      |
|-----------------------------------------|--------------------------------------------------|
| **Write Unit Tests**                    | Write unit tests for functions and methods using the `test` package. |
| **Write Widget Tests**                  | Write widget tests to ensure UI components render correctly using the `flutter_test` package. |
| **Write Integration Tests**             | Write integration tests to test complete workflows and interactions using the `integration_test` package. |

## Security Practices

| Practice                                | Description                                      |
|-----------------------------------------|--------------------------------------------------|
| **Sanitize User Input**                 | Always sanitize and validate user input to prevent security vulnerabilities. |
| **Use Secure Storage for Sensitive Data** | Use secure storage solutions for sensitive information such as tokens or user credentials. |
| **Use HTTPS for Network Requests**      | Ensure all network requests use HTTPS to protect data in transit. |

## Performance

| Practice                                | Description                                      |
|-----------------------------------------|--------------------------------------------------|
| **Optimize Widgets**                   | Optimize widget rebuilds by using `const` constructors and avoiding unnecessary re-renders. |
| **Use Asynchronous Programming**        | Use `async` and `await` to handle asynchronous operations efficiently. |
| **Profile and Analyze Performance**     | Use Flutter's performance tools to profile and analyze application performance. |

## Documentation

| Practice                                | Description                                      |
|-----------------------------------------|--------------------------------------------------|
| **Document Public APIs**                | Document public APIs and widget usage with DartDoc comments. |
| **Maintain Code Comments**              | Keep code comments relevant and up-to-date. Avoid redundant comments. |
| **Write Clear README Files**            | Provide clear and comprehensive README files for project setup and usage. |

## Tools and VSCode Plugins

| Tool/Plugin                        | Description                                      |
|------------------------------------|--------------------------------------------------|
| **Flutter**                        | The Flutter SDK for building cross-platform applications. |
| **Dart**                           | The Dart SDK for the Dart programming language. |
| **Flutter DevTools**               | Tools for debugging and profiling Flutter applications. |
| **Dart Analysis**                  | Dart's built-in analysis tool for linting and code quality checks. |
| **VSCode Flutter Extension**       | Provides Flutter support, including debugging and widget editing in VSCode. |
| **VSCode Dart Extension**          | Adds Dart language support, including syntax highlighting and code completion. |
| **Pub Dev**                        | The package repository for Dart and Flutter packages. |
| **Code Formatter**                 | Automatically formats Dart code according to Dart's style guidelines. |

## Example File Structure

```plaintext
lib/
  ├── models/
  │   └── user.dart
  ├── services/
  │   └── api_service.dart
  ├── providers/
  │   └── user_provider.dart
  ├── screens/
  │   ├── home_screen.dart
  │   └── profile_screen.dart
  ├── widgets/
  │   └── user_profile_widget.dart
  └── utils/
      └── constants.dart
```

# Flutter: Manual State Management and Coding Standards

This guide outlines the best practices for **manual state management** in Flutter and how to structure your code and files for readability and maintainability.

---

## Manual State Management: Standards and Best Practices

Managing state in Flutter manually often involves the use of `StatefulWidget`. Here’s how to do it effectively:

### 1. Choose the Right State Management Approach
- **Local State:** Use for ephemeral, widget-specific state.
- **Global State:** For shared data, consider `InheritedWidget`, `ChangeNotifier`, or advanced state management solutions like `Provider` or `Riverpod`.

### 2. Keep the Widget Tree Clean
- Break large widgets into smaller, reusable components to maintain readability.

### 3. Use `setState` Judiciously
- Avoid overusing `setState` in large widgets; limit it to small, targeted updates to the UI.

### 4. Leverage Keys for Widgets
- Use `Key` (e.g., `ValueKey`, `UniqueKey`) to preserve widget state during rebuilds.

---

### 5. Example: Local State Management

```dart
class CounterWidget extends StatefulWidget {
  @override
  _CounterWidgetState createState() => _CounterWidgetState();
}

class _CounterWidgetState extends State<CounterWidget> {
  int _counter = 0;

  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Column(
      mainAxisAlignment: MainAxisAlignment.center,
      children: [
        Text('Counter: $_counter'),
        ElevatedButton(
          onPressed: _incrementCounter,
          child: Text('Increment'),
        ),
      ],
    );
  }
}
```

---

## Coding Structure and File Organization

To maintain readability and scalability in your Flutter project, follow these standards for organizing code within a single file and across the project.

---

### File Structure: Standards and Best Practices

#### 1. Order of Code in a File
- **Imports:** Organize logically:
  1. Dart SDK imports
  2. Flutter framework imports
  3. Third-party package imports
  4. Local project imports

```dart
import 'dart:async';

import 'package:flutter/material.dart';

import 'widgets/custom_button.dart';
import 'models/user_model.dart';
```

- **Constants and Enumerations:**
  Define global constants and enums after imports.

```dart
const double kDefaultPadding = 16.0;

enum UserStatus { active, inactive, banned }
```

- **Widget Definitions:**  
  The top-level widget comes first, followed by helper widgets.

- **Event Handlers and Logic:**  
  Place below widget definitions to keep the UI code clean.

#### 2. Organizing the `build()` Method
Break down complex layouts into helper methods or widgets:

```dart
@override
Widget build(BuildContext context) {
  return Scaffold(
    appBar: AppBar(title: Text('Dashboard')),
    body: _buildBody(),
  );
}

Widget _buildBody() {
  return Column(
    children: [
      _buildHeader(),
      _buildList(),
    ],
  );
}

Widget _buildHeader() {
  return Text('Header');
}

Widget _buildList() {
  return ListView.builder(
    itemCount: items.length,
    itemBuilder: (context, index) {
      return ListTile(title: Text(items[index]));
    },
  );
}
```

---

### 3. Modularizing Large Files
Split large widgets into separate files to improve maintainability.

#### Project File Structure Example
Organize files by feature and common components:

```
lib/
├── features/
│   ├── auth/
│   │   ├── login_page.dart
│   │   ├── register_page.dart
│   │   ├── auth_service.dart
│   └── dashboard/
│       ├── dashboard_page.dart
│       ├── dashboard_controller.dart
│       ├── widgets/
│           ├── dashboard_header.dart
│           ├── dashboard_card.dart
├── common/
│   ├── widgets/
│   │   ├── custom_button.dart
│   │   ├── input_field.dart
│   ├── models/
│       ├── user_model.dart
│       ├── settings_model.dart
```

---

### 4. Best Practices for Widget Display
- Use **`ListView.builder`** for large lists to optimize memory usage.
- Mark reusable widgets with `const` where possible to prevent unnecessary rebuilds.
- Use responsive layouts with `Expanded`, `Flexible`, and `MediaQuery`.

---

## Complete Code Example

```dart
import 'package:flutter/material.dart';

const double kDefaultPadding = 16.0;

class CounterApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Counter App',
      home: CounterWidget(),
    );
  }
}

class CounterWidget extends StatefulWidget {
  @override
  _CounterWidgetState createState() => _CounterWidgetState();
}

class _CounterWidgetState extends State<CounterWidget> {
  int _counter = 0;

  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Counter App')),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Text('Counter: $_counter', style: TextStyle(fontSize: 24)),
            SizedBox(height: kDefaultPadding),
            ElevatedButton(
              onPressed: _incrementCounter,
              child: Text('Increment'),
            ),
          ],
        ),
      ),
    );
  }
}

void main() => runApp(CounterApp());
```

---

## Key Takeaways

1. **Use Local State Only When Necessary:**  
   Opt for global state for shared data.
   
2. **Keep Code Clean and Modular:**  
   Split large widgets and logic into smaller, reusable files and methods.

3. **Follow a Consistent Structure:**  
   Order imports, constants, widgets, and logic consistently.

4. **Optimize Lists:**  
   Use `ListView.builder` for large datasets and leverage `const` widgets where possible.

By following these best practices, you’ll create clean, maintainable, and efficient Flutter applications.


# API Usage in Flutter: Standards and Best Practices

This guide provides best practices and standards for integrating APIs in a Flutter application to ensure efficient, maintainable, and scalable code.

---

## **1. Use a Dedicated Service Layer**
- Create a dedicated file or directory for API-related logic.
- Keep API calls separate from UI code to ensure better modularity and testing.

**Example: `api_service.dart`**
```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

class ApiService {
  final String baseUrl;

  ApiService({required this.baseUrl});

  Future<dynamic> get(String endpoint) async {
    final response = await http.get(Uri.parse('$baseUrl$endpoint'));
    if (response.statusCode == 200) {
      return json.decode(response.body);
    } else {
      throw Exception('Failed to load data');
    }
  }

  Future<dynamic> post(String endpoint, Map<String, dynamic> data) async {
    final response = await http.post(
      Uri.parse('$baseUrl$endpoint'),
      headers: {'Content-Type': 'application/json'},
      body: json.encode(data),
    );
    if (response.statusCode == 200 || response.statusCode == 201) {
      return json.decode(response.body);
    } else {
      throw Exception('Failed to post data');
    }
  }
}
```

---

## **2. Organize API Endpoints**
- Store endpoints in a constants file for better management and reusability.

**Example: `api_constants.dart`**
```dart
class ApiConstants {
  static const String baseUrl = 'https://api.example.com/';
  static const String login = 'auth/login';
  static const String fetchUsers = 'users';
}
```

---

## **3. Use Dependency Injection for APIs**
- Use dependency injection to make API services easier to test and mock.

**Example: Using Provider**
```dart
import 'package:provider/provider.dart';

void main() {
  runApp(
    MultiProvider(
      providers: [
        Provider<ApiService>(create: (_) => ApiService(baseUrl: ApiConstants.baseUrl)),
      ],
      child: MyApp(),
    ),
  );
}
```

---

## **4. Handle Errors Gracefully**
- Use try-catch blocks and provide meaningful error messages.
- Create a custom error handler for centralized error management.

**Example: Error Handling**
```dart
try {
  final data = await apiService.get(ApiConstants.fetchUsers);
  print(data);
} catch (e) {
  print('Error: $e');
}
```

---

## **5. Use Models for JSON Parsing**
- Convert API responses to Dart objects using model classes.

**Example: User Model**
```dart
class User {
  final int id;
  final String name;

  User({required this.id, required this.name});

  factory User.fromJson(Map<String, dynamic> json) {
    return User(
      id: json['id'],
      name: json['name'],
    );
  }

  Map<String, dynamic> toJson() {
    return {
      'id': id,
      'name': name,
    };
  }
}
```

---

## **6. Utilize Asynchronous Programming**
- Use `FutureBuilder` or state management libraries like `Provider` or `Riverpod` to handle asynchronous data fetching.

**Example: Using `FutureBuilder`**
```dart
Future<List<User>> fetchUsers() async {
  final data = await apiService.get(ApiConstants.fetchUsers);
  return (data as List).map((json) => User.fromJson(json)).toList();
}

@override
Widget build(BuildContext context) {
  return FutureBuilder<List<User>>(
    future: fetchUsers(),
    builder: (context, snapshot) {
      if (snapshot.connectionState == ConnectionState.waiting) {
        return CircularProgressIndicator();
      } else if (snapshot.hasError) {
        return Text('Error: ${snapshot.error}');
      } else {
        final users = snapshot.data!;
        return ListView.builder(
          itemCount: users.length,
          itemBuilder: (context, index) {
            return ListTile(title: Text(users[index].name));
          },
        );
      }
    },
  );
}
```

---

## **7. Secure API Calls**
- Never hardcode API keys or sensitive data in the app.
- Use environment variables or secure storage.

**Example: Environment Variables**
```yaml
# Add dotenv to pubspec.yaml
dependencies:
  flutter_dotenv: ^5.0.2
```

**Load Environment Variables**
```dart
import 'package:flutter_dotenv/flutter_dotenv.dart';

void main() async {
  await dotenv.load();
  runApp(MyApp());
}

final apiKey = dotenv.env['API_KEY'];
```

---

## **8. Cache API Responses**
- Use a caching library like `shared_preferences` or `hive` to cache API responses for better performance and offline support.

**Example: Caching with `shared_preferences`**
```dart
import 'package:shared_preferences/shared_preferences.dart';

Future<void> cacheResponse(String key, String data) async {
  final prefs = await SharedPreferences.getInstance();
  await prefs.setString(key, data);
}

Future<String?> getCachedResponse(String key) async {
  final prefs = await SharedPreferences.getInstance();
  return prefs.getString(key);
}
```

---

## **9. Testing APIs**
- Write unit tests for API services using `mockito` or `http_mock_adapter`.

**Example: Testing with `mockito`**
```dart
import 'package:flutter_test/flutter_test.dart';
import 'package:mockito/mockito.dart';
import 'package:your_app/api_service.dart';

class MockHttpClient extends Mock implements ApiService {}

void main() {
  late MockHttpClient mockHttpClient;

  setUp(() {
    mockHttpClient = MockHttpClient();
  });

  test('fetch users returns a list of users', () async {
    when(mockHttpClient.get('users')).thenAnswer(
      (_) async => [{'id': 1, 'name': 'John Doe'}],
    );

    final data = await mockHttpClient.get('users');
    expect(data, isA<List<dynamic>>());
    expect(data[0]['name'], 'John Doe');
  });
}
```

---

## **10. Key Takeaways**
- Separate API logic from UI for better modularity.
- Use constants for API endpoints.
- Handle errors and secure sensitive data.
- Cache responses for offline support.
- Write unit tests to ensure reliability.

By following these best practices, you can create a robust and maintainable API integration in your Flutter application.
