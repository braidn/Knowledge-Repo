* built with a `Threads.new` block.
* gotcha: print, because it creates a new line builds the thread and the newline as separate threads.
  * if another thread starts before the newline is written it stomps out the puts action
  * use `print \n` to get around this little issue.
* `Thread.list` will bounce back a list of running threads
* building timing dependencies into a multithreaded app is considered some SERIOUS bad form
  * overly complex
  * prevents the thread compiler from doing its optimized thang.
* RubyMutex are used to control access to specific resources.