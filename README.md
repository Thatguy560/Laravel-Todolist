# First Laravel Project

- Laravel is a web application framework with expressive, elegant syntax.  

- Provides features such as dependency injection, an expressive database abstraction layer, queues and scheduled jobs, unit and integration testing.

- Docker is a tool for running applications and services in small, light-weight "containers" which do not interfere with your local computer's installed software or configuration.

# Installing with Docker

- If you're developing on a Mac and [Docker Desktop](https://www.docker.com/products/docker-desktop) is already installed, you can use a simple terminal command to create a new Laravel project. For example, to create a new Laravel application in a directory named "example-app", you may run the following command in your terminal: 

```
curl -s "https://laravel.build/example-app" | bash
```

- You can change "example-app" im this URL to anything you like.

- After the project has been created, you can navigate to the application directory and start Laravel Sail. Laravel Sail provides a simple command-line interface for interacting with Laravel's default Docker configuration.  

```
cd example-app 

./vendor/bin/sail up
```

- The first time you run the Sail up command, Sail's application containers will be built on your machine. This could take several minutes. **Don't worry, sebsequent attempts to start Sail will be much faster.**

Once the application's Docker containers have been started, you can access the application in your web browser at: https://localhost.

# Installing with Composer 

If your computer already has PHP and Composer installed, you may create a new Laravel project by using Composer directly. After the application has been created, you may start Laravel's local development server using the Artisan CLI's **serve** command: 

```
composer create-project laravel/laravel example-app 

cd example-app 

php artisan serve 
```

'example-app' is just the name we gave it, it can be called anything.  

# The Laravel Installer 

Or, you may install the Laravel installer as a global Composer dependency:

```
composer global require laravel/installer 

laravel new example-app 

cd example-app  

php artisan serve (To open up server)
```

# Next Steps and documentation 

[Request Lifecycle](https://laravel.com/docs/8.x/lifecycle)

[Configuration](https://laravel.com/docs/8.x/configuration)

[Directory Structure](https://laravel.com/docs/8.x/structure)

[Service Container](https://laravel.com/docs/8.x/container)

[Facades](https://laravel.com/docs/8.x/facades)