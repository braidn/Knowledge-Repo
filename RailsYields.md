* The application layout sits in here. If rails finds no layouts for a `<%= yield %>` call then it will default to application
  * You can call the name of the layout as a string in the specific controller
    * Ex: `layout "standard" or control what actions it will accept layout "standard", :only(or :except => [:rss, :atom]`
* `content_for(:name_Of_Yield)` blocks are cool because they can pass information around that gets fired in specific templates
  * page 384 of Agile Web Dev, 4th Edition explains this nicely