* Layouts are controller specific and are found in: app/views/layout
* {{RailsYields}}
* What layout is chosen from the layout dir can be controlled in the specific controller
  * `layout 'name'`
  * using `layout 'nil'` will turn off layouts for a specific controller
  * specific actions use `render(layout: 'name')`
* Use `content_for(:name_Of_Yield)` to yield specific sections from the layout file
* {{RailsPartials}}
* {{RailsForms}}