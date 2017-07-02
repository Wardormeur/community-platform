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

/config: contains the microservice configuration, including

* the port on which the microservice is running, 
* the postgres params,
* the mailing params
* other env variables \(integrations\)
* permissions for acts when they are exposed through Hapijs

## Ongoing migrations

/lib: contains all the logic

* entities : CRUD actions only available to the local controllers
  * should not contain any logic
    * allows us to swap database  easily
* controllers:  external acts available to any other microservice /zen
  * as they can be exposed through cp-zen/hapijs, they should be validated and have permissions set
    * permissions, validation and tests are grouped on the same folder than their act

/test:

* this directory doesn't exist anymore as every act has its own tests along with its code, its permissions and its validation

## Regarding zen-platform

/lib : contains all the api endpoints and their definition

* **ongoing**: separation of validation from the endpoint to allow reuse of definition
* **ongoing**: missing validations of api calls

/web/index: entrypoint

* loader of plugins, config, api endpoints.

/web/controllers:  serves the index

* define exceptions to our SPA
  * embedded
  * open-graph
  * routes for directives template
  * ...

/web/config:

* statically defined api responses
  * programming languages
  * languages
* config for
  * caching
  * plugins
    * i18n
    * dustjs

/web/public:  Angular1 front-end

* **ongoing migration** : unless it's a bugfix, please use [cp-zen-front-end](https://github.com/CoderDojo/cp-zen-frontend/tree/staging) instead



