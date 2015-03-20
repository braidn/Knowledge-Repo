# Background Jobs

* Sometimes called queueing in an application.

## Ruby

* 3 top contenders has been Sidekiq/Resque/Dj.
* Sidekiq uses threads over processes forking like Resque.
* Sidekiq and Resque utilize Redis.
* Sidekiq hinges on Redis and once it fails, it loses everything.
* [Shoryuken][1] and [SQS][2] seems to be a very durable option.

[1]: https://github.com/phstc/shoryuken
[2]: https://aws.amazon.com/sqs/?tag=vig-20