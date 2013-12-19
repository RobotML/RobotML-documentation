Limitations and perspectives
========================================================

At this day, several limitations are to be known between what can be possibly modeled in RobotML 
and what is effectively generated in RTMaps. The most important ones follow:

	* RobotML "service ports" are not supported in RTMaps.
	* In RTMaps, only leaf-components can embed executable code (i.e. components which don't contain 
	  other components in a lower hierarchy level). Higher-level components are called "macro-components" 
	  in RTMaps and are just containers of lower-lever architecture diagrams. They don't have their own 
	  implementation. When starting the execution of an application, it is possible to imagine that the 
	  whole diagram would be "flattened" which means all the higher-lever components would be removed 
	  and replaced by their content, and this recursively. In the end, only leaf-components would then 
	  remain on the diagram. 
	* The "deployment" part is not implemented yet: in future versions, the objective is to add a "deployment" 
	  step between the model definition and the generation step. 
	
		* In this deployment phase, it will be possible to specify target-specific parameters that are 
		  not accessible in the RobotML meta-model, for instance, concerning RTMaps the reader strategies 
		  of components (FIFO reader, Last or Next reader, Sampling reader...) and the synchronization 
		  strategies for components with multiple inputs (Asynchronous arrival on any input, Triggered by   
		  first input, Resampling on all inputs, Synchronized reading on several inputs...)
		* Also this deployment phase will allow to choose, for each component defined in the model if the 
		  generator should create C++ source code for empty-shell components in RTMaps (to be completed by   
		  the C++ programmer) or to map onto pre-existing components or macro-components available in RTMaps.
		
	* Generation of code for execution of FSMs that would be defined in the model is not supported yet.
	* It would be interesting in a further future to consider the possibility to perform reverse model 
	  transformations, which would mean, in our case, the possibility to build new diagrams in RTMaps with 
	  existing components or user-programmed components, then generate the corresponding RobotML model to be 
	  exploited inside the RobotML modeling platform.
	
	

