Mapping between modeling concepts and RTMaps code
========================================================

This chapter will describe more in details how RobotML meta-model concepts are generated 
towards RTMaps concepts, objects and mechanisms.

Data types, input and output ports
-----------------------------------

The RobotML meta-model defines a set of data types, mostly mapped from the ROS data types, that can 
be used to characterize objects that will be exchanged via data-flow or service ports.
The RobotML meta-model also allows the user to define his own specific data types.

The RTMaps generator transforms this datatypes definitions into C++ types and classes in a generic way.

	* Primitive datatypes
	Primitive datatypes are mapped directly to existing dataypes in C++, sometimes via 
	RTMaps-specific "typedefs" as some datatypes declarations may differ from one platform to 
	another. See generated file maps_proteus_primitive_datatypes.h". ::
	
		#include "maps_types.h"

		/**************************************/
		/* PRIMITIVE DATA TYPES */
		/**************************************/
		typedef bool Bool;
		typedef MAPSUInt8 Byte;
		typedef MAPSUInt8 Char;
		typedef MAPSInt8 Int8;
		typedef MAPSUInt8 UInt8;
		typedef MAPSInt16 Int16;
		typedef MAPSUInt16 UInt16;
		typedef MAPSInt32 Int32;
		typedef MAPSUInt32 UInt32;
		typedef MAPSInt64 Int64;
		typedef MAPSUInt64 UInt64;
		typedef MAPSFloat32 Float32;
		typedef MAPSFloat64 Float64;
		typedef std::string String;

		typedef MAPSTimestamp 	Time;
		typedef MAPSDelay 		Duration;
		...
	
	* Composed datatypes
	Composed datatypes are datatypes based on collections of primitive datatypes or association of different 
	sets of primitive datatypes, or even made of other composed datatypes. The RTMaps generator uses dynamic 
	templates from the STL such as std::vector to generated the corresponding C++ classes. Example:
	Generated file ``Header.h`` for the composed datatype ``Header``: ::
	
		class Header {
			public:
			UInt32 seq;
			Time stamp;
			String frame_id;
		};
		
	Generated file ``Image.h`` for the composed datatype ``Image``: ::
	
		#include "robotml/Header.h"

		class Image {
			public:
			Header header;
			UInt32 height;
			UInt32 width;
			String encoding;
			UInt8 is_bigendian;
			UInt32 step;
			std::vector<UInt8> data;
		};

As the content of these objects often has to be dynamically allocated or re-allocated, and often differs 
significantly from standard RTMaps datatypes, the RobotML generator defines custom RTMaps dataypes for 
each RobotML datatype definition.

A custom RTMaps datatype consists in the datatype class, the class name, and the definition of an input 
port filter, defined to accept connections from output ports with such or such type. For instance, the 
definition of the input filter for the Image datatype as define in RobotML is the following: ::

	// The RTMaps input filter for the structure Image
	const MAPSTypeFilterBase MAPSFilterImage = MAPS_FILTER_USER_STRUCTURE(Image);
	
This way, RTMaps output ports are defined as follows: ::

	MAPS_OUTPUT_USER_STRUCTURES_VECTOR("video",Image, 0)
	
and RTMaps input ports are defined as follows: ::

	MAPS_INPUT("video",MAPSFilterImage,MAPS::FifoReader)
	
As the content of classes may have to be dynamically allocated and re-allocated at runtime, 
the generator needs to implement the most generic way to do so in RTMaps: allocate a pointer 
in each slot of the standard RTMaps output buffers, and let the user (or the generated code) 
allocate the memory (and release it!) whenever necessary.

In the Birth method, an ugly bunch of code (the user may not need to understand nor modify it) 
goes through each output buffer slot, and allocates dynamically an object with the right datatype. 
All these will be released in the ``FreeBuffers`` method, called at diagram execution shutdown, 
once all the components on the diagram have stopped.

In ``Birth``: ::
	
	_amer_relative_buffers.Clear();
	MAPSIOMonitor &monitor_amer_relative=Output(0).Monitor();
	MAPSFastIOHandle it_amer_relative;
	it_amer_relative=monitor_amer_relative.InitBegin();
	while (it_amer_relative) {
		MAPSIOElt &IOElt_amer_relative=monitor_amer_relative[it_amer_relative];
		IOElt_amer_relative.Data() = (void*) new Amer_Relative[1]; //TODO: replace 1 by port.upper.
		if (IOElt_amer_relative.Data() == NULL)
			Error("Not enough memory.");
		_amer_relative_buffers.Append((Amer_Relative*)IOElt_amer_relative.Data());
		monitor_amer_relative.InitNext(it_amer_relative);
	}

In ``FreeBuffers``: ::

	//Let's release the memory we allocated on the output buffers.
	MAPSListIterator it_amer_relative;
	MAPSForallItems(it_amer_relative,_amer_relative_buffers) {
		delete [] _amer_relative_buffers[it_amer_relative ];
	}
	_amer_relative_buffers.Clear();
	
Components and components hierarchy
------------------------------------

