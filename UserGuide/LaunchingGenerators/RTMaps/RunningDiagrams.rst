Running the generated diagrams
========================================================

In order to run the generated RTMaps diagrams, proceed as follows:

	* Start RTMaps 4 (under Linux, type 'rtmaps' in a terminal).
	* Open the generated diagram called ``[modelname].rtd``
	* Eventually re-organize the layout of the diagram (the components have been placed aumotically by the generator without so much intelligence).
	
.. figure:: images/diagram.png
   :align: center
   :alt: The generated RTMaps diagram in the Studio.
   
   The generated RTMaps diagram in the Studio.

At this point, if you start the application, nothing very interesting will occur as the
components we have compiled and that will run in the diagram are just empty shells (no 
algorithms have been generated nor data acquisition code or control code).

The next chapter will present how to integrate your own code inside the generated components, 
and in future versions, how to map components from the model directly to pre-existing components 
from the RTMaps libraries.