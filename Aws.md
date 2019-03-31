# Amazon Web Services

## Notes

* Aka, one of the worst built dashboards ever.

## Lambda

* Supports two different invocation types.
  * Events (usually from somewhere in Amazon services)
  * RequestResponse (usually from the SDK or Api Gateway)
* Also supports both push (event pushed from a service) and 
    pull (polling) event methods
* All Lambdas execute in some kind of container or jail.
  * When a function fires for the first time, the container is built, thereby cold starting
  * However, if a function is rerun within a period of time, it may use the same container (warm)
  * Juggling warm and cold starts is key to performant handlers.
* There is also the same concept of warm/cold with background processes.
  * These however, are called 'freeze/thaw' cycles.
  * Where if a process was backgrounded, it may finish invocation when the container is reused.
* There are many ways to improve function invocation time (keeping things warm)
  * Scheduling perodic events to keep the handler warm.
  * Increase overall memory allocated to the handler.
  * Move all initialization and setup code out of the handler.
* Handlers are passed an event object on invocation.
  * this object contains query string params, headers, etc.
* Caching can be done at the API Gateway level.
  * cacheing can be done on URL params, query strings, whatever.
  * Like most caching though, there is a good amount of tweaking to get things right here.

### Programming

* All handlers are passed an event, a context and a callback.
* Events are JSON blobs containing information about the caller.
* Context is information about the current Lambda. 
  * How long it's been running, memory, identity if using Cognito
* The callback is optional and used to return information to the caller.
  * This method takes two params: an error (or null) and a response (usually a string)
* Lambdas themselves can be versioned. 
  * Really just means that the previous version still works but, can't be modified.
  * Usually invoked using the version number after the name: nameOfFunc:2 
* Aliases are nameing queues that map to functions and their versions.
  * This makes dealing with dev/staging/prod a breeze.
  * All sources can point to an alias versus a hard coded version.
* Environment variables and encrypted environment are a possibility as well when building handlers.
  * These variables are even available in procces.env if using NodeJS.

## Testing

* Keeping code decoupled from Lambda and unit tested is the best way forward. 
* However there are ways to test IN AWS how a lambda will run.
  * There is a lambda-test-harness blueprint that will test other lambda handlers.
  * Any output will be saved in a Dynamo DB table.
  * Both Unit and Load testing is doable through this test harness.

## IAM

* Used to identify a server, application or human.
* Users who are created as credentials for an application are called 'service accounts'
* There is actually a cap of 5k to all accounts (liftable)
* All policies (managed and inline) are built using JSON
  * fucking huzzah...

## Authentication

* If building an application, [Cognito][cog] is an option for authorization.
  * another alternative here would be [Auth0][au0]
* Cognito can verify requests at the Gateway level.
  * This would prevent the subsequent Lambda from running if auth didn't pass.
  * When a user auths with cognito they are provided temporary IAM credentials.
  * In addition, the service can persist end user data.
* The API Gateway can use Lambda functions to authorize requests.
  * these are called 'custom authorizers'.
  * They run during the method request phase, before the request hits the backend.
  * At its' heart it uses a bearer token (header) and validates it against an IAM policy
* These custom authorizers end up being Lambda funcs that validate JWTs.

## Resources

* Specifies what an AWS product can do or have access to.
  * Example here would be to allow SNS to communicate to an S3 bucket.
* Not all of AWS products support resource policies (it's a small list)
* Resource based policies are always inline (versus managed)

## Logging and Alerting

* CloudWatch manages both of these actions under one 'product'
* At the beginning of a project, 
    mostly logs will be used to diagnose errors in Lambda logic.
* CloudTrail is a service that records API calls
  * Effective at debugging who is using an AWS service, and logs of the use.
* As long as a Lambda service is using a solid logging framework, 
    Lambda will record logs effectively in CloudWatch
* CloudWatch automatically saves logs indefinitely.
  * it's on the developer to scope when and how they are thrown away.
* Filters can be created to sift through logs at much easier rate.
* Because this is Amazon, S3 logs are separate from CloudWatch

## Development

* The platform makes environment variables available in process.env
  * and in other environment settings for other languages.
  * these can be encrypted with Amazon's Key Management Service.
  * These variables are set on a per function basis.

## Books

* _AWS in Action_ Manning, 2016

[cog]: https://aws.amazon.com/cognito
[au0]: https://auth0.com/
