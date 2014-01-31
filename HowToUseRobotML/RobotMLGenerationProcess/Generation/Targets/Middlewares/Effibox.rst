Effibox
=======

.. toctree::
   :maxdepth: 3

TODO mise en forme

Generation RobotML to Effibox

Effibox generated application

The generator creates a complete Effibox application containing:
- subscriptions to the sensors used in the modeling
- all model classes assigned to the middleware
- standard datatypes and custom datatypes
Below is an example of a generated application tree:

.. figure:: Effibox_images/tree.png
   :width: 300px
   :align: center
 
In the "src" directory are placed all the c + + source files:
 -. RoboCabApplication * pp is the main class
- Data structures (standard and custom) are stored in a subdirectory Datatypes
 - The components of the model are stored in a subdirectory Software

Correspondence between the model and the generated code:
Components:
Component "RobotML" is translating as a C++ class. The elements of the component are declared as class attributes:
- Instance of each sub-component
- Input ports
- Outputs ports
- Internal and external connections between components
- State machines and transitions

Ports:

Output Ports:

Each output port is translated by an Effibox communication object named TaskBuffer.
In this object is assigned to one or more processing functions.
Each time data is added to TaskBuffer (push method), all associated processing functions are executed in parallel.

Input port :
An input port is translated as a method of the class corresponding to the component.
This method can be associated with an output port as a processing function.
Then, it's automatically called when an event is transmitted by the output port connected.

Connections:
Internal:
Within a macro-component, several sub-components may have their input/output ports / interconnected.
The connection is simply an association with an input port and an output port, thanks to addFunctionToExecute method in TaskBuffer class (see output port).

Example :
//inner components connexions
pathPlanner.pathDef->addFunctionToExecute(boost::bind(&LocalisationModule::pathDefIn, &localisation, _1));

External:
In a macro-component, an external connection is a connection between an input of an internal component and an input of the macro-component,
or between an output of an internal component and an output of the macro-component.
 - An external connection "input-input" is translated by encoding the input port of the macro-component as a method that calls the method corresponding to the input port of the subcomponent.
 - An external connection "output-output" is translated by encoding the output port of the macro-component as a pointer to the input port of the internal component.

State Machines :
State names are translate into a structure enum. Transitions are implemented as methods. If a method has already a c++ content in modeling, this content is copied.

Limits :
- Only the contents of c++ transition functions are copied. If the content is written in another language, it will be ignored.
- The change of state is currently not implemented correctly.

Datatypes :
- RobotML datatypes: the RobotML datatypes are converted into C++ structures using standard C + + language. Thus there may be differences between the datatypes and datatypes modeling after translation.
- User datatypes: the user-defined datatypes are built the same way, based on the RobotML translate datatypes.

External algorithms:
Not supported by the generator for the moment.

Port Service
Not supported by the generator for the moment.

Deployment plan :
- All components containing the following stereotypes are generated as a sensor subscription: CameraSystem, GPSSystem, InertialMeasurementUnitSystem, InertialNavigationSystem, OdometrySystem, Robot (see next paragraph).
- All components allocated on the platform are generated as an Effibox component, whatever their stereotype.

Sensor connections:
The sensor connections are translated as Effibox subscriptions.
They are stored in the xml file describing the Effibox application .awp file.
Processing functions associated with the sensors are encoded in the main application class. In each function, Effibox types are converted to RoboML type. Here dataflows are connected to inputs of instantiated components.

To make the sensor data connections to your RobotML components works properly, you must respect some contraints into the model:
- A RobotML IMU sensor must transmit the datatype Imu in an output dataflow.
- A RobotML Gps sensor must transmit the datatype NavSatFix in an output dataflow.
- A RobotML Camera sensor must transmit the datatype Image in an output dataflow.
- A RobotML Lidar sensor must transmit the datatype LidarScan in an output dataflow.
- A RobotML Odometry sensor must transmit the datatype CarLikeOdometry (Vipalab for example) or DifferentialOdometry (wifibot for example) in an output dataflow.

