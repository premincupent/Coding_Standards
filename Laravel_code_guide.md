# [Gathered by cupent](https://www.cupent.com)
Create Date: 02-09-2024
Last Update Date: 02-09-2024
# Laravel Coding Best Practices and Style Guide

## General Coding Practices

| Practice                                | Description                                      |
|-----------------------------------------|--------------------------------------------------|
| **Use PSR Standards**                   | Adhere to PSR-1, PSR-2, and PSR-4 standards for coding style and autoloading. |
| **Keep Methods and Functions Short**    | Methods and functions should be concise and perform a single task. |
| **Avoid Magic Methods**                 | Prefer explicit methods over magic methods for clarity and maintainability. |
| **Use Dependency Injection**            | Inject dependencies through constructors or methods rather than using facades. |
| **Use Type Hinting**                    | Use type hinting for method parameters and return types to ensure type safety. |
| **Follow Single Responsibility Principle** | Each class or method should have a single responsibility or purpose. |
| **Comment and Document Code**           | Use comments and PHPDoc to explain complex logic and document public methods. |

## Splitting Functions and Reusability

| Practice                                | Description                                      |
|-----------------------------------------|--------------------------------------------------|
| **Refactor Large Functions**            | Break large functions into smaller, more manageable functions. Each function should perform a single, well-defined task. |
| **Create Reusable Functions**            | Extract commonly used logic into reusable functions or methods to avoid code duplication. |
| **Use Helper Classes**                  | Utilize helper classes for utility functions that are used across different parts of the application. |
| **Leverage Traits**                     | Use traits to share methods across multiple classes without inheritance. |
| **Apply the DRY Principle**              | Follow the "Don't Repeat Yourself" principle to reduce redundancy in code. Avoid duplicating code across different methods or classes. |

## Managing Large Classes and Functions

| Practice                                | Description                                      |
|-----------------------------------------|--------------------------------------------------|
| **Split Large Classes**                 | Break down large classes into smaller, focused classes that handle specific responsibilities. |
| **Use Service Classes**                 | Organize business logic into service classes to keep controllers and models lean. |
| **Apply the Law of Demeter**            | Ensure that a class only interacts with its immediate dependencies, not with dependencies of dependencies. |
| **Encapsulate Code**                    | Encapsulate related functionalities into separate classes or methods to improve maintainability and readability. |
| **Follow SOLID Principles**             | Adhere to SOLID principles (Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation, Dependency Inversion) to create scalable and maintainable code. |
| **Use Interfaces and Abstract Classes** | Define interfaces or abstract classes to outline the structure of implementations, which promotes flexibility and decoupling. |

## Naming Conventions

| Component                   | Convention                                    | Example                       |
|-----------------------------|------------------------------------------------|-------------------------------|
| **Model**                   | Singular, PascalCase                          | `User`, `OrderDetail`         |
| **Table**                   | Plural, snake_case                             | `users`, `order_details`      |
| **Migration**              | `create_<table>_table`, `add_<column>_to_<table>_table` | `create_users_table`, `add_age_to_users_table` |
| **Controller**             | PascalCase with `Controller` suffix            | `UserController`, `OrderController` |
| **Route**                  | kebab-case                                    | `user-profile`, `order-history` |
| **View**                   | snake_case                                    | `user_profile.blade.php`, `order_history.blade.php` |
| **Configuration File**     | snake_case                                    | `database.php`, `app.php`     |
| **Environment Variables**  | UPPER_CASE                                     | `DB_CONNECTION`, `APP_ENV`    |
| **Test Class**             | PascalCase with `Test` suffix                  | `UserTest`, `OrderTest`       |
| **Event**                  | PascalCase                                    | `UserRegistered`, `OrderPlaced` |
| **Job**                    | PascalCase with `Job` suffix                   | `SendEmailJob`, `ProcessOrderJob` |
| **Middleware**             | PascalCase with `Middleware` suffix            | `AuthenticateMiddleware`, `CheckRoleMiddleware` |

## Code Structure

