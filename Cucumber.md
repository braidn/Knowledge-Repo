Way to build a scenario in human readable language when using [outside in development][5]. Best served with large [Capybara Dsl][1] like rodents

* To install a skeleton in a rails project: `rails g cucumber:install`
* This also creates several handy rake tasks that can be seen by `rake -T`
* Consist of three parts: Title, Brief Narrative, any amount of Scenarios
* Anything above the `Scenario` declaration is just documentation and considered a `Feature:` block
* Anything below it are steps in the specific scenario
* Each step begins with 5 possible [keywords][4]: `Given, When, Then, And, But`
* In many instances considered integration tests.
* All matches are returned as a String based variable.
* Before each scenario is run Cucumber creates a new object named World
* step definitions execute in the context of World just like methods of the World object
* Before any steps are run, Cucumber loads all files from features/support
* if an env.rb file exists in this dir it will be the VERY first file to be loaded

###Objects

* Best to use [Factory_girl][3]
* make sure the files from the factories dir (or wherever) is being loaded into the factories.rb file in the support section of Cucumber
* an [example][2]
* This works because all files in features/support get loaded prior to cucumber running its tests
* Instance variables are available in all steps once defined in one step.

###Flags

* `--dry-run`: parses the .feature file without execution, will show any errors in the Gherkin

###Tags

* Tags can be used to define scenarios or whole features with `@tagname`
* multiple tags are allowed
* Cucumber can run just a certain set of tags 
* Way easier than defining all your features with folders.

[1]: /CapybaraDsl
[2]: /FactoryGirlCucumberEnvironment
[3]: /FactoryGirlCucumberEnvironment
[4]: /CucumberKeywords
[5]: /OutsideInDevelopment