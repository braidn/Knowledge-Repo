# Webpack

## Notes

* When webpack-dev-server is setup properly, no js includes are required during development.
  * when the bundle is built for production, these will be automagically added. 

## With Rails

* Recommended to run in [hot reload mode][1]
* Build scripts accessible by navigating to `localhost:8080/bundle.js`
* [This code can be used][2] to have rails use localhost:8080 for serving assets in dev  

[1]: http://webpack.github.io/docs/webpack-dev-server.html
[2]: ReactRailsAssetConfig