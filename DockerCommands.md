# Handy Docker Commands

* When a container has it's tty exposed, it's easy to attach to it:
  * `docker attach name_of_container`
  * to detach use `ctrl p + ctrl q`
  * This is great when dealing with binding.pry/byebug execution.