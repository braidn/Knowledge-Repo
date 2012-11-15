* `resource` calls produce singular paths instead of plural for `resources`
  * article_path vs articles_path
  * article_path will take the user to the resource (think find by id or show)
  * and articles_path will take the user to the index route
* `resource` is dwarfed to 6 actions because really? Why index only one item