# [Gathered by cupent](https://www.cupent.com)
Create Date: 02-09-2024
Last Update Date: 02-09-2024

# Laravel Quick Reference

## Artisan Commands

| Command                                   | Description                                      |
|-------------------------------------------|--------------------------------------------------|
| `php artisan --help`                     | Show help                                        |
| `php artisan --version`                  | Show version                                     |
| `php artisan --quiet`                    | Quiet mode                                       |
| `php artisan --verbose`                  | Verbose mode                                     |
| `php artisan --env`                      | Set environment                                  |
| `php artisan --no-interaction`           | No interaction                                   |
| `php artisan --ansi`                     | Force ANSI output                                |
| `php artisan --no-ansi`                  | Disable ANSI output                              |
| `php artisan clear-compiled`             | Clear compiled files                             |
| `php artisan dump-autoload`               | Regenerate autoload files                        |
| `php artisan env`                        | Display the current environment                 |
| `php artisan help`                       | Display help for a specific command              |
| `php artisan list`                       | List all available commands                      |
| `php artisan migrate`                    | Run migrations                                   |
| `php artisan optimize`                   | Optimize framework                               |
| `php artisan routes`                     | List all routes                                  |
| `php artisan serve`                      | Start local development server                   |
| `php artisan tinker`                     | Start REPL (interactive shell)                   |
| `php artisan up`                         | Bring the application out of maintenance mode    |
| `php artisan down`                       | Put the application into maintenance mode        |
| `php artisan cache:clear`                | Clear the application cache                      |
| `php artisan key:generate`               | Generate application key                         |
| `php artisan make:model ModelName`       | Generate a new model                             |
| `php artisan make:controller ControllerName` | Generate a new controller                      |
| `php artisan make:view view_name`        | Generate a new view                              |
| `php artisan make:seeder SeederName`     | Generate a new seeder                            |
| `php artisan make:migration migration_name` | Generate a new migration                        |
| `php artisan make:resource ResourceName` | Generate a resource (model, views, controller)  |
| `php artisan generate:model`             | Generate model                                   |
| `php artisan generate:controller`        | Generate controller                              |
| `php artisan generate:view`              | Generate view                                    |
| `php artisan generate:seed`              | Generate seeder                                  |
| `php artisan generate:migration`         | Generate migration                               |
| `php artisan generate:resource`          | Generate model, views, controller, migration, seeder |

## Composer Commands

| Command                                   | Description                                      |
|-------------------------------------------|--------------------------------------------------|
| `composer create-project laravel/laravel folder_name` | Create a new Laravel project                  |
| `composer install`                       | Install dependencies                             |
| `composer update`                        | Update dependencies                              |
| `composer dump-autoload`                  | Regenerate autoload files                        |
| `composer self-update`                   | Update Composer itself                          |
| `composer require package/name`          | Add a new package                                |
| `composer remove package/name`           | Remove a package                                 |
| `composer show`                          | Show installed packages and their versions      |

## Routing

| Command                                  | Description                                      |
|------------------------------------------|--------------------------------------------------|
| `Route::get('foo', function() {})`       | Define a GET route                               |
| `Route::post('foo', function() {})`      | Define a POST route                              |
| `Route::put('foo', function() {})`       | Define a PUT route                               |
| `Route::delete('foo', function() {})`    | Define a DELETE route                            |
| `Route::any('foo', function() {})`       | Define a route for any HTTP verb                 |
| `Route::match(['get', 'post'], 'foo', function() {})` | Define a route for multiple HTTP verbs |
| `Route::redirect('foo', 'bar')`          | Redirect a route                                |
| `Route::view('foo', 'view')`             | Return a view response                           |
| `Route::get('foo/{bar}', function($bar) {})` | Define route with required parameter            |
| `Route::get('foo/{bar?}', function($bar = 'bar') {})` | Define route with optional parameter            |
| `Route::group(['prefix' => 'foo'], function() {})` | Prefix routes with 'foo'                       |
| `Route::group(['domain' => '{sub}.example.com'], function() {})` | Define routes for sub-domain |

## URL Helpers

| Command                                  | Description                                      |
|------------------------------------------|--------------------------------------------------|
| `URL::full()`                           | Generate full URL                                |
| `URL::current()`                        | Generate current URL                             |
| `URL::previous()`                       | Generate previous URL                            |
| `URL::to('foo/bar', $parameters, $secure)` | Generate URL to route                           |
| `URL::secure('foo/bar', $parameters)`   | Generate secure URL                              |
| `URL::action('FooController@method', $parameters, $absolute)` | Generate URL to action                   |
| `URL::route('foo', $parameters, $absolute)` | Generate URL to named route                     |
| `URL::asset('css/foo.css', $secure)`    | Generate URL to asset file                       |
| `URL::secureAsset('css/foo.css')`       | Generate secure URL to asset file                |
| `URL::isValidUrl('http://example.com')` | Validate a URL                                  |

## Eloquent ORM

| Command                                  | Description                                      |
|------------------------------------------|--------------------------------------------------|
| `Model::create(['key' => 'value'])`      | Create a new model instance                     |
| `Model::destroy(1)`                     | Delete a model by primary key                    |
| `Model::all()`                           | Retrieve all models                              |
| `Model::find(1)`                         | Find a model by primary key                      |
| `Model::findOrFail(1)`                   | Find model or throw exception if not found       |
| `Model::where('foo', 'bar')->get()`      | Query models with conditions                     |
| `Model::where('foo', 'bar')->first()`    | Retrieve the first result of a query             |
| `Model::where('foo', 'bar')->count()`    | Count results of a query                         |
| `Model::where('foo', 'bar')->delete()`   | Delete results of a query                        |
| `Model::whereRaw('foo = bar and cars = ?', [20])->get()` | Query with raw SQL conditions               |
| `Model::on('connection-name')->find(1)`  | Use a specific database connection               |
| `Model::with('relation')->get()`         | Eager load relationships                         |
| `Model::all()->take(10)`                 | Retrieve the first 10 results                   |
| `Model::all()->skip(10)`                 | Skip the first 10 results                       |

## Soft Deletes

| Command                                  | Description                                      |
|------------------------------------------|--------------------------------------------------|
| `Model::withTrashed()->where('cars', 2)->get()` | Include trashed models in the query       |
| `Model::withTrashed()->where('cars', 2)->restore()` | Restore trashed models                       |
| `Model::where('cars', 2)->forceDelete()` | Permanently delete a model                      |
| `Model::onlyTrashed()->where('cars', 2)->get()` | Retrieve only trashed models                  |

## Events

| Command                                  | Description                                      |
|------------------------------------------|--------------------------------------------------|
| `Event::fire('foo.bar', [$bar])`         | Fire an event                                    |
| `Event::listen('foo.bar', function($bar) {})` | Listen for an event                              |
| `Event::listen('foo.*', function($bar) {})` | Listen for all events matching a pattern      |
| `Event::queue('foo', [$bar])`            | Queue an event                                   |
| `Event::subscribe(new FooEventHandler)`  | Subscribe to events                              |
| `Event::flush('foo')`                    | Flush all queued events                          |

## Mail

| Command                                  | Description                                      |
|------------------------------------------|--------------------------------------------------|
| `Mail::send('email.view', $data, function($message) {})` | Send email using a view                      |
| `Mail::to('recipient@example.com')->send(new MailClass())` | Send email using a Mailable class           |
| `Mail::queue(new MailClass())`           | Queue an email to be sent later                  |
| `Mail::later($delay, new MailClass())`   | Send email after a delay                         |

---

Feel free to modify or expand upon these sections to fit your project's needs.
