# (ARCHIVED) EAFC Web Development Exam Project Fullstack

## Archive note

This repository will be archived as of **08/02/2022 (D/M/Y), 9PM (UTC+1 Brussels)** for school access.
You can find the forked repository [here](https://github.com/PinsonJulien/EAFC-Web-Development-Exam-Project-Fullstack)


## Context

This repository is related to my Web Development Exam from my bachelor degree in Business Computing, 2nd year.
You can consult the *scope statement* (in French) in the `scope.pdf` file at root.

This application is using **Angular 15** and **Laravel 9**, scaffolded as a **Rest api** using session based authentication. They both have their own repositories which are submodules of this one.

## Minimal requirements

### Laravel 9

- PHP 8.0
- MySQL 5.7.36
- Composer 2.3.10

### Angular 15

- [NodeJS v16.13.1](https://nodejs.org/en/download/)
- NPM v8.3.0 (included with NodeJS)
- Backend from this [repository](https://github.com/PinsonJulien/school-website-backend-laravel)
- [Angular CLI v15.1.4](https://angular.io/guide/setup-local#install-the-angular-cli)

### Database configuration

Make sure your mysql database:
- Is using `InnoDB` as the engine.
- Has `default-row-format` set to `dynamic`.

## Setting up the project

### Laravel

In `cd EAFC-Web-Development-Exam-Project-Backend-Archive`
- Run `composer install`
- Copy the `.env.example` file to `.env` and replace environment variables that do not fit your database configuration.
- Make the sure the .env has `FILESYSTEM_DRIVER=public` this will ensure the files are properly saved.
- Make sure the `FRONTEND_URL` .env variable matches `http://127.0.0.1:5000/`
- Run `php artisan key:generate` (this will fill the **APP_KEY** .env variable).
- Run `php artisan storage:link` to create a **symbolic link** between *public/storage* and *storage/app/public*
- Run `php artisan migrate` command to generate all the tables.

### Angular

In `cd EAFC-Web-Development-Exam-Project-Frontend-Archive`
- If it's not done already, install the Angular CLI : `npm install -g @angular/cli`
- run `npm install`
- In `src/environments/enronment.ts`, make sure the `baseUrl` matches `127.0.0.1:8000/`.

## Preparing data for the demo

### Laravel 

In `cd EAFC-Web-Development-Exam-Project-Backend-Archive`
Run `php artisan db:seed --class=DemoSeeder` to populate the database.

Each SiteRole has an initial User, you can log yourself using these credentials (email ; password)
- Guest: **guest@site.com** ; **guest**
- User: **user@site.com** ; **user**
- Secretary: **secretary@site.com** ; **secretary**
- Administrator: **administrator@site.com** ; **administrator**
- Banned: **banned@site.com** ; **banned**

## Running the project

Make sure you have two consoles open.

### Laravel

In `cd EAFC-Web-Development-Exam-Project-Backend-Archive`
Run `php artisan serve`

### Angular

In `cd EAFC-Web-Development-Exam-Project-Frontend-Archive`
Run `ng serve --host 127.0.0.1 --port 5000 --open` and access the application at `http://127.0.0.1:5000/`.

## Project evolutions

Both frontend and backend have their own project evolutions in their respective readme.