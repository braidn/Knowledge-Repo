# Micro Services

## Notes

* Only one rule:
  * If a service is too complex it needs to be broken into smaller ones.

## Acronyms (because they all suck)

* AMQP or Advanced Message Queuing Protocol

## Pillars

* Decomposability
  * A smattering of loosly coupled services
  * Each service should only run the required functions to satisfy the services' context.
* Autonomous
  * Each service should be runable without any other service.
  * Any changes to one service shouldn't affect any others.
  * This let's each service evolve naturally.
* Scalable
  * Any kind of scaling should be doable (horizontal and vertical).
  * This often times means that service discovery is required.
  * Router and DNS approach are the most common implementations here. 
* Communicable
  * Must be able to converse, usually over HTTP.
  * However, items like Protobufs are another way that communication can occur.

## Communication

* Several ways that services can talk or communicate with one another:
  * RPI (Remote Procedural Invocation)
    * Thing gRPC for Google or GitHub
    * These often times have no middle broker so very simple/easy to maintain.
  * Message Bus
    * Inter process communication protocol, usually async in manner.
    * Think Rabbit MQ/Apache Kafka here.
    * These are often times highly available because the broker persists the message
        and decouples clients completely from service discovery.
  * Protobufs
    * Designed as a way to serialize data and a communication protocol.
    * These are somewhat new so there isn't a ton of information on them.
    * Since info is sent in binary, debugging can be somewhat tricky.

## Service Discovery

* How in a world of containerization does a client discover the location of a service instance?
  * Service Registry
    * Central space to register the location of services.
    * Many times these receive constant communication (GET/POST) to keep a map of known services.
  * Server Side Discovery
    * All requests are routed through a central hub, usually a load balancer.
    * A request of maintained registry is then passed back.
    * Decouples the client from needing to know the whearabouts of the services.
    * Load balancers can be single points of failures.
  * Client Side Discovery
    * Client handles the network location of services and load balances as required.
    * Usually these are still stored in a central DB of sorts.
    * THe load balancing 'pattern' is usually some algorithym to decide on where the request will go.
    * While these are simple, if a polyglot microservce exists, 
        then each language needs to re-create the load balancing.

## Data Management

* How will data persistence be structrured across services?
  * Database Per Service
    * Keeps data private to each service, exposable only through APIs.
    * Different services require different DB's, this allows each to choose.
    * This doesn't have to be a whole DB per service.
        Perhaps it's on a per schema basis, or a per table pool basis.
    * Queries across multiple data stores can be complex/expensive.

## Sharing Concerns

* Any new service should have the ability to pick up a shared environment.
* This could mean sharing logging, service registries, or any other 3rd party item.
* Logging is one of the most common shared concerns.

## Design Patterns

* Everything has a pattern, there are even a few in the microservice world.
  * Aync Messaging
    * The idea here is to maintain reliable and consistent state throughout the whole app.
    * Think message busses/RabbitMQ.
    * Pub/Sub allows a model to receive an event and send a message to all subscribers.
    * Message based commands here are more powerful than HTTP (synchronous)
    * If there are heavy DB ops, this pattern sometimes breaks down due to more synchronous events.
  * Backend For Frontends
    * Microservices across a bunch of different interfaces.
    * At its' heart it's about creating separate backends per interface (Mobile/Web).
    * Each 'backend' can maintain itself and handle its' own responsibility.
    * These 'backends' only contain interface specific code, code sharing is the only path to sanity.
    * This optimizes each interface with little disruption between interfaces.
