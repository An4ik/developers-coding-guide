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
