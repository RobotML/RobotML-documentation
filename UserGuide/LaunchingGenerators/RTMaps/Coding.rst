Integrating your own code
========================================================

In order to add life to this application, it becomes necessary to write C++ code 
inside the generated leaf-components, which means inside the generated .h and .cpp files.

In order to make sure that the user-specific code inserted inside files that have been generated 
automatically will not be overwritten or erased with the next generation operation, any line 
of user-specific code has to be written in ``use code`` sections, identified by special comments: ::

	// 	Start of user code [subject]
	... user code ...
	// 	End of user code

Several sections have been foreseen in the generator for the user to write his own code.
Let's have a quick overview of the different available sections:

	* Additional include files:
	  Need to introduce external C or C++ libraries? Include additional header files in the .h files of the corresponding components: ::
	
		#include "YouthChallengeModel/YouthChallengeModel_datatypes_all.h"
		#include "proteus/maps_proteus_datatype_filters.h"
		#include "YouthChallengeModel/YouthChallengeModel_datatype_filters.h"
		#include "maps.hpp"

		// Start of user code Additional includes
		#include "my_api.hpp"
		// End of user code

	* Overlaoded MAPSComponent methods:
	  Need to write code inside special methods of the parent MAPSComponent class (overload the component constructor, 
	  react to a property value change, create inputs/outputs/properties dynamically, etc...) . Declare those overloaded 
	  methods in the .h file in the class declaration: ::
	
		class MAPSAmer_Loc : public MAPSComponent
		{
			// Use standard header definition macro
			MAPS_COMPONENT_STANDARD_HEADER_CODE(MAPSAmer_Loc)
		// 	Start of user code Overloaded methods declarations (Dynamic, Set...)
			void Dynamic();
			void Set(MAPSProperty& p, MAPSInt64 value);
		// 	End of user code
		private :
		...		

	* Need to declare additional member variables and methods to your component class? 
	  In the component .h file, use section at the end of the class declaration: ::

		// 	Start of user code Additional members and methods
		// 	End of user code
		};
		
	* Several similar sections are available as well in the .cpp file for the component implementation: 
	  additional include files, additional inputs/outputs/properties definitions, implementation of optional 
	  overloaded methods of MAPSComponent declaread in the header file, and also
	
		* Initialization code at the end of the Birth() method: ::
	
			// 	Start of user code User-specific initalizations
			// 	End of user code
			
		* Common execution code to call each time a sample has been received 
		  on an input port, at the end of the Core() method: ::
		
			// 	Start of user code Core processing
			// 	End of user code
			
		* Code to execute each time a sample is received on a specific input port: 
		  inside callbacks called from the Core() method. For instance: ::
		
				//This callback will be called each time a new sample is received on the corresponding input port.
				void MAPSAmer_Loc::Amer_Relative_Received_on_amer_relative_InPort(Amer_Relative* data_in, int count, MAPSTimestamp t)
				{
				//	Start of user code Processing code for samples received on Amer_Relative
				//	End of user code
				}
				
		* Code to execute in order to emit data samples on output ports: inside generated methods to call 
		  from elsewhere (from Core() or from data sample reception callbacks). For instance: ::

			//To be completed by programmer, then called by programmer whenever necessary in order to
			//output a data sample on output port amer
			void MAPSAmer_Loc::Output_amer(MAPSTimestamp t)
			{
				MAPSIOElt* ioeltout = StartWriting(Output("amer"));

			// 	Start of user code Output on amer implementation
				int count_Amer_out = 1; 	//changed it to the number of samples to write in output MAPSIOElt 
														//(but never more than the max vector size allocated on the output).
				Amer* data_out = (Amer*)ioeltout->Data();

				//Fill in data_out here.
				//....

				ioeltout->VectorSize() =  count_Amer_out * sizeof(Amer); //For non-standard datatypes, by convention,  
			//	End of user code

				ioeltout->Timestamp() = t;	
				StopWriting(ioeltout);
			}
				
		* Termination code to execute at the end of the diagram execution : inside the Death() method. ::
		
			void MAPSAmer_Loc::Death()
			{
			// 	Start of user code Death implementation
			// 	End of user code

			}

