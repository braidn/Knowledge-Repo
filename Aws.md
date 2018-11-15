# Amazon Web Services

## Notes

* Aka, one of the worst built dashboards ever.

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
