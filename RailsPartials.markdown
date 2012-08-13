* Sometimes called partial-page templates and MUST always start with an underscore (_)
* Invoked one or more times from within another template, potentially passing it objects to render as parameters. When the partial template finishes rendering, it returns control to the calling template
* to use call: `<%= render(:partial => "name_Of_Partial", :object => @if_Different_From_Name) %>`
  * which also can be written as: `<%= render(partial: 'name_Of_Partial', object: @if_Different_From_Name)`
  * or a simpler use: `<%= render 'name_WithoutUnderscore_In_Same_Dir' %>`

in addition you can add local variables to the partial by passing a `:locals => {}` hash along with :object and :partial

* Ex: `:locals => {authorized_by => sessions[:user_name], :from_ip => request.remote_ip})`
  * this can also done when you call it. So if you call `render @cart` you have added the variable from @cart into the partial and is now available without the @ symbol in the partial itself...Partials are complex little things most of the time.
* `:partial` adheres to every entry where `:collection => " {{collectionName}} "` to each member of a collection or list of items
* incredibly valuable when iterating over a list of items
* `:spacer_template => "templateName"` is a kind of shim that gets placed between each item in an object. So if you wanted a space between each item you might have `<br />` in the _spacer template

Rails can detect a / in the name of a `:partial` call and will figure it to be a call to a dir in app/views. This means you could hold all of your header / footer stuff in a folder called shared/ and call `:partial => "shared/Name"` when needed across views