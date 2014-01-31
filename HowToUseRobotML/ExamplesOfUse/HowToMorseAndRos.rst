How-to : MORSE and ROS
======================

Pierrick Koch - `GREYC <https://www.greyc.fr/>`_ -
`CNRS <http://www.cnrs.fr/>`_

`anr-proteus.fr <http://anr-proteus.fr/>`_

Objectif: First step with ROS and MORSE.

--------------

ROS
---

Robot Operating System (ROS) can be seen as 2 main parts:

-  A communication
   `middleware <http://en.wikipedia.org/wiki/Middleware>`_, with related
   APIs (C++, Python, Java),
-  A set of Robotic software (hardware abstraction, drivers, libs).

`roscore <http://ros.org/wiki/roscore>`_: run a
`master <http://ros.org/wiki/Master>`_
`node <http://ros.org/wiki/Nodes>`_

::

    roscore

*TIP*: to stop ``roscore``: press Ctrl+C in the terminal

Basic commands:

`roscd <http://ros.org/wiki/roscd>`_: change directory within ROS
environment

::

    Usage: roscd [package]

`roslaunch <http://ros.org/wiki/roslaunch>`_: launching ROS nodes via
``.launch`` files

::

    Usage: roslaunch [options] [package] <filename> [arg_name:=value...]

cf. `Tutorials <http://ros.org/wiki/ROS/Tutorials>`_

--------------

rostopic
--------

::

    rostopic
    rostopic is a command-line tool for printing information about ROS Topics.

    Commands:
      rostopic bw    display bandwidth used by topic
      rostopic echo  print messages to screen
      rostopic find  find topics by type
      rostopic hz    display publishing rate of topic
      rostopic info  print information about active topic
      rostopic list  list active topics
      rostopic pub   publish data to topic
      rostopic type  print topic type

    Type rostopic <command> -h for more detailed usage, e.g. 'rostopic echo -h'

--------------

rostopic: exemple
-----------------

Publish & print a message on ROS bus:

::

    rostopic pub /test std_msgs/String "Bonjour Proteus"
    rostopic echo /test

`|rostopic| <http://ros.org/wiki/rostopic>`_

--------------

MORSE
-----

Developped at LAAS/CNRS in Toulouse (France), MORSE is a generic robotic
simulation platform based on Blender. Blender is a free and open source
3D modelisation platform. Which integrates differents methods for 3D
rendering, animating, and a game engine used by MORSE for the
simulation, as well as the physic engine Bullet. MORSE allow to build a
robotic simulation by using Blender GUI / API.

Blender 2.5 introduced a new API allowing to interact with all
scene-data through the Blender Python API, aka. ``bpy``.

`|blender-data-api| <http://www.blender.org/development/release-logs/blender-256-beta/data-access>`_

`|blender-roadmap| <http://download.blender.org/release/>`_

--------------

MORSE
^^^^^

`|morse| <http://morse.openrobots.org>`_

--------------

MORSE GLSL
^^^^^^^^^^

MORSE is
`meant <http://www.openrobots.org/morse/doc/latest/user/installation.html#hardware>`_
to run with a graphic card compatible `OpenGL Shading
Language <http://en.wikipedia.org/wiki/GLSL>`_

ATI/AMD Radeon `|AMD| <http://support.amd.com/us/gpudownload/linux/Pages/radeon_linux.aspx>`_
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

9x00, Xx00, X1x00, HD2x00, HD3x00 & +
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

``sudo apt-get install``
```xserver-xorg-video-radeon`` <http://apt.ubuntu.com/p/xserver-xorg-video-radeon>`_

nVidia `|nvidia| <http://www.nvidia.com/object/unix.html>`_
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

Geforce FX, 6x00, 7x00, 8x00, 9x00, GTX 2x0 & +
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

``sudo apt-get install``
```nvidia-current`` <http://apt.ubuntu.com/p/nvidia-current>`_

cf. `Blender System
Requirements <http://www.blender.org/features-gallery/requirements/>`_
`Blender 2.48 Realtime GLSL
Materials <http://www.blender.org/development/release-logs/blender-248/realtime-glsl-materials/>`_

Use the tool ``/usr/bin/jockey-gtk`` to install additional drivers. You
can use ``lspci|grep VGA`` to know your card's name.

--------------

MORSE config
------------

-  Coordinates: `main
   droite <http://en.wikibooks.org/wiki/Blender_3D:_Noob_to_Pro/Understanding_Coordinates>`_

.. figure:: HowToMorseAndRos_images/200px-Rechte-hand-regel.jpg
   :align: center
   :alt: right

   right

-  Units: metric, angle: degree in UI, radian in simulation
-  ROS: `ROS Standard Units of Measure and Coordinate
   Conventions <http://ros.org/reps/rep-0103.html>`_

.. figure:: HowToMorseAndRos_images/screenshot-morse-metric.png
   :align: center
   :alt: metric

   metric

--------------

MORSE & ROS
-----------

