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

By using the logical operators `||` and `&&` several expressions can be combined in the search text.

**Examples**

> All AAS that contain at least one operation element:
>
> `#Opr`

> All AAS that contain at least one submodel with the name 'Nameplate':
>
> `#SM:Nameplate`

> All AAS that contain at least one property with the value 'SmartFactory OWL':
>
> `#Prop=SmartFactory OWL`

> All AAS that contain at least one property with the name 'Producer' and the value 'SmartFactory OWL':
>
> `#Prop:producer=SmartFactory OWL`

> All AAS where 'RotationSpeed' is greater or equal then 5000:
>
> `#Prop=RotationSpeed >= 5000`

> All AAS where 'ProductionDate' is from 12/24/2022 until 12/31/2022:
>
> `#Prop=ProductionDate = 12/24/2022...12/31/2022`

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
