The generated folder tree content
========================================================

The result of the generation resides in a new folder called ``rtmaps-generated-files`` in the same folder as the model files.


.. figure:: images/generated_content.png
   :align: center
   :alt: The generated files.
   
At the root of the generated folder is the main RTMaps  diagram (.rtd file) for the execution of the generated model.
It cannot be opened yet as it requires a package file (.pck) which has to be compiled from the generated RTMaps components source codes.

	* Folder ``macro_components``: contains RTMaps macro-components files (.rtmc) which are actually "sub-diagrams", i.e. higher-level components which contain other components.
	* Folder ``user_sdk`` contains the necessary source codes and project files (or makefile) for the RTMaps leaf components included in the model. In this folder is the Solution files (.sln) for Visual C++ 2005 (for use under Windows only of course).
	
		* Folder ``include`` contains data types definitions in C++ language for the RobotML meta-model data types and the model-specific data types (i.e. data types defined inside the model).
		* Folder ``[modelname].u`` contains the source codes for the leaf components to be compiled and run in the model.
			
			* ``makefile``: Makefile for compiling the package with gcc under Linux
			* ``rtmaps_[modelname].vcproj``: project files for Visual C++ 2005
			* ``[modelname].pckinfo``: text file with meta package information (version number, short description).
			* Folder ``local_interfaces`` contains the header files for the RTMaps components classes.
			* Folder ``src`` contains the implementation .cpp files for the RTMaps components classes.
   