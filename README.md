# django-boilerplate

Base project of a django service
License: MIT

## Basic Commands

### Setting Up Your Users

-   To create a **normal user account**, just go to Sign Up and fill out the form. Once you submit it, you'll see a "Verify Your E-mail Address" page. Go to your console to see a simulated email verification message. Copy the link into your browser. Now the user's email should be verified and ready to go.

-   To create a **superuser account**, use this command:

        $ python manage.py createsuperuser

For convenience, you can keep your normal user logged in on Chrome and your superuser logged in on Firefox (or similar), so that you can see how the site behaves for both kinds of users.

### Type checks

Running type checks with mypy:

    $ mypy django_boilerplate

### Test coverage

To run the tests, check your test coverage, and generate an HTML coverage report:

    $ coverage run -m pytest
    $ coverage html
    $ open htmlcov/index.html

#### Running tests with pytest

    $ pytest

## Deployment

The following details how to deploy this application.

### Docker

#### Building & Running Production Stack

You will need to build the stack first. To do that, run:

    $ docker-compose -f production.yml build

Once this is ready, you can run it with:

    $ docker-compose -f production.yml up

To run the stack and detach the containers, run:

    $ docker-compose -f production.yml up -d

To run a migration, open up a second terminal and run:

    $ docker-compose -f production.yml run --rm django python manage.py migrate

To create a superuser, run:

    $ docker-compose -f production.yml run --rm django python manage.py createsuperuser

If you need a shell, run:

    $ docker-compose -f production.yml run --rm django python manage.py shell

To check the logs out, run:

    $ docker-compose -f production.yml logs

If you want to scale your application, run:

    $ docker-compose -f production.yml up --scale django=4
