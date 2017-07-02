## Inside a microservice

We use senecajs as a framework \(senecajs.org\) for all our plugins.

The only exception to the following is cp-zen as it's both containing our front-end and serving it, but still does the link through hapijs to the microservices

## Current

service.js or index.js

* loader for local seneca instance
  * set up external plugins
    * database
    * logging
    * ..
  * import custom plugins \(depending on the microservice\)
    * dojos
    * users
    * events

/lib : contains all the logic

* Each file is the logic for one act

/tests :

* "unit" test
* often, &lt;serviceName&gt;-test.specs.js contains all the tests, into one unique file

/tests/e2e : contains the microservice for loading testdata for this microservice

/config: 

* contains env variables
* permissions for acts when they are exposed through Hapijs

## On going migration

/lib: contains all the logic

* entities : CRUD actions only available to the local controllers
  * should not contain any logic
    * allows us to swap database  easily
* controllers:  external acts available to any other microservice /zen
  * as they can be exposed through cp-zen/hapijs, they should be validated and have permissions set
    * permissions and validation are grouped on the same folder than their act

/test:

* this directory doesn't exist anymore as every act has its own tests along with its code, its permissions and its validation

/config : contains the microservice configuration, including

* the port on which the microservice is running, 
* the postgres params,
* the mailing params

## Regarding zen-platform

Server-side :

It handles

