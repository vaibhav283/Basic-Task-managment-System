# Basic-Task-managment-System
Basic Task managment System with Yajra datatable, CRUD operation
# Task Name: Basic Taks Managment System

# Requirement: 
PHP:8x
Laravel: 8x/9x or above
Mysql: 8 or above
Bootstrap: 4x

# Install laravel 
composer create-project laravel/laravel:^9.0 basic-tms

# Create database in mysql and connect database. Open .env file from the root and add db credentials
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=basic-tms
DB_USERNAME=root
DB_PASSWORD=

# Install yajra package
composer require yajra/laravel-datatables-oracle

# Goto config\app.php
add class in provider Yajra\DataTables\DataTablesServiceProvider::class

'DataTables' => Yajra\DataTables\Facades\DataTables::class

# Publish it
php artisan vendor:publish --provider="Yajra\DataTables\DataTablesServiceProvider"

# Create model name as task along with migration file
php artisan make:model Task -m
(app\Models\Task.php)

# Create seedeer for the table task
php artisan make:seeder TaskTableSeeder   
(database\seeders\TaskTableSeeder.php)

# Run the seeder
php artisan db:seed --class=TaskTableSeeder

# Create controller
php artisan make:controller TasksController
(app\Http\Controllers\TasksController.php)

# Views
For layout : resources\views\app.blade.php
For views 
Task list: resources\views\tasks\list.blade.php  
Add Task: resources\views\tasks\add.blade.php    
Edit Task: resources\views\tasks\edit.blade.php  
View task can view throught Modal in list.blade.php

# If required database dump basic-tms.sql file is copied in the root

URL: http://127.0.0.1:8000/task