A RobotML model is made of components which can themselves be made of components, which can themselves 
be made of... components, etc.

The model does not make any difference between a component which contains other components and a 
leaf-component (i.e. a component which does not contain any lower level component) - a component 
which contains other component can embed a behaviour for itself -. RTMaps does.

In RTMaps, only leaf-components can embed executable code. Components which contain other components 
are just defined by the components they contain and how they are connected together.
So, at this day (generator V1.1), a leaf component in the model will be generated to a 
RTMaps component code skeleton (a header .h and an implementation .cpp file).

Whereas a higher-level component in the model will be generated to a RTMaps "macro-component" (an .rtmc file), 
which is actually an XML file containing a sub-diagram with "input aliases" and "output aliases" which are 
the exported input and output ports of the macro-component, to be connected at the higher-level.

.. figure:: images/P2_proximetry_model.png
   :align: center
   :alt: A high-level component (P2_Proximetry) as defined in RobotML.
   
   A high-level component (P2_Proximetry) as defined in RobotML.

.. figure:: images/P2_proximetry_rtmaps.png
   :align: center
   :alt: The same high-level component as generated for RTMaps
   
   The same high-level component as generated for RTMaps
   
.. figure:: images/Amer_Identif_model.png
   :align: center
   :alt: The "Amer_Identif" leaf-component as defined in RobotML
   
   The "Amer_Identif" leaf-component as defined in RobotML
   
becomes ::

	maps_Amer_Identif.h
	maps_Amer_Identif.cpp
	
which after compilation become a component in an RTMaps package: 

.. figure:: images/Amer_Identif_pck.png
   :align: center
   :alt: The "Amer_Identif" leaf-component as an RTMaps component.
   
   The "Amer_Identif" leaf-component as an RTMaps component.
   
Data exchange mechanisms
------------------------

In RTMaps, several exchanges strategies are available between components as components often execute 
in parallel, in different threads.

A component can retrieve data on its inputs in a blocking or non-blocking manner, using the output buffer 
it is connected to as a FIFO buffer or LIFO buffer, etc.

A component with several inputs can be wake-up and execute its tasks following different classical 
patterns such as:

	* asynchronous arrival of a data sample on any of the inputs: the component will be notified 
	  as soon as a data sample arrives on any of its input, it can the retrieve the sample and execute code.
	* Triggered: the component will be notified when a data sample arrives on its first input, then 
	  it will read data available on the other inputs in a non-blocking manner (resampling).
	* Resampling: the component will read data on all its inputs in a non-blocking manner. It will 
	  then be synchronized by something else, like a software timer for instance.
	* Synchronized: the component will be notified when data samples that have been acquired at the 
	  same time are available on all of its inputs (and not data samples that are made available 
	  at the same time to the component inputs): this is useful for data fusion algorithms where 
	  it is necessary to process data that has been measured at the same time, whatever the latencies 
	  induces by the different processing channels on the different tracks. This way, it is 
	  possible to resynchronize the different data streams downstream the diagram, whatever the 
	  intermediate latencies.

In the RobotML meta-model, such mechanisms cannot be specified. They are specific to RTMaps. 
The objective for future versions is to provide a way to specify those mechanisms in the "deployment" 
phase, between model definition phase and code generation phase, once the generation target has 
been chosen and the PROTEUS tools can propose a way to specify target-specific parameters.

For now however, the generator implements the most generic way by default: the component is 
notified each time a new sample is made available on any of its inputs. Appropriate callbacks 
are called from the generated Core() method, allowing the programmer to include its own code 
upon data sample reception events.

From that behaviour, the programmer may be able (provided that he implements the necessary 
internal buffers, data samples storage and so on...)  to re-implement all the other mechanisms, 
even if this would certainly be very tedious.

This is done via a "multiple  StartReading" call in the Core method on all the available inputs: ::

	int input_that_answered;
	MAPSIOElt* ioelt_in = StartReading(_nb_inputs, _inputs, 	&input_that_answered);
	if (ioelt_in == NULL)
		return;

	MAPSTimestamp timestamp_in = ioelt_in->Timestamp();

	switch (input_that_answered) {
		case 0: //We received an element from port laser_scan.
			{
			int count = ioelt_in->VectorSize() / sizeof(LaserScan);
			LaserScan* data_in = (LaserScan*)ioelt_in->Data();
			LaserScan_Received_on_laser_scan_InPort(data_in,count, 				ioelt_in->Timestamp());			
			} 
			break;
		case 1: //We received an element from port proxy_left_right.
			{
			int count = ioelt_in->VectorSize() / sizeof(Proxi_Left_Right);
			Proxi_Left_Right* data_in = (Proxi_Left_Right*)ioelt_in-				>Data();
															Proxi_Left_Right_Received_on_proxy_left_right_InPort(data_in,count, 		ioelt_in->Timestamp());			
			} 
			break;
		default:
			Error("Unknown input.");	
	}
	// 	Start of user code Core processing
	// 	End of user code




	  
   




   

