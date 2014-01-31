MORSE RobotML Generator
-----------------------

MORSE Simulator
^^^^^^^^^^^^^^^

MORSE is a robotic simulation software developed by roboticists from several research laboratories (including GREYC). It is a framework to evaluate robotic algorithms and their integration in complex environments, modeled with the Blender 3D real-time engine which brings realistic rendering and physics simulation. The simulations can be specified at various levels of abstraction. This enables researchers to focus on their field of interest, that can range from processing low-level sensor data to the integration of a complete team of robots.

Building and configuration of scenarios are done with a set of Python classes provided by MORSE, known as the Builder API. The Builder API provides an internal domain-specific language (DSL) that completely hides the somewhat complex interface of Blender from the user, so that those unfamiliar with Blender can directly configure MORSE using Python scripts.
Scripts can then be tracked on a version control system to follow changes and apply patches.

The API offers classes to add robots, sensors and actuators, to position, rename and configure any of the parameters used by these components, to include additional objects (furniture, obstacles, etc.) and to add middleware bindings, modifiers and services for each component.

MORSE Generator
^^^^^^^^^^^^^^^

The MORSE generator transforms RobotML models into a suitable Python script using the MORSE Builder API. The code is available here: https://github.com/RobotML/RobotML-SDK-Juno/tree/master/plugins/generators/MORSE
The algorithm of the MORSE generator is basically a visitor on a RobotML model where RobotML stereotype that represent a sensors or actuators are mapped on a Python class. At the moment, only the AirOARP sensors are completely supported. This included the following prototypes: CameraSystem, GPSSystem, LIDARSystem.
