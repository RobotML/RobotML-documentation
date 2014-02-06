VLE RobotML Generator
---------------------

About
^^^^^

The Virtual Laboratory Environment :term:`VLE` is a multi-modeling and simulation platform. It is a powerful modeler and simulator supporting the use of different formalisms for models specification and simulation.
:term:`VLE` is particularly well adapted for complex models where the coupling of different formalisms is required. In addition to the classical use of one single formalism for modeling and simulation, :term:`VLE` can integrate, i.e. couple, heterogeneous formalisms in one coherent simulation model.

For instance, :term:`VLE` supports, and is not limited to, the modeling and simulation of the following formalisms (stand alone or coupled together):

* Discrete Event Specifications
* Differential equations
* Difference equations
* Petri net
* Finite State Automata

:term:`VLE` supports the following modeling and simulation paradigms:

* System Dynamics
* Multi-Agent Systems, Multi-Agent Simulation
* Decision support systems
* Learning systems

:term:`VLE` is based on the theory of modeling and simulation initially developed by B.P. Zeigler in the 70's and continuously enriched until now by an active international community.
:term:`VLE` is based on the :term:`DEVS` formalism (Discrete Event systems Specification). :term:`VLE` provides a set of C++ libraries, the :term:`VFL` and a lot of programs like a simulator, a graphical user interface to model and develop models and tools to analyze and visualize simulation outputs. The :term:`VFL` are sufficiently well designed to allow the development of new simulators, models or new programs for modeling and analysis.

:term:`VLE`'s goals is to provide powerful tools for modeling, simulating and analysing complex dynamics systems. The development are complying with the :term`DEVS` specification DEVS and works made by the simulation community. 

.. seealso:: `VLE official website <http://www.vle-project.org>`_

.. _DEVSModels:

DEVS models
^^^^^^^^^^^

=============== ===================================================================================================================================
 Name            Description
=============== ===================================================================================================================================
 Passive         DEVS model which makes nothing, which reacts to no external event and which generates no ouput-event.
 Counter         Very simple model which counts the number of events received on all the input-ports of the model. No output-event is produced.
 Conditional     Model may require parameters that are expressed in condition form.
 Generator       Generates an event every X time units (x can be a parameter).
 Storage         Replicate the input to output with a lag. If an input is present before the replication to output, so this input is ignored
 Binary Counter  Send "1" if two "1" is received within a period.
 Sampling        Replicate with a frequency the last input.
=============== ===================================================================================================================================

 
See :ref:`RobotML VLE integration<RobotMLVLEIntegration>` to know the implementation specificities.