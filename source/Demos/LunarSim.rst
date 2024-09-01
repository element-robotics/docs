Lunar Sim Demo
==============

Space ROS Lunar Sim Demo Docker Image
-------------------------------------

The Space ROS Lunar Sim Demo docker image uses the spaceros docker image (*osrf/space-ros:latest*) as its base image.
The Dockerfile installs all of the prerequisite system dependencies along with the demo source code, then builds the Space ROS Lunar Sim Demo.

This demo includes a Gazebo simulation of the lunar environment (specfically around the Shackleton crater near the south pole). It uses
Digital Elevation Models (DEMs) from the Lunar Orbiter Laser Altimeter (LOLA) to accurately simulate the lunar surface in a specific region. It also contains a dynamic model of the Sun that moves according to Ephemeris data.  

Building the Demo Docker
^^^^^^^^^^^^^^^^^^^^^^^^

The demo image builds on top of the spaceros image.
To build the docker image, first ensure the spaceros base image is available either by `building it locally <https://github.com/space-ros/space-ros>`_ or pulling it.

Then build lunar_sim demo images:

.. code-block:: bash

  cd ../lunar_sim
  ./build.sh


Running the Demo Docker
^^^^^^^^^^^^^^^^^^^^^^^

Run the following to allow GUI passthrough:

.. code-block:: bash

  xhost +local:docker


Then run:

.. code-block:: bash

	./run.sh


Depending on the host computer, you might need to remove the ``--gpus all`` flag in ``run.sh``, which uses your GPUs.

