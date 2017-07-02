# Common actions

## Searching an endpoint

Our swagger documentation : [https://zen.coderdojo.com/documentation](https://zen.coderdojo.com/documentation)

## Consuming an endpoint

```
curl 'http://localhost:8000/api/2.0/dojos'
```

## Consuming an act

If you didn't expose your function through HapiJs \(because it's back-end only\), you can still call it through the microservice directly

```
curl -d '{"role": "cd-dojos", "cmd":"load", "id": 1}' http://localhost:10301/act
```

The role parameter describe the microservice targeted. The port number is mapped to the same microservice and declared per microservice.

The cmd parameter is the name of the function under which it has been registred.

You'll often find in the newest microservice that the act follows a new pattern, adding "entity" or "ctrl" parameter. This allows us to differenciate CRUD actions \(private\) from exposed actions.

## Adding a route

In cp-zen, find a /lib/{entityName}.js file. It should contain all the API route definition

## Adding an url

In Angular1, open /web/js/init-master.js and add your configuration here.

## 



