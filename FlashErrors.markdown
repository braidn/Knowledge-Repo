* super easy way to build flash errors into a specific controller, view, whatever:
  * `notice: 'message'`
* `flash.now[:notice] = 'message'` will flash a message for the current controller only
  * best used for home page welcomes and with the render controller method
* `flash[.notice] = 'message'` will flash for the next controller
  * best used with the render controller method
* {{RenderSampleTemplateCode}}