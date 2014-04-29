.. _RMLPI-DIG:

Developper Installation Guide
*****************************

Modeller
========

You need to download the `Eclipse Modelling tools <http://www.eclipse.org/downloads/packages/eclipse-modeling-tools/keplersr1>`_.
Then extract the modeller on your computer and launch it.
Next, you need to install :term:`Papyrus`, with :term:`RobotML` extra feature, and :term:`Subclipse`.

.. _Papyrusinstallation:

Papyrus
=======

In **Help** menu, select "Install new software...". Clic on "Add" button, and add the right update site.

================= ========================================================================= 
 Eclipse version   Update site
================= =========================================================================
 Juno              http://download.eclipse.org/modeling/mdt/papyrus/updates/releases/juno
 Kepler            http://download.eclipse.org/modeling/mdt/papyrus/updates/nightly/kepler
================= =========================================================================
 
Install the "Papyrus UML" components.

.. _RobotMLInstallation:

RobotML
=======

To install :term:`RobotML`, :term:`Papyrus`is required. See :ref:`Papyrus installation<Papyrusinstallation>` to install it.
In **Help** menu, select **Install new software...**, and choose the **Papyrus update site**. Uncheck the **group item** option.
In the filter field, enter **RobotML** and select the binary element. You can now validate the installation.

.. _RobotMLExtensionInstallation:

RobotML extension
=================
RobotML extension is not include as feature of :term:`Papyrus`. You need to build the *RobotML extension* update site to install it.

RobotML extension building
''''''''''''''''''''''''''

Create a new workspace named as *RobotML_Extension*. Import from :term:`git` the projet following project:
- org.eclipse.papyrus.robotml.extension
- org.eclipse.papyrus.robotml.extension.feature
- org.eclipse.papyrus.robotml.extension.update

In the *org.eclipse.papyrus.robotml.extension.update* open the file *site.xml*. And clic and the **Build All** button.

.. comment
   image:: images/robotml_extension_build.png
   align: center
   alt: RobotML extension building.

The files *Artfact.jar* and *XXXXXX.jar* as been created in the update site project.

Now Got to the **Help** menu and choose **Install new software...**. Clic on the **Add** button and select to add a local update site.

.. comment
   image:: images/robotml_extension_add_site.png
   align: center
   alt: Add robotML extension update site

Select the path of the update site project, and validate. In the update site viewer, check the *Dynamic validation* item. 

.. comment
   image:: images/robotML_extension_selection.png
   align: center
   alt: RobotML extension item selection update

Click next and accept the condition to finish the installation.

Ok the extension as been install on your platform.

Generator
=========

Acceleo
'''''''

To install :term:`Acceleo` on your platform, use the Eclips's tool **Install Modeling Component**, from the ***Help** menu.

.. seealso:: :ref:`Acceleo presentation<DevGuideGeneratorAcceleo>`   

XText
'''''

To install :term:`Xtext` on your platform, use the Eclips's tool **Install Modeling Component**, from the ***Help** menu.

RTMaps
''''''

:term:`RTMaps` has an extras feature of :term:`Papyrus`. To use you need to have :term:`Papyrus` and :term:`RobotML` installed on yout platform.

.. seealso:: :ref:`Papyrus installation<Papyrusinstallation>` and :ref:`RobotML installation<RobotMLInstallation`

In **Help** menu, select **Install new software...**, and choose the **Papyrus update site**. Uncheck the **group item** option.
In the filter field, enter **RTMaps** and select the binary element. You can now validate the installation.

.. comment
   image:: images/rtmaps_installation.png
   align: center
   alt: Install RTMaps RobotML generator
   
.. seealso:: :ref:`RTMaps presentation<>`

OROCOS
''''''

:term:`OROCOS` has an extras feature of :term:`Papyrus`. To use you need to have :term:`Papyrus` and :term:`RobotML` installed on yout platform.

.. seealso:: :ref:`Papyrus installation<Papyrusinstallation>` and :ref:`RobotML installation<RobotMLInstallation`

In **Help** menu, select **Install new software...**, and choose the **Papyrus update site**. Uncheck the **group item** option.
In the filter field, enter **OROCOS** and select the binary element. You can now validate the installation.

.. comment
   image:: images/orocos_installation.png
   align: center
   alt: Install OROCOS RobotML generator
   
.. seealso:: :ref:`Orrocos presentation<>`

ARROCAM
'''''''

:term:`ARROCAM` has an extras feature of :term:`Papyrus`. To use you need to have :term:`Papyrus` and :term:`RobotML` installed on your platform.

.. seealso:: :ref:`Papyrus installation<Papyrusinstallation>` and :ref:`RobotML installation<RobotMLInstallation`

In **Help** menu, select **Install new software...**, and choose the **Papyrus update site**. Uncheck the **group item** option.
In the filter field, enter **Arrocam** and select the binary element. You can now validate the installation.

.. comment
   image:: images/arrocam_installation.png
   align: center
   alt: Install Arrocam RobtoML generator
   
.. seealso:: :ref:`Arrocam presentation<>`

Dynamic Validation
==================

Dynamic validation is a RobotML extension include. It be installed, with the extension.

.. seealso:: :ref:`Dynamic validation presentation<>`

:ref:`Up<RMLPI-DIG>`