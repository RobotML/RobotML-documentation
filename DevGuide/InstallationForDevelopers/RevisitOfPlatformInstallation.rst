.. _DG-IFD-RPI:

Revisit of Platform Installation
================================

Introduction
------------

As it was discussed in the :ref:`RobotML tooling installation page <UG-PI-IRT>`\ , The RobotML platform is constituted of many components. As a developer or for your information as an advanced user, you can be interested to discover it. Here follows the detailed description of how to install its many components one after the other.

Directives provided here allow to install the complete platform, modelling, generation and validation, on every :term:`OS` that supports JAVA and C/C++ compilation. However, when needed there could be indication specifying limits on this assumption. 

How to install Modelling components
-----------------------------------

	1. Install the latest version of eclipse Indigo: you have to download it from `Indigo eclipse website <http://www.eclipse.org/downloads/packages/eclipse-modeling-tools/indigor>`_\ , then, if java is installed and thus whatever the OS
	2. Install the latest version of Papyrus, Xtext and Acceleo
	
		a. Open the modelling panel: on the menu, choose *help* then in it choose *Install modeling components*
		b. select :term:`papyrus`, :term:`Xtext` and :term:`Acceleo` components:
		
.. figure::   RevisitOfPlatformInstallation_images/ModelingComponents.png
   :align:   center
   :width:   400
   :alt:     Modeling components installation panel

   *Modeling components installation panel*

.. note::

   The modelling panel is in fact just a shortcut to the classical eclipse installation methodology. After installing the eclipse indigo flavour, you can click on *Help then Install New Software* then add the different needed update site linked to the three different component quoted above (The :ref:`glossary <G>` provides more information on where to find the specific needed information for each of them).

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

		a. A name is interesting to give to this update site. RobotML name is not mandatory but is useful if you have to edit it in order to recognise your update site easily in the list of them.
		b. Location is mandatory and is *http://proteus.bourges.univ-orleans.fr/modelling_platform/org.eclipse.papyrus.proteus.update.site*. Copy/Paste to the Location field.

	3. Select :term:`RobotML` Modeling Tools and follow procedure (the complete procedure is similar to any similar things)

.. figure:: RevisitOfPlatformInstallation_images/SelectionOfRobotMLComponents.png
   :align:   center
   :width:   500
   :alt:     Selection of RobotML update site components

   *RobotML components to select*

Install SVN
-----------

:term:`SVN` is extremely important to the project as it is one of the :term:`portal`\ /\ :term:`RobotML` platform connection link. In order to install it on the platform, there are two steps (notwithstanding classical update site operations):

	1. Find the latest version of Eclipse update site

		a. at go to http://subclipse.tigris.org/servlets/ProjectProcess?pageID=p4wYuA

.. figure:: RevisitOfPlatformInstallation_images/InstallSVN-Portal.png
   :align:   center
   :width:   500
   :alt:     Determination of SVN update site

   *SVN update site web address*

	2. Use the address in :term:`eclipse` in order to install :term:`SVN` component.