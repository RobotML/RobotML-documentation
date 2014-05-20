.. RobotML documentation master file, created by
   sphinx-quickstart on Mon Jul  2 22:20:55 2012.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.
   Throughout the different document, there is a need to tag the sections or figures
   or whatever. In order to implement this important feature allowing hyperlinks
   to exist, there is a need to create a scheme for the different tags. In 
   ReST, it means ".. tagname:". tagname is done folloing the convention
   prefix "_", then for each folder parent folder, introduce the set
   of capital of the folder name separated by "_" and at the end,
   the capital letter of the filename added of a letter to choose specific
   of the position in the document. As an axample, the first tag hereafter is
   _I because the filename is index (first letter taken when no capital letter)
   and there are no folder above. The following tag is _I_RMLD because we are tagging
   the section called RobotML Documentation into the index file.

.. _I:

.. note::
   This page introducess the :term:`RobotML` platform (see section below)
   as well as the the way to build the documentation you are reading (see :ref:`I_DHT`).
   There is, following, a section dedicated to indices and tables (see :ref:`I_IT`)
   and finally a list of websites linked to the platform (see :ref:`I_LW`). 

.. _I_RMLD:

RobotML Documentation
=====================

In the robotic domain, academic as well as industry, there is nowadays a need to describe more
formally the system developed whatever they are. This need arises from several different considerations such as:

* the robotic systems under development are more and more complex and only one person is not able
  to understand in detail the sub systems that it is composed of. To provide models instead of
  code is a way to simplify the presentation allowing someone of the team to understand the
  big picture when working the details of his / her proper module;
* It is very difficult to the brick of impossible to understand complex behaviours 
  when dealing directly with code in languages that can be very exotic to the 
  common developer. To present a unified and standardised view of these behaviours
  allows for outsiders to understand more easily the top view and even details of the robot or robots systems
  presented;
* Complex robot systems ask when developed to group many different people with many
  different skills (servoing, architectures, simulation, electromagnetism, vision and so on and so forth).
  There is a need to decouple the development activity as these different skills are so different
  it is not possible for any of them to understand all the other activities. Such a modelling approach
  helps to do exactly that;
* For the time being there are no standardised way to present algorithms to other and thus to allow them
  to be sold without a specific ad hoc contractual approach. :term:`ROS` is a first attempt to implement
  such a capability but it remains at an academic level and not independant from the platform or :term:`OS`
  on which this algorithm will work. In other word, there is a need of such a standard to allow the emergence
  of an actual "parts for robots" market.

In order to answer the need demonstrated above a project (see :term:`PROTEUS`) allowed to create a modelling language
and other associated toolings which this documentation is foccussing on. Thus
:term:`RobotML` is a language associated to a platform linked to :term:`PAPYRUS` tool and build
upon :term:`ECLIPSE` framework. The goal of this language is to answer the above problematics and thus to ease development of
robotics application and to facilitate exchanges between roboticians and
end-users. 

,,,,,,   

:term:`RobotML` documentation is decomposed in many parts. 
A presentation of its rationale is done in its introduction, 
then, instructions are provided in order to install the platform
followed by some hints of how to use it through some examples.
The following sections are providing in-depth information on the underlying language
(the so-called meta-model), the different choices done in order to present the user modelling capabilities
and finally the different generators add-ons with example of use.
The last section is dedicated to the web :term:`portal`
and its interactions with the :term:`RobotML` platform.

The last bit of important information is that each time it is necessary,
the documentation will separate the :term:`user` point of view from the :term:`developper` one
trying to limit the amount of knowledge to what is strictly deemed necessary.

.. toctree::
   :maxdepth: 1

   Introduction to RobotML <IntroductionToRobotML/index.rst>
   RobotML Platform Installation <RobotMLPlatformInstallation/index.rst>
   How to Use the RobotML Platform <HowToUseRobotML/index.rst>
   RobotML Meta-model <RobotMLMetamodel/index.rst>
   RobotML Modeling Platform <RobotMLModelingPlatform/index.rst>
   RobotML Code Generators <RobotMLCodeGenerators/index.rst>
   RobotML Community Web portal <RobotMLWebPortal/index.rst>

More information on RobotML are available through its
dedicated portal that is accessible directly following
`<http://rim.bourges.univ-orleans.fr/>`_ .

.. warning::
   Documentation is written solely in English due to lack of resources that would have allowed at least a French version. The reason for this choice is the importance of dissemination and cooperation at the European Level (see projects such as :term:`BRICS`\ ).

.. _I_DHT:

Documentation How-to
====================

The documentation you are reading has been generated using the sphinx tool.
It is a part of the development in itself and here follows tho sections that explicits 
how to install the sphinx tool, where to find its associated documentation and
provides a list of known bugs and frequently asked questions. 

.. toctree::
   :maxdepth: 1
   
   Sphinx and documentation <DocumentationHowTo/SphinxAndProteusDocumentation>
   Bugs and questions <DocumentationHowTo/BugsAndQuestions>

.. _I_IT:  

Indices and tables
==================

* :ref:`G`
* :ref:`genindex`
* :ref:`search`

.. _I_LW:

Related websites
================

Hereafter a list ow websites considered relevant for this documentation. The reader will find here much more information on the

* :term:`RobotML` Modeller: websites related to the modelling problematic
   * `eclipse <http://www.eclipse.org/modeling/>`_
   * `papyrus <https://www.eclipse.org/papyrus/>`_

* Robotics and modelling: websites illustrating use of modelling in the robotics domain
   * `RIM <http://europe.bourges.univ-orleans.fr/>`_ : website dedicated to Robotic Models sharing and hosted by :term:`PRISME` laboratory
   * `BRICS <http://www.best-of-robotics.org/>`_ : An european project someway on the same lines :term`PROTEUS` porject was.
   * `Smartsoft <http://www.servicerobotik-ulm.de/drupal/>`_ : Christian Schlegel developed under the auspices of `Hochschule Ulm <http://www.hs-ulm.de/>`_ a tooling close to the effort underway in :term:`RobotML` tooling


* Robotics middleware: list 
   * :term:`OROCOS`
   * :term:`RTMaps`
   * :term:`ARROCAM`