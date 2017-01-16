# Angular 2

[[_TOC_]]

## Notes

* The `@` connotation above a class, is for annotations.
  * These usually take an object that outlines information for the class.
  * Two that are particularly important are `Component` and `Template`
* Constructor functions often times ask Angular to instantiates the dependencies and types.
  * This is actually not dependency injection but IoC(Inversion of Control)
* Each component has it's own scope over the previous Angular 1.5/6 shared scope.
  * components in general in A2 resemble directives from the 1.x days.
* System.js can be used to bootstrap an app and include it on an html page.

### Components

* This is becoming the building block of the web with these kinds of frameworks.
* We define a tag that has some kind of special meaning to the angular application 
  * this tag is usually named accordingly to it's function ex: `<weather></weather>`
  * this is very similiar to what VueJs does with it's component/tag system.
* Components have an annotation and a Class definition (usually both, rarely one or the other)
  * the class definition here is very much a TypeScript class
* They usually have a selector that names the new tag and a template string literal.

### Debugging

* [[TypeScript]] has source maps but must be turned on in the `.tsconfig` file.
  * this is handy when using a `debugger` call and viewing the file as .ts versus .js
* [Augury][1] is a great extension for viewing the visual component tree of an Angular2 app.
* Angular2 does not have the same kind of `$log` service as Ang1

### Templates

* Every template will have it's own `style` tag.
  * This can be imported using the `import url()` syntax or can be written inline.
* Binding to a model is done by peppering markup tags with `#modelName`
  * If one were to add this to an input field `<input type="text" #todo>` everything will automatically sync.
  * This syntax is odd but it is nice that this function is opt in.
* When using `[]` to surround an attribute it means that it is invoking 'data binding'.
  * If the attribute changes, it will be reflected immediately within the DOM.
  * Handy especially if an attribute is used to toggle specific CSS classes.
* When getting the value from an element use the `#someReference.value`

### Pipes

* Ways to move data throughout transforms (think Unix pipes).
* Can also be thought of as Angular1 'Filters'.

[1]: https://augury.angular.io
