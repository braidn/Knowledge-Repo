###Notes

* Unexpected short-lived code is considered an epic failure
* Waterfall design process is considered "Big Design Up Front"
  * Done in different phases with different groups dealing with each group
  * Hardware is done in this model
    * this is probably the reason why software began with this model
  * Works well for:
    * Software with specs that never change.
  * Big problem is that you build one version AND then you realize how to build the real program
* Agile model:
  * Customer collaboration over contract negotiation
  * Individual and interactions over processes & tools
  * Working software over comprehensive documentation
  * Responsive to change over following a plan
  * Continuous improvements over phases
  * TDD based design
  * [Velocity][1] to measure team progress
* Rails has a strong tie to Agile development model

###Testing

* Unit Testing: 1st level (Lowest), single method does what was expected
* Module or Functional: across individual units
* Integration: Interface between units have consisten assumptions, communicate correctly
* System or Acceptance: 4th level (Highest), integrated program meets its spec
* Coverage: % of code tested
* Big part of Agile, test before code is written

###Formal Methods

* Proofs that program follows behavior of the specs
* Search all possible methods
* Expensive, and usually not done unless

###Productivity

* _4 Techniques_:
  * Clarity via conciseness
    * Syntax: shorter and easier to read
    * [Raise level of abstraction][2]
  * Synthesis
    * BitBlt: generate code to fit situations
    * Programing by example
  * Reuse
    * Reuse old code vs write new code
    * Standardized libraries
    * Procedures and functions
    * Object oriented programing
    * [Design patterns][3]
  * Automation and Tools
    * Replace tedious tasks with automation
    * Must repeatedly learn how to use new tools (be a better developer)

###DRY

* Don't Repeat Yourself
* Don't copy and paste code
* Definite part of Productivity

### Software as a Service (SAAS)

* No installs to worry about with the OS
* No worries about data loss
* Easy to groups to interact with data
* If data is large or changed frequently, it is simple to keep 1 copy
* The 1 copy leads to less compatibility hazards
* 1 copy simplifies upgrades

###Service Oriented Architecture

* All components are designed to be services
* Modular and easy to repair mistakes
* All communications go through an api

###Cloud Computing

* Clusters are more scalable than traditional server
* VMs simplify ops
* Warehouse Scale comps refers to the economies at scale
* Traditional Datacenters utilize only 10-20%
* Watson cost roughly 200$ per hour

###Pitfalls/Fallacies

* Adding people to a software project doesn't add to productivity
  * Reduce what you do to speed things up



[1]: https://en.wikipedia.org/wiki/Velocity_(software_development)
[2]: https://en.wikipedia.org/wiki/Abstraction_(computer_science)
[3]: https://en.wikipedia.org/wiki/Design_pattern_(computer_science)