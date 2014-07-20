###Components

* `Component` is the building block behind React
* The UI layer can be though of as a tree (think BTree) of components
* Components have a `render()` method that creates an intermediate-DOM
* Calling `renderComponent()` on the root of the tree will recursively build its' entire DOM
