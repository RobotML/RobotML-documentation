Compiling the necessary packages
========================================================

RTMaps runs code in components which are actually instances of C++ classes. Now such components code has been generated, it is time to compile it
into a shared library which can then be dynamically loaded in the RTMaps environment. They are called *packages* of components.

In order to compile the package containing the generated components, proceed as follows:

	* Under Windows:
		
		* Open the ``maps_sdk_vc2005.sln`` in Visual C++ 2005. The solution contains a project called ``rtmaps_[modelname]``
		* Switch the current configuration to *Release* instead of *Debug*
		* Build the project
		
.. figure:: images/visual_project.png
   :align: center
   :alt: The generated project for Visual C++ 2005.
   
   The generated project for Visual C++ 2005.

   
.. figure:: images/visual_compilation.png
   :align: center
   :alt: The compilation result in Visual C++.
   
   The compilation result in Visual C++.

	* Under Linux:
		
		* Open a terminal
		* From path ``.../rtmaps-generated-files/user_sdk/[modelname].u/``, type ``make``

		
.. figure:: images/make_terminal.png
   :align: center
   :alt: Compilation under Linux.
   
   Compilation under Linux.

   
This creates a file called ``rtmaps_[modelname].pck`` in folder ``rtmaps-generated-files\user_sdk\packages\[linux_x86]``.
		
