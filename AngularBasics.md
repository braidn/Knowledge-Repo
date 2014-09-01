

## Scopes

>Scopes are necessary due to isolating data between different controllers and directives. If scopes are not used than pollution between ctrls/directives may and will occur.  

3 different kind of scopes:

1. `@` which simply reads info back from the dom element string.
1. `=` anything updated in the view will update in the controller scope.
1. `&` call a method from a directive to a controller.