###Feature

* Begins all cucumber files although it doesn't do too much
* Basically there for documentation to outline what is going on below
* The feature name goes on the same line as the `Feature:` declaration
* The remainder is its description

###Scenario

* Behavior defined in all scenarios, added up define what the feature is
* Most features will contain between 5-20 scenarios
* All scenarios follow the same pattern
  1. Get the system into a particular state.
  1. Poke it (or tickle it, or ...).
  1. Examine the new state.
* Has a name line like the feature and can (not normal) have multiple description lines

###Given, When, Then

* Used to describe different parts of the scenario

###And, but

* Used to add more steps to each Given, When or Then

###*

* Used to replace all of the Given, When, Then, And, But keywords.
* Doesn't read as easily but I can see how it could be useful in places where speed is needed