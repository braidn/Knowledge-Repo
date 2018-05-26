# Single Responsibility

##[Notes][1]

* If a change occurs and a class contains > 1 responsibility then there
will be more than one reason for it to change
* This is also known as being coupled
  * When the responsibilities change they will likely negatively affect
  the other responsibility
* The idea really stretches to "Decoupling two or more interfaces"
  * There will likely be instances where there is a small amount of
  "glue" holding things together. 
  * This coupling is a tradeoff and must be taken into consideration at any time of a project.

### Cohesion

* Really this is minimizing how much communication occurs across components/classes/etc.
* Talking about the size of an object's public API layer and minimizing it is in preserving cohesion.

[1]: http://www.objectmentor.com/resources/articles/srp.pdf
