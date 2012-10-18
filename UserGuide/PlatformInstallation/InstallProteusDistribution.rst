.. _UG-PI-IPD:

Install RobotML-sdk
-------------------

This presentation aims at helping you to install :term:`RobotML-sdk`\ .

More information is available in different locations:

	1. As this sdk was developed thanks to the :term:`PROTEUS` project, information can be found on its `website,  anr-proteus.fr <http://anr-proteus.fr/>`_\ ;
	2. The `Formal robotic portal <http://anr-proteus.fr/>`_ is the place where all accessible information, data, tools, etc can be found;
	3. This very document includes a :ref:`detailed description <DG_IFD_RODI>` of the different tools installed and how to test their correct installation using a specific installer.

.. TODO
	update the link to the portal and the page concerned inside


Introduction
````````````

.. figure:: InstallProteusDistribution_images/proteus.svg
   :width: 600px
   :align: center
   :alt: proteus

:term:`RobotML-sdk` is a set of tools developed or selected within the PROTEUS project when specifying it. As already explained and shown again on the picture,
in order to provide the whole power of RobotML, there is a need to provide the different possible targets on which
to generate actual behaviour for the robot either in :term:`simulators <simulator>` or in actual robots.
It is available as a set of Debian packages for the selected project's operating system Ubuntu Linux distribution.

Those tools are up-to-date on PROTEUS APT repository hosted by `univ-orleans.fr <http://proteus.bourges.univ-orleans.fr>`__.

.. Warning::
	The repository's access is secured, as some software are not free, every member has credentials to install and update his distribution.
	
.. TODO
	it is necessary to adapt the last sentence to point to the portal on the subscription page.


RobotML-sdk constitution
````````````````````````

Here follows the list of tools included in the sdk.

-  Main tools

   -  `ROS <http://www.ros.org>`__ Robot Operating System
   -  `Eclipse <http://eclipse.org>`__/`Papyrus <http://eclipse.org/papyrus>`__
   -  `Protege <http://protege.stanford.edu>`__

-  Simulation plateform

   -  `CycabTK <http://cycabtk.gforge.inria.fr>`__
   -  `MORSE <http://morse.openrobots.org>`__
   -  `VLE <http://www.vle-project.org>`__

-  Robotic framework

   -  `Arrocam <http://effidence.com/fr/effibox/decouvrir.html>`__
   -  `RTMaps <http://intempora.com/technology/rtmaps-software>`__
   -  `Urbi <http://gostai.com/products/urbi>`__
   -  `Orocos <http://orocos.org>`__


Ubuntu installation
```````````````````

In order to harmonise software integration, Ubuntu Linux distribution was chosen.
 
-	The latest `LTS <https://wiki.ubuntu.com/LTS>`__, the 12.04 (32 bits, x86 architecture), is the reference version. LTS stands for Long Term Support (5 years), meaning for the 12.04, until 2017!
-	`Download Ubuntu 12.04 (Precise Pangolin) <http://releases.ubuntu.com/precise/ubuntu-12.04.1-desktop-i386.iso>`__ (image CD ISO ~700 MB)
-	Follow instruction provided by Ubuntu to install image on your own computer

.. note::
	allow at least 10 GB for your installation (15 should be enough)

Menu installation
`````````````````

.. TODO
	describe menu installation from portal as soon as ready

Authoring
`````````

.. sectionauthor:: Pierrick Koch <pierrick.koch@laas.fr>