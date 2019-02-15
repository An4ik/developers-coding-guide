Local Deployment (manually)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^
We have run our project on local machine. So here is an instructions how to do it.


Clone project
-----------------

Simply clone the project from repository on my github account.
::

    git clone https://github.com/An4ik/beta_career
    git clone git@github.com:An4ik/beta_career.git


Install virtual environment
------------------------------
You have project on your local machine, so now is time to isolate your
development environment i.g. create virtual environment.

::

    python3 -m virtualenv venv

It will create directory called **venv** in your current directory.
::

    # For activating
    source venv/bin/activate

    # for deactivating
    deactivate

Sometimes it's difficult to change directory to your **venv**, activating/deactivating
it. So fortunately we have `VirtualenvWrapper <https://virtualenvwrapper.readthedocs.io/en/latest/>`_
library solving our problem. Try to use it, since it will economy your time in the future.


Install Dependencies
----------------------
To install project dependencies simply run command below

::

    pip install -r requirements/local.txt

.. warning::
   You may have some problem during installation. So it's your problem --> google it.
..

Setup database
---------------
Make sure that you've installed PostgreSQL on your local machine. Then simply run::


    # login as **postgres** user
    sudo su - postgres

    # attempt to psql shell
    psql

    # It's easy to create all stuff (db, role, password) as project's name.

    # create database
    postgres=# create database <database_name>;

    # create user (role)
    postgres=# create user <user_name> with password '<password>';

    # grant all privileges
    postgres=# grant all privileges on database <database_name> to <user_name>;


Run migrations
---------------
Running migration i.g. do changes on database

::

    ./manage.py migrate


Run server
-------------
Run server on your local machine, but make sure that your **8000** port doesn't used.
::

    ./manage.py runserver


Ensure that you've done
------------------------
Simply open any web-browser and enter URL: **localhost:8000** you should see main page.

Good job!
