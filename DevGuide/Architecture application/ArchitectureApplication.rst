.. _DevGuideArchitectureApplication:

:ref:`Retourn<DevGuide>`

Arhitecture application
#######################

Generality
**********

.. image:: ./images/architecture_application.png
 :align: center
 :alt: Architecture application

Repository architecture
***********************

.. warning:: This section will be strictly respected in your developement.

On the root, we find:

=============== ==============================================
 Folder          Description
=============== ==============================================
 dsl-papyrus     Contains all papyrus DSL development
 dsl-xtext       Contains all DSL specified with xtext
 generators      Contains all generator's developpement
 features        Contains all features project
 update-sites    Contains all update site for the platform
=============== ==============================================  

DSL Papyrus
===========

It contain the papyrus's DSL development. 

=================== ==========================================================
 Folder              Description
=================== ==========================================================
 robotml             Contain all development about the RobotML DSL.
 robotml-extension   Contain all development about the RobotML DSL extension.    
=================== ==========================================================

DSL Xtext
=========

It contain the xtext's DSL development

=================== ==========================================================
 Folder              Description
=================== ==========================================================
 AthenaDSL           Contain all developement project for Athena DSL.
=================== ==========================================================

Generators
==========

It contains all generators development projects.

=================== ==================================================================================
 Folder              Description
=================== ==================================================================================
 Athena              Contain all development project to transcoding RobotML model on Athena language.
 Common              Contain all development common's project for the generators.
 CycabTk             Contain all development project to transcoding RobotML model to CycabTk.
 MORSE               Contain all development project to transcoding RobotML model to MORSE.
 OROCOS              Contain all development project to transcoding RobotML model to OROCOS.
 RTMaps              Contain all development project to transcoding RobotML model to RTMaps.
 xtext               Contain all development project to transcofing Athena DSL model to VLE.
=================== ==================================================================================

If your need to create a new middleware generator:

1. Create a new directory with the middleware's name.
2. Put in this new directory your generator's development project. 

-----------

:ref:`Up<DevGuideArchitectureApplication>`
