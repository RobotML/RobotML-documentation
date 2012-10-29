How-to : CycabTK Simulator
==========================

Amaury Nègre - `e-Motion <http://emotion.inrialpes.fr/>`_ -
`CNRS <http://www.cnrs.fr/>`_ `/` 
`Inria <http://www.inria.fr/>`_


`anr-proteus.fr <http://anr-proteus.fr/>`_

Objectives: First step with CycabTK.

--------------

CycabTK
-------

`CycabTK <http://cycabtk.gforge.inria.fr>`_ is a robotic toolkit developed at Inria Grenoble.
It mainly offers a 3D simulator integrating physics engine for mobile robots. It has been designed to be interfaced with ROS.
Prior version of the toolkit also offers a blackboard-based middleware, named Hugr, automatic mobile robot drivers and
sensor drivers (sensors as Sick laser, GPS, motion tracker, mono or stereo camera).

--------------

Installation
------------

CycabTK Simulator is a `ROS <http://www.ros.org/wiki>`_ package that provide a set of `mg-Engine <http://mgengine.sourceforge.net>`_
plugins to simulate robots and sensors.
 
Install from the proteus repository on Ubuntu 12.04 i386 :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
 
If you use Ubuntu 12.04 i386, you just have to install the **CycabTKSimulator** package from the proteus repository
(`https://packages.greyc.fr/proteus <https://packages.greyc.fr/proteus>`_) : ::

   $ apt-get install CycabTKSimulator

Install from sources :
^^^^^^^^^^^^^^^^^^^^^^

To install the simulator from the sources, read `instructions <http://cycabtk.gforge.inria.fr/wiki/doku.php?id=download2>`_ on the CycabTK main site


Test installation :
-------------------

To verify the installation, you can launch the tutorial launchfile : ::

   $ roslaunch CycabTKSimulator cycabtk_tutorial.launch 
   
After that, you should see a window like this :

.. figure:: HowToCycabTK_images/cycabtk_tutorial_screenshot.png 
   :align: center
 
 You can move the robot by pressing the keyboard arrows.
 
 You can check you have sensors / commands topics in ROS : ::
 
   $ rostopic list
   /clock
   /robot/camera/camera_info
   /robot/camera/image_raw
   /robot/camera/image_raw/compressed
   /robot/camera/image_raw/compressed/parameter_descriptions
   /robot/camera/image_raw/compressed/parameter_updates
   /robot/camera/image_raw/compressedDepth
   /robot/camera/image_raw/compressedDepth/parameter_descriptions
   /robot/camera/image_raw/compressedDepth/parameter_updates
   /robot/camera/image_raw/theora
   /robot/camera/image_raw/theora/parameter_descriptions
   /robot/camera/image_raw/theora/parameter_updates
   /robot/ground_vehicle_odometry
   /robot/hokuyo/scan
   /robot/ir1/range
   /robot/ir2/range
   /robot/twistCommand
   /rosout
   /rosout_agg
   /tf
   

Create a new simulation
-----------------------
Instructions to create a new simulation are available on the CycabTK web site : `<http://cycabtk.gforge.inria.fr/wiki/doku.php?id=tuto:tutorial>`_
