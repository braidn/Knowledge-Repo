##Notes

* Example of two or more parameters:
  * `task :my_task, [:first_param, :second_param] => :environment do |t, args|`
* Execute from another task
  * `Rake::Task["your_task"].execute({:some_param => some_value})`
