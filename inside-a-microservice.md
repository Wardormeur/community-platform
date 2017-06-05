## Inside a microservice

We use senecajs as a framework \(senecajs.org\) for all our plugins.

The only exception to the following is cp-zen as it's both containing our front-end and serving it, but still does the link through hapijs to the microservices

service.js/index.js

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

* entities : CRUD actions only available to the local controllers
  * should not contain any logic
* controllers:  external acts available to any other microservice /zen
  * as they can be exposed through cp-zen/hapijs, they should be validated and have permissions set
    * on newer structure of our microservices, permissions and validation are grouped together with the act itself
    * on older ones, permissions are on /config and validation is only covered by HapiJs

/tests : unit-test

/tests/e2e : contains the microservice for loading testdata for this microservice

/config : contains the microservice configuration, including

* the port on which the microservice is running, 
* the postgres params,
* the mailing params



## Regarding zen-platform

Server-side : 

It handles 

