# React Patterns

## Notes

* Components can be thought of as their own little isolated systems.
  * They have their own state, input and output.
* Using `props.children` we can keep our composed functions agnostic and dependency free.
 * this is due to pretty much anything be able to be passed down through props.