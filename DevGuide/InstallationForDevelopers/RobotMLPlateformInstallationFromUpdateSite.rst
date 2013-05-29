.. _DG-IFD-RPI:

:term:`RobotML` platform installation from update site
======================================================

Introduction
------------

As it was discussed in the :ref:`RobotML tooling installation page <UG-PI-IRT>`\ , The RobotML platform is constituted of many components. As a developer or for your information as an advanced user, you can be interested to discover it. Here follows the detailed description of how to install its many components one after the other.

Directives provided here allow to install the complete platform for modelling, code generation and validation. 


How to install Modelling components
-----------------------------------

	1. Install the latest version of eclipse Juno: you have to download it from `Juno eclipse website <http://www.eclipse.org/downloads/packages/eclipse-modeling-tools/junosr1>`_\ , then, if java is installed and thus whatever the OS
	2. Install the latest version of Papyrus
	
		a. Open the modelling panel: on the menu, choose *help* then in it choose *Install modeling components*
		b. select :term:`papyrus` component:
		
.. figure::   RevisitOfPlatformInstallation_images/ModelingComponents.png
   :align:   center
   :width:   400
   :alt:     Modeling components installation panel

   *Modeling components installation panel*

.. note::

   The modelling panel is in fact just a shortcut to the classical eclipse installation methodology. After installing eclipse Juno, you can click on *Help then Install New Software* then add the different needed update site linked to the three different component quoted above (The :ref:`glossary <G>` provides more information on where to find the specific needed information for each of them).

How to install mandatory components for RobotML platflorm
---------------------------------------------------------

	1. How to install :term:`RobotML` Modeling tools: the language is based upon :term:`papyrus` framework. It is installed thanks to the update site mechanism as (choose help/install new software in :term:`eclipse`\ ):
	
.. figure:: RevisitOfPlatformInstallation_images/InstallNewSoftwarePanel.png
   :align:   center
   :width:   600
   :alt:     Install new software panel

   *Install new software panel accessible from help menu*
   
	2. It is necessary to create an update site in order to install :term:`RobotML` thus after selecting add button, the following panel appears.

.. figure:: RevisitOfPlatformInstallation_images/UpdateSiteDefinitionPanel.png
   :align:   center
   :width:   300
   :alt:     Definition of update site panel

   *Definition of update site panel accessible from add button*

		a. You should add a name to your update site. RobotML name is not mandatory but is useful if you have to edit it in order to recognise your update site easily in the list.
		b. Location is mandatory and is *http://proteus.bourges.univ-orleans.fr/modelling_platform/org.eclipse.papyrus.robotml.update.site*.

	3. Select :term:`RobotML` Modeling Tools and follow the procedure

.. figure:: RevisitOfPlatformInstallation_images/SelectionOfRobotMLComponents.png
   :align:   center
   :width:   500
   :alt:     Selection of RobotML update site components

   *RobotML components to select*

Install SVN
-----------

:term:`SVN` is extremely important to the project as it is one of the :term:`portal`\ /\ :term:`RobotML` platform connection link. In order to install it, there are two steps:

	1. Find the latest version of Eclipse update site

		a. at go to http://subclipse.tigris.org/servlets/ProjectProcess?pageID=p4wYuA

.. figure:: RevisitOfPlatformInstallation_images/InstallSVN-Portal.png
   :align:   center
   :width:   500
   :alt:     Determination of SVN update site

   *SVN update site web address*

	2. Use the address in :term:`eclipse` in order to install :term:`SVN` component.