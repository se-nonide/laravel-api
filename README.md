# Laravel test Rest API

This is a project made in PHP using the Laravel framework to build a simple example Rest API. 
The project is based on the official Laravel documentation.

<img title="Laravel" alt="Laravel logo" width="100" src="https://laravel.com/img/logomark.min.svg">

## Technologies to use
- Built in ORM
- JWT for auth


## Run the project

To run the project run:
```
cd example-app
php artisan serve
```

## Laravel developer guide

This section consists of a brief guide to developing in Laravel

### Creation of a new entity in the App

To create a new entity in the application you must follow the next steps. The new entity will be called `Student`.

#### Migration

First we will create the migration for the new table in the database:
```
php artisan make:migration crate_students_table
```

Add the following code on the new migration in `example-app/database/migrations/yyyy_mm_dd_hhmmss_create_students_table.php`:
```php
public function up(): void
{
    Schema::create("students", function (Blueprint $table) {
      // Here the attributes that the db table has are defined
      $table->id();
      $table->string("name");
      $table->string("course");
      $table->string("email");
      $table->string("phone");
      $table->timstamps();
    });
}

```

Once is done, we will migrate the database with the following command:
```
php artisan migrate
```

#### Model
Then we will create the model within our application with the following command:
```
php artisan make:model Student
```

Add the following code on the new model in `example-app/app/Models/Student.php`:
```php
protected $table = "students";
protected $fillable = [
  // Here the attributes that the model has are defined
  "name", "course", "email", "phone" 
];
```

#### Controller
Then we will create the controller for the new entity. Run the following command:
```
php artisan make:controller StudentController
```

Inside the controller we will create a function that acts as a handler:
```php
class StudentController extends Controller
{
    // This will be a handler for a http route
    public function index() {
        return "Hello World!";
    }
}

```

So finally we will link the controller to an endpoint in `example-app/routes/api.php`:
(Remember to import the StudentController in `api.php` file)
```php
Route::get("students", [StudentController::class, 'index']);
```

You can check all is rigth on http://localhost:8000/api/students after serving the app.
