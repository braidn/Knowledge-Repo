# Angular 2

[[_TOC_]]

## Notes

* The `@` connotation above a class, is for annotations.
  * These usually take an object that outlines information for the class.
  * Two that are particularly important are `Component` and `Template`
* Constructor functions often times ask Angular to instantiates the dependencies and types.
  * This is actually not dependency injection but IoC(Inversion of Control)

### Templates

* Every template will have it's own `style` tag.
  * This can be imported using the `import url()` syntax or can be written inline.
* Binding to a model is done by peppering markup tags with `#modelName`
  * If one were to add this to an input field `<input type="text" #todo>` everything will automatically sync.
  * This syntax is odd but it is nice that this function is opt in.
* When using `[]` to surround an attribute it means that it is invoking 'data binding'.
  * If the attribute changes, it will be reflected immediately within the DOM.
  * Handy especially if an attribute is used to toggle specific CSS classes.