# Handy Docker Commands

* When a container has it's tty exposed, it's easy to attach to it:
  * `docker attach name_of_container`
  * to detach use `ctrl p + ctrl q`
  * This is great when dealing with binding.pry/byebug execution.
* When shit's getting out of hand space wise (Docker's usurping all of it):
  * `docker system prune`
  * This command has some output/user interaction so it won't be run accidentally.

## Ruby

* When running an container with a volume, using bundle exec is highly recommended for all commands.
  * ex: `docker-compose run --rm web bundle exec ruby ...`