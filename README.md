#####Laravel: 5.7
#####Vue: 2.5

After you clone this project, do the following:

```bash
# go into the project
cd Vue-Laravel-SPA

# create a .env file
cp .env.example .env

# install composer dependencies
composer update

# install npm dependencies
npm install

# generate a key for your application
php artisan key:generate

# generate Server secret for JWT
php artisan jwt:secret

# create a local MySQL database (make sure you have MySQL up and running)
mysql -u root

> create database vuespa_db;
> exit;

# add the database connection config to your .env file
DB_CONNECTION=mysql
DB_DATABASE=vuespa_db
DB_USERNAME=root
DB_PASSWORD=

# run the migration files to generate the schema
php artisan migrate

# run webpack and watch for changes
npm run watch
```
