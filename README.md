# Twutter


## Technologies / Libraries

- AngularJS
- Bootstrap
- wepback

- node.js
- Koa
- Seneca
- Passport

- Bluebird
- Lodash
- JWT


## Personal Libraries Used

I also make use of some of my own libraries, available on npm: 

- config-layered
- alt-user-seneca
- alt-auth-seneca

Alt-user-seneca and alt-auth-seneca comprise a Koa, Passport and Seneca based 
authentication and authorisation skeleton framework that uses JWTs for auth
rather than session cookies.


## Architecture

jwt_serv splits the authentication and user management aspects into microservices based on Seneca. In contrast to Seneca's official seneca-auth and seneca-user,
the microservices are each split into two parts - the service itself, that communicates only via JSON through Seneca, and a Koa adapter that provides the
requisite routes to Koa and communicates via JSON only with Seneca. This means that, during development, it is straightforward to have all of the services
launched in a single app, but it is trivial to split out the auth and user services separately so that the system as a whole can be flexibly architected.
