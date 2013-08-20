* Splitting a word into an array to do something with it is fairly
common
  * `%q(WordOfTheDay).split(//)`
* Finding the longest word in array
  * `%w{Some array}.max-by(&:length)`
* Sort array by longest
  * `%w(some array).sort_by(&:length)`
  * This will output from smallest to biggest. Pass a `.reverse` and you
  should be golden.
* Select items from an array
  * this is easily done with `.select` and then passing the value into
  a regex like: `x =~ /[aeiou]/`
  * Anything that passes is true will be passed back out into an array
* Squashing repetitive values from an array
  * Ruby makes this easy with the `.uniq` method for every Array
* Build a random name or string:
	* `('a'..'z').to_a.sample(5).join`
* Assign two variables together using map
	* `var1, var2 = 2.times.map { something }`
	* times would need to be set to how many vars needed being set

