# Background Jobs

* Sometimes called queueing in an application.

## Ruby

* 3 top contenders has been Sidekiq/Resque/Dj.
* Sidekiq uses threads over processes forking like Resque.
* Sidekiq and Resque utilize Redis.
* Sidekiq hinges on Redis and once it fails, it loses everything.
* Shoryuken and SQS seems to be a very durable option.