Fly - Phalcon Admin

Website & Documentation: https://laravelvoyager.com
Video Tutorial Here: https://laravelvoyager.com/academy/
Join our Slack chat: https://voyager-slack-invitation.herokuapp.com/

Phalcon Admin & BREAD System (Browse, Read, Edit, Add, & Delete), supporting Phalcon 3.x

# Requirements
NGINX + FPM or Apache
PHP 7.x
Composer

# Installation Steps
1. Require the Package
After creating your new Phalcon application you can include the Fly package with the following command:

composer require tcg/voyager
2. Add the DB Credentials & APP_URL
Next make sure to create a new database and add your database credentials to your .env file:

DB_HOST=localhost
DB_DATABASE=homestead
DB_USERNAME=homestead
DB_PASSWORD=secret
You will also want to update your website URL inside of the APP_URL variable inside the .env file:

APP_URL=http://localhost:8000
Only if you are on Phalcon 3.x will you need to Add the Service Provider.

3. Run The Installer
Lastly, we can install voyager. You can do this either with or without dummy data. The dummy data will include 1 admin account (if no users already exists), 1 demo page, 4 demo posts, 2 categories and 7 settings.

To install Fly without dummy simply run

php artisan voyager:install
If you prefer installing it with dummy run

php artisan voyager:install --with-dummy
Troubleshooting: Specified key was too long error. If you see this error message you have an outdated version of MySQL, use the following solution: https://laravel-news.com/laravel-5-4-key-too-long-error

And we're all good to go!

Start up a local development server with php artisan serve And, visit http://localhost:8000/admin.

Creating an Admin User
If you did go ahead with the dummy data, a user should have been created for you with the following login credentials:

email: admin@admin.com
password: password

NOTE: Please note that a dummy user is only created if there are no current users in your database.

If you did not go with the dummy user, you may wish to assign admin privileges to an existing user. This can easily be done by running this command:

php artisan voyager:admin your@email.com
If you did not install the dummy data and you wish to create a new admin user you can pass the --create flag, like so:

php artisan voyager:admin your@email.com --create
And you will be prompted for the user's name and password.
