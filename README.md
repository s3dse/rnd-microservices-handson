# rnd-microservices-handson

RnD Day: Microservices Hands-On

# Goals

- experience core principles of Microservices architecture
  - isolated runtimes
  - Java & Spring Boot technology stack
  - persistence with JPA
  - exposes synchronous REST/JSON endpoints
  - consumes external synchronous REST/JSON endpoints
  - sends asynchronous events over message bus
  - receives asynchronous events over message bus

# Use Case

This project contains a collection of four microservices
based on spring-boot, communicating via REST and AMQP.
The "start-group-delivery" and "start-group-bakery"
branches contain the starting points for implementing
two services. The "ref" branch contains the reference
implementations. Avoid peeking here without trying yourself
first. :-)

The folder pizza-service-intro/index.html contains a presentation that gives an overview of the application.

The exercise branches "start-group-delivery" and "start-group-bakery" contain a presentation explaining the tasks (delivery/exercise-instructions/index.html or bakery/exercise-instructions/).

# Run the solution

We dockerized our microservices and you can use docker-compose to run the solution.

You need to install [docker](http://docs.docker.com/mac/started/) and [docker-compose](https://docs.docker.com/compose/install/). If you are not on linux you also need [docker-machine](https://docs.docker.com/machine/install-machine/).


Start the event bus:
```
infrastructure/start.sh
```

Start the microservices:
```
./service.sh
```

In order to point the ui to the correct backend you might need to change the following lines to point to your docker ip in the docker-compose.yml
```
- CATALOG_API_BACKEND_HOST=http://192.168.99.100:8081
- ORDER_API_BACKEND_HOST=http://192.168.99.100:8082
```


