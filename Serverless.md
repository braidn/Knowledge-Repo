# Serverless Architecture

## Notes

* A natural progression to serverless can be thought of as:
  * SOA -> [Microservices][ms] -> serverless
  * Although serverless architecture is a descendant of microservices, 
      it doesn't need to maintain the baggage that microservices has 
      (namely service discovery)
* Often times Lambdas are though of having two different architectures:
  1. Compute as Backend where the lambda acts like a backend for some frontend.
  1. Compute as Glue where the lambda is a pipeline to carry out workflows.
* Getting the right granularity for functions is a particular skill that needs to be developed.
  * Functions should do the bare minimum but if they too little they are hard to debug.
  * Minimizing the amount of data transformations will also help keep granularity manageable.
* Attempt/strive to reduce the number of steps a system takes to perform an action
* DB's also have to be super fast in a Serverless architecture.
* Event driven micro-services is a great medium to build into Serverless functions/applications.

## Principles

1. Use a compute service to execute code on demand
1. Write single purpose (stateless functions)
1. Design push based, event driven pipelines
1. Create thicker and thicker frontends
1. Embrace third parties

## Patterns

* _Command Pattern_ is common in FAS style of development
  * A central lambda acts like an orchestrator for more functions.
  * Drastically simplifies the work of the API Gateway (often time a single function/access point).
  * Decouples the caller from the receiver.
  * Reduce coupling by allowing the client to be parameterized in the request.
  * Think a single GraphQL endpoint that fires off new lambdas, requests, etc.
* _Messaging Pattern_ is something more common in distributed systems.
  * All events/requests/records are encoded into some kind of queue.
  * Highly resilient to fault due to everything being recorded in a queue.
  * When servers come back online, they just pick up wherever the queue is.
  * Amazon SQS is a perfect place to build a queue of this type.
  * Kinesis Streams are also a good use case for queuing.
* _Fan Out Pattern_ is another popular way to accomplish event driven architecture.
  * It works with a messaging/subscriptions channel.
  * When some message is added to the channel, all subscribers to the channel are notified.
  * This makes it perfect for when parallel work is required.
* _Pipes and Filters_ is a pattern used to decompose complex tasks.
  * Think of pipes like unix pipes.
  * Often times used to work with complex data or video.
  * Perfect for any task that has multiple steps to get to a particular result.

## Testing

* If the serverless functions are running in lambda, the run-local-lambda package can invoke handlers with event data.
  * This is handy because its' output can be asserted on (ala Jest/Mocha/Testing frameworks)

## Authentication

* It's pretty common here to use some type of JSON Web Tokens or delegation tokens for this.

## Nomenclature

* Tier: Module boundary between major components in a system.
  * data, presentation, application, etc.
* Layer: Much smaller slices that carry out specific parts of an application.

[ms]: /Microservices
