# Our microservices/repositories

![](/assets/Untitled Diagram.png)

* Zen-platform :

  * It contains both our server as well as our angular front-end 
    * a new front-end, called [cp-zen-frontend](https://github.com/CoderDojo/cp-zen-frontend/tree/staging) is to be packaged as a on-going separation and rewrite from cp-zen-platform
      * hence do not work on cp-zen for its front-end part unless it's a quick bugfix;
      * instead write new with vueJs our friendly front-end :\)

* User service :

  * It contains anything from the authentication to the PI of users
    * users \(authentication/system info\)
    * profiles \(PI\)
    * agreements
    * LMS integration

* Dojo service :

  * It contains anything linked to a dojo:
    * dojo
    * user-dojo relationship
    * dojo leads

* Event service

  * Anything linked to events
    * event
    * ticket
    * session \(a regroupement of tickets\)
    * application \(a ticket ordered\)

* Badge service

  * Badge system integration