-  Naming convention of
   `topics <http://www.openrobots.org/morse/doc/latest/user/middlewares/ros.html#generation-of-ros-node-and-topics>`_

``/Robot/Composant`` alphanumeric CamelCase

::

    rostopic list -v

    Published topics:
     * /ATRV/CameraMain [sensor_msgs/Image] 1 publisher
     * /rosout [rosgraph_msgs/Log] 1 publisher
     * /ATRV/Pose_sensor [nav_msgs/Odometry] 1 publisher
     * /rosout_agg [rosgraph_msgs/Log] 1 publisher
     * /ATRV/Odometry [geometry_msgs/Twist] 1 publisher
     * /ATRV/Sick [sensor_msgs/LaserScan] 1 publisher

    Subscribed topics:
     * /rosout [rosgraph_msgs/Log] 1 subscriber
     * /ATRV/Motion_Controller [geometry_msgs/Twist] 1 subscriber

--------------

MORSE CLI
---------

Once installed, MORSE is launch by the command
``morse {check,edit,run} [scene]``, it accept differents parameters:

-  .blend file (simulation scene)
-  .py file (scene builder script)

ie:

::

    morse edit my_builder_script.py

    morse edit my_saved_scene.blend

... respectively result in:

1. edit a scene build through a script in Blender GUI.
2. edit a scene saved in a .blend file in Blender GUI.

--------------

MORSE: simulation loop
----------------------

`|morse-main-loop| <http://www.openrobots.org/morse/doc/latest/dev/dev_overview.html#morse-execution-loop>`_

--------------

MORSE: scene builder API
------------------------

`|morse-builder| <http://www.openrobots.org/morse/doc/latest/dev/builder.html>`_

cf.
`openrobots.org/morse/doc/latest/dev/builder.html <http://www.openrobots.org/morse/doc/latest/dev/builder.html>`_

--------------

Demo: intro
-----------

robot made of one controler (v, ω)
----------------------------------

::

    !python
    from morse.builder import *

    # Add the robot
    simplebot = Robot('atrv')

    # Add a motion controler
    motion = Actuator('v_omega')
    motion.translate(z=0.3)
    # Connect the controler to the robot
    simplebot.append(motion)

    # Configure the controler with the ROS middleware
    motion.configure_mw('ros')

    # Setup the environment
    env = Environment('indoors-1/indoor-1')
    env.aim_camera([1.0470, 0, 0.7854])

(`code <https://github.com/anr-proteus/proteus/blob/master/proteus_demo/data/wifibot.py>`_)

--------------

Demo: intro (2)
---------------

commands to run
^^^^^^^^^^^^^^^

