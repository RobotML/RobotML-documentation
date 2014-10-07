.. _UG_TUTO:

Tutorial
========

To use :term:`RobotML` tools, nothing is better than an concret case. In this tutrial we go to purpose a scenary, and we go to get a solution at this scenary. Next anothers persons could purpose anothers solutions for this scenary.

Purpose the scenary
"""""""""""""""""""

.. info:
   You should to have your RobotML web site identifiant to purpose your scenary at the community
   
For our tutorial, we would to modelize a little autonomous car.

Purpose a solution
""""""""""""""""""

Now we have purpose our scenary, we go resolve it. After had install the :term:`RobotML` platform, launch itand create a new workspace.
Two way exist to modelize the solution:

* First, create a :term:`RobotML` project including all necessary modelization's components.But component can not be reused for anothers model, it's boring. 
* Second, create some :term:`RobotML` project, someone contain all component of a defined perimeter. This solution permit modelization's capitalization with with importing *Components* project in the *hosting* project.

In our tutorial, we going to use the second method. We will go to define 4 project:

* The datatypes,
* The base components,
* The systems,
* The environment.

The Datatypes
*************

After a quick reflection, we can define the information that our car need:

* Time,
* Speed,
* Position,
* Destination,
* Commands (run, break, reverse, turn leftt, turn right).

*Time* will be define by *Long* datatype, *Speed* with the datatype *Real*, *Position* and *Destination* with the datatype *Position*. The *Commands* will be define by an enumeration.
First create a new :term:`RobotML` project. So in the *Project explorer* view, do a right clic with the mouse and select **New ...**. Select **RobotML project** in the dialog, and named the project as *CarAuto_Types*. Show the :term:`RobotML` perspective.
Now we go to create a new datatype. In the *Model explorer* select the main package, and do right clic with the mouse. Select **Add diagram...**, and create a new *Datatype diagram*. Select the *Datatype component* from the *Component menu* on the right of the screen, and drag it on the created diagram. Name it *Real*.Repeat the operation to create the types *Long* and *Position*.
We go to define an enumeration to declare our car's commands. In the *component menu* select the enumeration component, and drag it on the datatypes diagram. Named this enumeration as *Commands*. Now we go to add the enumeration's values. Select the enumération, and in the *Owned literal* section from the *Property* view, clic on the *Add* button. A dialog to create an enumerate is showing. Named this enumerate as *Run* and put his type as *Long*. Repeat the operation for another enumerate (break, reverse, turn left, turn right).

Well our datatypes project is done. Now go to define the base components.


The base components
*******************
For a car be autonomous, we can imagine it need a propulsive system, naviagtion system, and a mind.
This section objective, is to define the components to build the different car's system. We going to declare:

* 4 engine (more simple in our example),
* 1 GPS,
* 1 cartography module,

First create a new :term:`RobotML` project as name *CarAuto_components*. Then create a new *Component diagram* in this project.
In the *Component menu* select the *Component* tool and drag it on the diagram to create a new component. Named it as "Base". Select the "Base" component in the *Model explorer* and do right clic with the mouse. Add a new *State machine* child. Create a new *State machine diagram*, and design the :term:`FSM` as the following:
Initial state => Init => Running => Final state

Now return on the *Component diagram* and add a new component. Named it as "Engine". Repeat the operation for the others comonent (*GPS*, and *Cartography module*). Next create a new *Class diagram*, and drag all component created on it. With the *Generalization tool* link the components *Engine*, *GPS*, and *Cartography module* with the *Base* component. Now all component inherit of the *Base* component's :term:`FSM`.    
 
We have defined our base components to build our car's system. Let go to build it!

The systems
***********

 Our car is composed by 3 systems : 
 
 * Navigation
 * Propulsive
 * Logic unity
 
 Create a new :term:`RobotML`project as name *CarAuto_Systems*. Next create a new *Component diagram*, create 3 new components (*Navigation*, *Propulsive*, and *Logic unity*). In the *Model explorer* select the root model and import the *CarAuto_comonents* model. Drag the components *GPS* and *Cartography module* in the *Navigation* system. Repeat the operation with the *Engine* comonent but drag it on the *Propulsive* system.
 
 In the *Component diagram*, create the new component named "Car", drag on it the following system :
 
 * Naviagtion
 * Propulsive
 * Logic unity
 
 Right! Now we have building our car!
 
The environment
***************

Last step, we should to declare an environment. Our car need an environment to evolve.

Create a new :term:`RobotML` projct as name *CarAuto_Environment*. Next create a new *Component diagram* add create a new component and named it *Environment*. Select the *Environment* comonent and show his properties. In the *Profil* tab, apply it the *Environment* Stereotype. Then import the *CarAuto_Systems* model, and drag on it the *Car* component.

Ok we have create our problem solution, but it is not functionnal!!! Systems should communicate to work!!!

Components communication
""""""""""""""""""""""""
  
 
  