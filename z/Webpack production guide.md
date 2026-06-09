
https://webpack.js.org/guides/production/

The goals of _development_ and _production_ builds differ greatly. In _development_, we want strong source mapping and a localhost server with live reloading or [[hot module replacement]]. In _production_, our goals shift to a focus on minified bundles, lighter weight source maps, and optimized assets to improve load time. With this logical separation at hand, we typically recommend writing **separate webpack configurations** for each environment.