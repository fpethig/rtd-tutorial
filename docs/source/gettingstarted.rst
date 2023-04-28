Getting Started
===============
*AASPortal* is a mono-repository project. It is implemented using the npm workspaces concept. The project consists of three packages:
-aas-portal: The browser app of *AASPortal*.
-aas-server: The Node.js server app of *AASPortal*.
-common: Types and functions used by aas-portal and aas-server.

.. autosummary::
   :toctree: generated

Prerequisites
-------------
* Visual Studio Code
* Node.js v18.10.0
* Angular 15.2.x
* GIT 2.36.0.windows.1
* Docker

aasportal
  ├── projects
  │     ├── aas-portal
  │     │     └── package.json
  │     ├── aas-server
  │     │     └── package.json
  │     └── common
  │          └── package.json
  └── package.json

## 1.2. Setup Visual Studio Code
The preferred development environment is Visual Studio Code.
Clone the [*aasportal*](git@gitlab.cc-asp.fraunhofer.de:iosb-ina-big-data-plattformen/aasportal.git) GIT repository. Open *aasportal* in Visual Studio Code. In a terminal window execute the the following commands:

    > npm install

and

    > npm run build -ws

restart Visual Studio Code.

## 1.3. Start AASPortal
The following command creates and executes a composed Docker image:

    > npm run start

Open one of the supported web browsers and go to the Web site:

    http://localhost/

Alternatively, the application can be started by specifying an Asset Administration Shell:

    http://localhost/?id='value'

`value` can be the AAS identification:

> http://localhost/?id=http://boschrexroth.com/shells/0608842005/917004878

the identification base64URL encoded

> http://localhost/?id=aHR0cDovL2Jvc2NocmV4cm90aC5jb20vc2hlbGxzLzA2MDg4NDIwMDUvOTE3MDA0ODc4

or the name (idShort) of the AAS

> http://localhost/?id=Bosch_NexoPistolGripNutrunner
