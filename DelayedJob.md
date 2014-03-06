##Notes

* Invoking new workers is as easy as `Delayed::Worker.new()`
  * You can then pass jobs into this with `worker.run(job)`
  * these will run immediately.
  * Handy if you have to run a bunch of jobs.

###Methods

* `invoke_job`: will start the job from the console immedimmediately
  * `payload_object.perform` will also do the same thing but, is more terse
