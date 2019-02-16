Local Deployment with Docker
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

We have run our project by using docker. So here is an instructions how to do it.

.. warning::

   Ensure you have installed *Docker* and *docker-compose*

---------

Once you are having docker-compose on your local machine simply use these commands:

::

    # To building images etc.
    sudo docker-compose -f local.yml build

    # To run it
    sudo docker-compose -f local.yml run



You can find credentials of database in a folder *./envs/.local/.postgres*. If you want to change it rebuilding won't help since docker has cached volumes. To do so
just remove existed volumes and rebuild it again.
::

    docker system prune -a --volumes --force


As with any shell command that we wish to run in our container, this is done using the **docker-compose -f local.yml run --rm command**

::

    $ docker-compose -f local.yml run --rm django python manage.py migrate
    $ docker-compose -f local.yml run --rm django python manage.py createsuperuser