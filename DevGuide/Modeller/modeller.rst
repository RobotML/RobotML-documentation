.. _DevGuideModeller:

:ref:`return<DevGuide>`

Modeller
########

Meta modelling
**************

About Papyrus
=============

:term:`Papyrus` is aiming at providing an integrated and user-consumable environment for 
editing any kind of :term:`EMF` :term:`model` and particularly supporting :term:`UML` and related modeling 
languages such as :term:`SysML` and :term:`MARTE`. Papyrus provides diagram editors for EMF-based 
modeling languages amongst them :term:`UML` 2 and :term:`SysML` and the glue required for integrating 
these editors (GMF-based or not) with other :term:`MBD` and MDSD tools.

:term:`Papyrus` provides a very advanced support for :term:`UML` profiles enabling support for 
"pure" :term:`DSL`. Every part of :term:`Papyrus` may be customized: model explorer, diagram editors, 
property editors, etc.

.. seealso:: `Papyrus website <http://www.eclipse.org/papyrus/>`_

Papyrus tutorials
=================

Go to `Papyrus tutorials page <http://www.eclipse.org/papyrus/usersTutorials/usersTutorialsIndex.php>`_.


DSL detailed
************

See `RobotML API documentation <http://www.google.fr>`_.


Installation
************

You need to download the `Eclipse Modelling tools <http://www.eclipse.org/downloads/packages/eclipse-modeling-tools/keplersr1>`_.
Then extract the modeller on your computer and launch it. You need to install :term:`Papyrus`, with :term:`RobotML` extra feature, :term:`Acceleo`, and :term:`Subclipse`.

- To install :term:`Acceleo`, clic on **Help/install Modellign component**, and selection :term:`Acceleo`.
- To install :term:`Papyrus` and :term:`Subclipse`, clic on **Help/Install new software...**, and add the following update site 

Juno version
============

======================= ========================================================================
 Plugin name             update site
======================= ========================================================================
 :term:`Papyrus`         http://download.eclipse.org/modeling/mdt/papyrus/updates/releases/juno
 :term:`Subclipse`       http://subclipse.tigris.org/update_1.10.x
======================= ========================================================================

.. note:: The juno version not support the dynamic validation.

Kepler version
==============

=========================== =========================================================================
 Plugin name                 update site
=========================== =========================================================================
 :term:`Papyrus` (nigthly)   http://download.eclipse.org/modeling/mdt/papyrus/updates/nightly/kepler
 :term:`Subclipse`           http://subclipse.tigris.org/update_1.10.x
=========================== =========================================================================

-----------

:ref:`Up<DevGuideModeller>`