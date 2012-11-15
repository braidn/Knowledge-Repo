###Details

* Instead of specifying your data directly, you build a blueprint that will construct your slice of data
* Three really popular gems in order:
  1. Factory Girl
  1. Machinist
  1. FixtureReplacement
* Using dynamic content is allowed by passing a block to the db value
  * Ex: `start_date { Date.today }`
  * In addition, you can reference previous fields in blocks as well
* Strive to create as little data with factories as needed
  * If compared 1:1, factories are a little slower than [fixtures][1]

###In Tests

* Assign a var to a `Factory.create(:factoryName, :modifiedAttribute => "Value")`
  * Any valid attribute can be passed into the hash after the factory name
  * Also can be written as `Factory(:factoryName)`
  * Or assign itself to an instance var in a setup block

###Sequencing (Building Unique Things)

* [Sequence Example][0]
* Can be referred to explicitly by calling `Factory.next(:sequenceName)` on any atribute
  * This can be __completely__ negated if the attribute name matches the sequence name

###Associations

* Associations want to be done from the `belong_to` side of the association as much as possible
* Written like: `association :attributeName, :factory => :factoryName, :overidingValue => "Stuff"`
* When calling the factory and you __don't__ want/need the association, call `nil` on it



[0]: /RailsTestFactoriesSequenceExample
[1]: /RailsTestFixtures