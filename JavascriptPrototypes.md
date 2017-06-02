#Javascript Prototypes

##Notes

* All objects in JS contain a __proto__ member/property.
  * it's sole purpose is to act like a method missing bank.
  * If a property can't be found on an object (ala `object.property`),
    * it's looked up in __proto__ by calling `object.__proto__.property`
  * This lookup is recurssive in the sense it continues to add new __proto__ onto each lookup.
    * second lookup example: `object.__proto__.__proto__.property`
  * This is done until a __proto__ returns a `null`.
* All of this magic allows for inheritance when creating new instances of classes.
  * ex: `function Animal() {}; Animal.prototype.walk => { console.log('walking') }`
  * could be be inereted from using:
  * ex: `function Bird() {}; Bird.__proto__.Animal.prototype; Bird.prototype.fly => { console.log('flying') }`
