###Notes

* Adding cool features that do not make app more productive is a classic pitfall
* Write tests, build stuff, no fluff
* This chapter and it's tests are just 1/3 of the overall test suites and tools needed

###Behavior Driven Design/Dev

* Software fails because projects are late or customers don't know what they want or over budget, or hard to maintain
* The above problems are easily trumped with the Agile Lifecycle because everyone is involved continuously
* Maintain a working prototype with working revisions
* The word behavior is because you ask about behavior of app (small parts) during development
* Done with user stories through a kanban or 3/5 card system
* Written in [connextra format][1]
* 3/5 cards are easy and nonthreatening therefore all stakeholders can brainstorm
* Real systems have 100s of features
* _Backlog_: a collection of User Stories not yet implemented

###User Stories

* All user stories should be `SMART`
* Specific, Measurable, Achievable, Relevant(Business whys), Timeboxed(Know when to give up)
* Each scenario __should__ be testable
* Adjectives used: Given, When, Then (we know this already)
* Estimate what's achievable using velocity
* Each story assigned and estimate of points (3 point scale) based on difficulty
* Velocity == Points completed per iteration
* Always ask "Why" in a recursive manner until the business value is discovered or ultimately killed ([5 why's][2])

###Cucumber and Capybara

* Cucumber tests customer understandable user stories
* Cucumber meets halfway and the developer
* 1 Feature per User Story + 1 or more Scenario and an unlimited amount of features (dev wants to keep it small)
* _User Story_ refers to a single _feature_
* _Featire_ is 1 or more _scenarios_ that show different ways a feature is used
* _Scenario_ is 3-8 _steps_ that describe the overall function of the scenario
* 5 Keywords provided: Given/When/Then/And/But
* Match steps with step definitions with Regexes
* Cucumber colors the steps depending on passing(green)/not yet implemented(yellow)/failing(red)

###Capybara

* Simulates a browser and to interact with app
* Cannot handle javascript(Webdriver can) but remains very fast

###User Interface Design

* User stories need User Interfaces
* Want all stakeholders involved in UI design
* Need UI equivalents of 3x5 cards
* _Sketches_: pen and paper drawing or "Lo-Fi UI"
* Storyboards show how UI changes based on user actions
* Next step is HAML and CSS so we can make it pretty _after_ it works

###Imperative VS Declarative

* _Imperative_: Initial user stories usually have lots of steps, specifying logical sequences that gets to desired results
* _Declarative_: much fewer steps
* Basically this boils down to Declarative steps reuse a lot of older steps and phrases, reducing the need to write out each and every step

[1]: /ConnextraFormat
[2]: http://www.agilejourneyman.com/2011/08/5-whys-putting-fun-back-into-your.html