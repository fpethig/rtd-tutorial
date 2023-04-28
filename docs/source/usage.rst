Usage
=====
Filter AAS Collection
---------------------
Display AAS in which a certain search text occurs. The search refers to the name, the identification and the endpoint type of the AAS.

A search within the structure of an AAS is started if the search text begins with a :cobj-text:`#`. It is possible to search for a specific model type with a specific name and, depending on the model type, a specific value. The search text has the following format:

.. code-block:: console

   #<abbreviation>:<idShort>[=, !=, <, <=, >=, >]<value>
 
.. code-block:: console
 
   #<abbreviation>:<idShort>=<min>...<max>

.. code-block:: none
   :caption: Supported model types

   | Abbreviation | Model Type                   |
   | ------------ | ---------------------------- |
   | AAS          | Asset Administration Shell   |
   | Asset        | Asset                        |
   | Cap          | Capability                   |
   | CD           | Concept Description          |
   | DE           | DataElement                  |
   | DST          | DataSpecification Template   |
   | InOut        | inoutputVariable             |
   | In           | inputVariable                |
   | Id           | Identifier/id                |
   | Prop         | Property                     |
   | MLP          | MultiLanguageProperty        |
   | Range        | Range                        |
   | Ent          | Entity                       |
   | Evt          | Event                        |
   | File         | File                         |
   | Blob         | Blob                         |
   | Opr          | Operation                    |
   | Out          | outputVariable               |
   | Qfr          | Qualifier                    |
   | Ref          | ReferenceElement             |
   | Rel          | RelationshipElement          |
   | RelA         | AnnotatedRelationshipElement |
   | SM           | Submodel                     |
   | SMC          | SubmodelElementCollection    |
   | SME          | SubmodelElement              |
   | View         | View                         |

By using the logical operators :kbd:`||` and :kbd:`&&` several expressions can be combined in the search text.

Examples
--------

All AAS that contain at least one operation element:

.. code-block:: console

   #Opr

All AAS that contain at least one submodel with the name :cobj-text:`Nameplate`:

.. code-block:: console

   #SM:Nameplate

All AAS that contain at least one property with the value :cobj-text:`SmartFactoryOWL`:

.. code-block:: console

   #Prop=SmartFactoryOWL

All AAS that contain at least one property with the name :cobj-text:`Producer` and the value :cobj-text:`SmartFactoryOWL`:

.. code-block:: console

   #Prop:producer=SmartFactoryOWL

All AAS where :cobj-text:`RotationSpeed` is greater or equal then :cobj-text:`5000`:

.. code-block:: console

   #Prop=RotationSpeed >= 5000

All AAS where :cobj-text:`ProductionDate` is between :cobj-text:`12/24/2022` and :cobj-text:`12/31/2022`:

.. code-block:: console

   #Prop=ProductionDate = 12/24/2022...12/31/2022

Endpoints
---------
Known endpoints:

.. code-block:: json
   :caption: Supported Endpoints

   {
       "endpoints": [
           {
               "name": "KI-Reallabor",
               "type": "AasxServer",
               "address": "http://153.97.102.163:51310"
           },
           {
               "name": "AASX Server",
               "type": "AasxServer",
               "address": "http://172.16.160.171:51310"
           },
           {
               "name": "AAS Registry",
               "type": "AASRegistry",
               "address": "http://172.16.160.188:50000/registry/api/v1/registry/"
           },
           {
               "name": "I4AAS Server",
               "address": "opc.tcp://172.16.160.178:30001/I4AASServer"
           },
           {
               "name": "I4AAS DzDemonstrator Server",
               "address": "opc.tcp://172.16.160.171:30001/I4AASDzDemonstratorServer/"
           },
           {
               "name": "Samples",
               "address": "file:///samples"
           }
       ]
   }
