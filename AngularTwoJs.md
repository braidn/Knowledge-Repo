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
* Components have an decorator and a Class definition (usually both, rarely one or the other)
  * the class definition here is very much a TypeScript class
  * and can be thought of as the controller in MVC.
  * the decorator is where we configure the component and map how the outside world interacts with the component
* They usually have a selector that names the new tag and a template string literal.
* A components 'host' is the element that the component is attached to. 
  * This is often times the name of `selector` portion of the component's declaration.
* Unlike A1, directives don't match globally. This means we need to explicitely add them.
  * This is done using the `directives: [DirectiveComponent]` property to the parent components.
* It is always a good thing to try and isolate data structures from the component code.
* Just like with most MVC structures, we want to move most of the logic out of components and into class/models
* An *ngFor directive can be used to create multiples of the component in it's declaration.
* Inputs to the component are handled with `[]` and outputs use `()`.
  * these can be thought of as the public API for the component.

#### Inputs or 'Props'

* Inputs that are passed to a component from its' parent.
* written like: `<componentName [inputName]="value">`
  + received by the component like: `inputs: ['inputName']`
  * there is also an option to take key/value pairs int the inputs array versus strings
* The class should define an instance variable for each input.
* The name goes into the component definition, not the class.
  * These are arrays so a component can be passed any # of inputs.

#### Ouputs

* Used to send data from the component to the outside world.
* There are many outputs to listen to: click, dbl-click, mousedown, etc
* Custom events can be emitted by a Component.
  * These are called `EventEmitters` and are basically RxJS.
  * A2 will automagically subscribe to these EventEmitters for us.
* _Setting up_ an EventMitter requires 3 declarations (usually)
  1. A propery on the class of type: `EventEmitter<string>` is created.
  1. During initialization, a `new EventEmitter()` is bound to this property
  1. A void method calls `.emit('some string')` on this emitter
* Any parent component listening on this event will respond accordingly

### Models

* No specific model library is provided by A2 which is actually pretty bizarre.
  * due to this fact, it's common to start out with simple POJOs.

### Data Architecture

* A1 used Two Way data binding that became incridbly laborious as the application grew.
* A2 uses what's common in React/Flux and implements one way data binding.
  * this can be thought of data flowing only down through the component tree.
* Two major contendors for data management:
  1. RXJS and observables
  2. Flux/Redux style of architecture.

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

### Template Tags

* `#someValue`: called a resolve and used to bind a piece of markup to a variable.
  * these are actually considered objects so they come with a bunch of fun methods.
  * in typescript land these are usually of type HTMLInputElement or HTML something.

### Pipes

* Ways to move data throughout transforms (think Unix pipes).
* Can also be thought of as Angular1 'Filters'.

[1]: https://augury.angular.io