| Structure                     | Description                                      |
|-------------------------------|--------------------------------------------------|
| **Controllers**               | Place controllers in `app/Http/Controllers`. Use resource controllers for RESTful operations. |
| **Models**                    | Place models in `app/Models`. Follow the naming convention and use Eloquent ORM features. |
| **Migrations**                | Place migrations in `database/migrations`. Name migrations descriptively and use timestamps. |
| **Seeds**                     | Place seeders in `database/seeders`. Name seeders according to the data they seed. |
| **Factories**                 | Place factories in `database/factories`. Use for generating test data and follow the naming convention. |
| **Requests**                  | Place form request classes in `app/Http/Requests`. Name requests based on their purpose. |
| **Policies**                  | Place policies in `app/Policies`. Name policies based on the model they are associated with. |
| **Providers**                 | Place service providers in `app/Providers`. Register bindings and configurations here. |
| **Routes**                    | Place route files in `routes/`. Keep route files organized by type, e.g., `web.php`, `api.php`. |

## Database Practices

| Practice                                | Description                                      |
|-----------------------------------------|--------------------------------------------------|
| **Use Migrations**                     | Always use migrations to modify the database schema. |
| **Use Seeders for Test Data**           | Use seeders to populate the database with test data. |
| **Avoid Direct SQL Queries**            | Use Eloquent ORM or query builder instead of raw SQL queries for better security and readability. |
| **Index Columns**                      | Add indexes to columns that are frequently searched or used in JOINs for performance. |

## Error Handling and Validation

| Practice                                | Description                                      |
|-----------------------------------------|--------------------------------------------------|
| **Use Custom Validation Rules**         | Create custom validation rules for complex validation logic. |
| **Handle Exceptions Gracefully**        | Use exception handling to provide user-friendly error messages and log exceptions. |
| **Use Form Requests for Validation**     | Use form request classes for validation logic to keep controllers clean. |

## Testing

| Practice                                | Description                                      |
|-----------------------------------------|--------------------------------------------------|
| **Write Unit Tests**                    | Write unit tests for individual components to ensure they work as expected. |
| **Write Feature Tests**                 | Write feature tests to test application functionality and user flows. |
| **Use Test Factories**                  | Use model factories to generate test data for your tests. |

## Security Practices

| Practice                                | Description                                      |
|-----------------------------------------|--------------------------------------------------|
| **Sanitize User Input**                 | Always sanitize and validate user input to prevent security vulnerabilities. |
| **Use Laravel’s Built-in Security Features** | Leverage Laravel's built-in features such as CSRF protection and authentication. |
| **Encrypt Sensitive Data**              | Use encryption for sensitive data stored in the database. |

## Performance

| Practice                                | Description                                      |
|-----------------------------------------|--------------------------------------------------|
| **Cache Frequently Accessed Data**      | Use caching to store frequently accessed data and reduce database queries. |
| **Optimize Queries**                   | Optimize database queries to reduce execution time and load. |
| **Use Queues for Time-Consuming Tasks** | Offload time-consuming tasks to queues to improve application responsiveness. |

## Documentation

| Practice                                | Description                                      |
|-----------------------------------------|--------------------------------------------------|
| **Document Public APIs**                | Document public APIs using tools like Swagger or Postman. |
| **Maintain Code Comments**              | Keep code comments up-to-date and relevant. Avoid redundant comments. |
| **Write Clear README Files**            | Provide clear and comprehensive README files for project setup and usage. |

## Tools and VSCode Plugins

| Tool/Plugin                        | Description                                      |
|------------------------------------|--------------------------------------------------|
| **Laravel Debugbar**               | A package that provides debugging information for Laravel applications. |
| **Laravel Telescope**              | An advanced debugging assistant that provides insights into your application's request lifecycle. |
| **PHPStorm**                       | A powerful IDE with comprehensive Laravel support, including code assistance and debugging. |
| **Laravel IDE Helper**             | Generates helper files to improve IDE code completion for Laravel projects. |
| **Composer**                       | Dependency manager for PHP, used to install and manage Laravel packages. |
| **PHPUnit**                        | Testing framework used for unit and feature testing in Laravel. |
| **Xdebug**                         | A debugger for PHP that provides advanced debugging capabilities. |
| **Prettier**                       | Code formatter to ensure consistent code style across your project. |
| **ESLint**                         | Linter for JavaScript and TypeScript to enforce code quality standards. |
| **Laravel Blade Snippets**         | VSCode extension that provides Blade syntax highlighting and snippets. |
| **Laravel Artisan**                | VSCode extension that adds Artisan commands to the command palette for easy access. |
| **PHP Intelephense**               | PHP language server that provides code completion, linting, and more for VSCode. |
| **GitLens**                        | Git extension for VSCode that enhances Git capabilities and visualization. |
| **Live Share**                     | VSCode extension for real-time collaborative coding sessions. |

