OROCOS ROBOTML Generator
------------------------


OROCOS middleware (Open Robot Control Software)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

OROCOS is a real-time component-based framework, also called OROCOS-RTT (Real-Time Toolkit) for its real-time aspects. OROCOS components interact by exchanging data, events or services through ports. Data exchange is performed through input/output data flow ports. Services are implemented as Interface operations. OROCOS allows also the definition of components behaviors as state machines using the package rFSM.

OROCOS Code Generator
^^^^^^^^^^^^^^^^^^^^^

OROCOS code generator implements model to text transformations using Acceleo.
Transformation rules link RobotML concepts (which gather the DSL architecture, the DSL control and the DSL communication) to OROCOS concepts. The code is available here https://github.com/RobotML/RobotML-SDK/tree/master/robotml-kepler/generators/OROCOS
The OROCOS code generator takes input from a RobotML model and provides: 
* OROCOS components (hpp, cpp files).
* Interfaces (hpp files) which define a set of abstract operations.
* Data Structures (.hpp files) representing user defined data types.
* a configuration file (OROCOS Program Script: OPS file) to configurate communication between components.
* RTT-LUA components (lua files) which load the state machines describing the behavior of components 
* LUA state machines (lua files) implemented using the rFSM package where states, transitions, events, effects and guard are explicitly specified.

OROCOS generator aims at providing an executable application. To do so, a set of artifacts are also generated:
- A makefile
- A Cmakelists.txt where the components to be loaded are specified.
- A manifest.xml file which specifies which libraries has to be imported.
