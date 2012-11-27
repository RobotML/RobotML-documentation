.. _Annex:

Annex
=====

.. note:: All code in this are writen on Alf.

List of enumeration for the scenario ATK
----------------------------------------
 
.. code-block:: c++

   enum NetworkID {
      INVALID_NETWORK(0),
      IFDL(20001),
      LBWDL(20002),
      HBWDL(20003),
       TCAS(20004)
   }
   
   enum SensorType {
      INVALID_SENSOR_TYPE(0),
      MAW(1),
      ESM(2),
      RDR(3),
      SAR(4),
      EOIR(5)
   }
   
   enum SensorFunction {
      INVALID_SENSOR_FUNCTION(0),
      IMAGE(1),
      SEQUENCE_OF_IMAGE(2),
      SEARCH_AND_TRACK(3)
   }
   
   enum EquipementType {
      PLATFORM(0),
      EQP_COMMS(1)
   }

List of composed datatypes for the scenario ATK
-----------------------------------------------

.. code-block:: c++

   datatype SensorDefinition {
      public type : SensorType;
      public workWithEntities : Logical
      public workWithEntitiesTypes : longs
      public technos : SensorTechnos
      public useLineOfSight : logical
      public fieldOfRegard : SensorAngularBounds
      public fieldofView : SensorAngularDelta
      public intervisitype : Long
      public resolution : Vector3
      public toBeAcquireDuration : Long
      public tobeLostDuration : Long
      public canBeJammed : Logical
      public historyLenght : Long
      public isEmitter : Logica 
      public id : Long
   }

.. TODO
   liste des datatypes composé
   
List of the external librairy's functions
-----------------------------------------

.. code-block:: c++

   public <<Algorithm>> function initRadarStep(in time : Long, in timestep : Long, in NID : long)

.. TODO
   liste des fonctions externes
   
List of the processing
----------------------

.. code-block:: c++
   public function_body initRadarStep() { return time == 0; }

.. TODO
   liste des processings
   
List of the components
----------------------

.. code-block:: c++

   public class Aircraft : Model
   {
      public <<dataflowport>> port in time : Long
      private property SID : Long
   }
     
.. TODO
   Liste des composants