start a ROS master node
"""""""""""""""""""""""

::

    roscore

start MORSE with a builder script (in another Terminal)
"""""""""""""""""""""""""""""""""""""""""""""""""""""""

::

    morse edit /usr/local/share/morse/examples/scenarii/ros_example.py

⌨ Press "``P``" in the 3D view to start the simulation (Game Engine)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

⌨ Use "``CTRL``" + mouse, and "``Z, Q/A, S, D/W``" to move the camera
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

publish a message on the controler topic (in another Terminal)
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

::

    rostopic pub -1 /ATRV/Motion_Controller geometry_msgs/Twist [1,0,0] [0,0,1]

--------------

Demo: intro (video)
-------------------

.. raw:: html

   <iframe src="http://player.vimeo.com/video/22116926?portrait=0" width="800" height="500" frameborder="0" allowfullscreen></iframe>

(`video <http://vimeo.com/22116926>`_)

--------------

Demo: advanced
--------------

obstacles avoidance w/ laser
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

::

    mkdir -p ~/work/ros-addons
    rosinstall ~/work/ros-addons /opt/ros/electric/ \
        http://anr-proteus.github.com/proteus.rosinstall
    source ~/work/ros-addons/setup.bash
    roscd proteus_demo && git pull && cd data
    morse run wifibot.py

run the master node (in another Terminal)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

::

    roscore

launch our node to control the robot (in another Terminal)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

::

    source ~/work/ros-addons/setup.bash
    roslaunch proteus_demo AvoidObstacleLaser.launch

*TIP*: if ``rosinstall`` is not recognized, install it as:

::

    sudo pip install -U rosinstall

--------------

Demo: advanced (video)
----------------------

.. raw:: html

   <iframe src="http://player.vimeo.com/video/24550587?portrait=0" width="800" height="500" frameborder="0" allowfullscreen></iframe>

(`video <http://vimeo.com/24550587>`_)

--------------

Demo: advanced (code)
---------------------

::

    !python
    # callback for each laser scan
    def handle_sick(msg):
        mid = len(msg.ranges) // 2
        cmd = Twist()
        # stop if an object is less than 2m in a 30deg angle
        halt=False
        for distance_to_object in msg.ranges[mid-15:mid+15]:
            if distance_to_object < 2:
                halt=True
                break
        if halt:
            # rotate on the wider scanned side
            if sum(msg.ranges[:mid]) > sum(msg.ranges[mid:]):
                cmd.angular.z = -1
            else:
                cmd.angular.z = 1
        else:
            cmd.linear.x = 1
        # publie the command to the controler (Twist msg)
        topic.publish(cmd)

    if __name__ == '__main__':
        rospy.init_node('wander')
        topic=rospy.Publisher('/ATRV/Motion_Controller', Twist)
        rospy.Subscriber('/ATRV/Sick', LaserScan, handle_sick)
        rospy.spin()

    # http://ros.org/doc/api/sensor_msgs/html/msg/LaserScan.html
    # http://ros.org/doc/api/geometry_msgs/html/msg/Twist.html

(`code <https://github.com/anr-proteus/proteus/blob/master/proteus_demo/nodes/AvoidObstacleLaser.py>`_)

--------------

Demo: Orocos
------------

The example's code is available on
`GitHub <https://github.com/anr-proteus/proteus/tree/master/proteus_orocos_obstaclelaser>`_

::

    roscd proteus_demo/data
    morse run wifibot.py

    rosmake proteus_orocos_obstaclelaser
    roslaunch proteus_orocos_obstaclelaser AvoidObstacleLaser.launch

`|morse-orocos| <https://github.com/anr-proteus/proteus/tree/master/proteus_orocos_obstaclelaser>`_

--------------

RViz (video)
------------

.. raw:: html

   <iframe src="http://player.vimeo.com/video/23244699?portrait=0" width="800" height="375" frameborder="0" allowfullscreen></iframe>

::

    rosrun rviz rviz

launch rviz with a configuration file
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

::

    roscd proteus_demo/data
    rosrun rviz rviz -d rviz.vcg

(`video <http://vimeo.com/23244699>`_)

--------------

Outdoor (video)
^^^^^^^^^^^^^^^

.. raw:: html

   <iframe src="http://player.vimeo.com/video/26054198?portrait=0" width="800" height="350" frameborder="0" allowfullscreen></iframe>

::

    roscd proteus_demo/data
    morse run wifibot.py

(`video <http://vimeo.com/26054198>`_)

--------------

Exploration (Bosch demo w/ Stage)
---------------------------------

::

    sudo apt-get install ros-electric-bosch-common
    roslaunch explore_stage explore.launch

    roscd explore_stage
    rosrun rviz rviz -d explore.vcg

`|exploration| <http://ros.org/wiki/explore_stage>`_

--------------

Exploration (Bosch demo w/ MORSE)
---------------------------------

.. raw:: html

   <iframe src="http://www.youtube.com/embed/videoseries?list=PL289431A5B18BD997&amp;hd=1&amp;rel=0" width="800" height="500" frameborder="0" allowfullscreen></iframe>

--------------

RTMaps
------

`|rtmaps| <http://intempora.com>`_

--------------

TIPS
----

MORSE create cache files in the current directory,

::

    rm scene.*.blend

allow you to delete those files.

Resources
---------

Blender Cookie: `cgcookie.com/blender <http://cgcookie.com/blender/>`_

Blend Swap: `blendswap.com <http://www.blendswap.com/>`_ (ie. `Rover
model <http://www.blendswap.com/3D-models/vehicles/rover/>`_ )

Blender Wiki: `wiki.blender.org <http://wiki.blender.org/>`_

--------------

Build a robot
-------------

.. raw:: html

   <iframe src="http://www.youtube.com/embed/videoseries?list=PLDC1FC34E5AC69429&amp;hd=1&amp;rel=0" width="800" height="500" frameborder="0" allowfullscreen></iframe>

--------------

That's all Folks!
-----------------

short link to this presentation:
`bit.ly/proteus2 <http://bit.ly/proteus2>`_

.. figure:: http://bit.ly/proteus2.qrcode
   :align: center
   :alt: proteus-morse-demo

1 page doc: `bit.ly/proteus2md <http://bit.ly/proteus2md>`_

sources on GitHub: `bit.ly/proteus-src <http://bit.ly/proteus-src>`_

*made with* `landslide <https://github.com/adamzap/landslide>`_

.. |rostopic| image:: HowToMorseAndRos_images/screenshot-rostopic.png
.. |blender-data-api| image:: HowToMorseAndRos_images/blender-data-api.jpg
.. |blender-roadmap| image:: HowToMorseAndRos_images/blender-roadmap.jpg
.. |morse| image:: HowToMorseAndRos_images/screenshot-morse.png
.. |AMD| image:: HowToMorseAndRos_images/AMD_logo.png
.. |nvidia| image:: HowToMorseAndRos_images/nvidia_logo.png
.. |morse-main-loop| image:: HowToMorseAndRos_images/morse_main_loop.png
.. |morse-builder| image:: HowToMorseAndRos_images/morsebuilder_uml.png
.. |morse-orocos| image:: HowToMorseAndRos_images/screenshot-morse-orocos.png
.. |exploration| image:: HowToMorseAndRos_images/screenshot-explor.png
.. |rtmaps| image:: HowToMorseAndRos_images/screenshot-morse-rtmaps.png
